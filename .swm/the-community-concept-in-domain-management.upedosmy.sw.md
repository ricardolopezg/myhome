---
title: The Community Concept in Domain Management
---
This document will cover the concept of 'Community' within the MyHome project. We'll cover:

1. What 'Community' is in the context of the project.
2. The main classes and fields related to 'Community'.

# What is 'Community' in MyHome

In the context of the MyHome project, a 'Community' represents a group of houses and amenities. It is implemented as a class in the <SwmPath repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome" path="/service/src/main/java/com/myhome/domain/Community.java">`(myhome) service/src/main/java/com/myhome/domain/Community.java`</SwmPath> file. A 'Community' has several attributes such as a unique ID, name, and district. It also has relationships with other entities such as 'User' (as admins), <SwmToken path="/service/src/main/java/com/myhome/domain/CommunityHouse.java" pos="56:4:4" line-data="public class CommunityHouse extends BaseEntity {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityHouse`</SwmToken>, and 'Amenity'.

<SwmSnippet path="/service/src/main/java/com/myhome/domain/Community.java" line="65" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==">

---

# Main Classes and Fields Related to 'Community'

The 'Community' class is defined here. It extends the <SwmToken path="/service/src/main/java/com/myhome/domain/Community.java" pos="65:8:8" line-data="public class Community extends BaseEntity {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`BaseEntity`</SwmToken> class and includes fields for admins, houses, name, <SwmToken path="/service/src/main/java/com/myhome/domain/Community.java" pos="75:5:5" line-data="  private String communityId;" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`communityId`</SwmToken>, district, and amenities. The 'admins' field represents the users who are administrators of the community. The 'houses' field represents the houses within the community. The 'amenities' field represents the amenities available within the community.

```java
public class Community extends BaseEntity {
  @ToString.Exclude
  @ManyToMany(fetch = FetchType.LAZY)
  private Set<User> admins = new HashSet<>();
  @ToString.Exclude
  @OneToMany(fetch = FetchType.LAZY)
  private Set<CommunityHouse> houses = new HashSet<>();
  @Column(nullable = false)
  private String name;
  @Column(unique = true, nullable = false)
  private String communityId;
  @Column(nullable = false)
  private String district;
  @ToString.Exclude
  @OneToMany(fetch = FetchType.LAZY, mappedBy = "community", orphanRemoval = true)
  private Set<Amenity> amenities = new HashSet<>();
}
```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/domain/CommunityHouse.java" line="56" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==">

---

The 'CommunityHouse' class is related to 'Community'. It represents a house within a community. The 'community' field in this class is a reference to the 'Community' that the house belongs to.

```java
public class CommunityHouse extends BaseEntity {
  @With
  @ManyToOne(fetch = FetchType.LAZY)
  private Community community;
  @With
  @Column(nullable = false)
  private String name;
  @With
  @Column(unique = true, nullable = false)
  private String houseId;
  @OneToMany(fetch = FetchType.LAZY)
  private Set<HouseMember> houseMembers = new HashSet<>();
  @OneToMany(fetch = FetchType.LAZY)
  private Set<Amenity> amenities = new HashSet<>();
}
```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/domain/Amenity.java" line="67" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==">

---

The 'Amenity' class is also related to 'Community'. It represents an amenity within a community. The 'community' field in this class is a reference to the 'Community' that the amenity belongs to.

```java
  @ManyToOne(fetch = FetchType.LAZY)
  private Community community;
  @ManyToOne
  private CommunityHouse communityHouse;
```

---

</SwmSnippet>

*This is an auto-generated document by Swimm AI 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
