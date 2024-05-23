---
title: Amenity lists
---
&nbsp;

## Listing all amenities flow

Getting the common amenity list in a community involves using the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> method in the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="25:4:4" line-data="public interface AmenityService {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityService`</SwmToken> interface. This method is implemented in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="58:10:10" line-data="    Set&lt;Amenity&gt; amenities = amenitySDJpaService.listAllAmenities(communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`amenitySDJpaService`</SwmToken> class and used in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="41:4:4" line-data="public class AmenityController implements AmenitiesApi {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityController`</SwmToken> class.

<SwmSnippet path="/service/src/main/java/com/myhome/services/AmenityService.java" line="33" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==">

---

The <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> method in the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="25:4:4" line-data="public interface AmenityService {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityService`</SwmToken> interface is designed to get all amenities for a specific community.

```java
  Set<Amenity> listAllAmenities(String communityId);
```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/services/springdatajpa/AmenitySDJpaService.java" line="82" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==">

---

The <SwmToken path="service/src/main/java/com/myhome/services/springdatajpa/AmenitySDJpaService.java" pos="82:8:8" line-data="  public Set&lt;Amenity&gt; listAllAmenities(String communityId) {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> method is implemented in the <SwmToken path="service/src/main/java/com/myhome/services/springdatajpa/AmenitySDJpaService.java" pos="37:4:4" line-data="public class AmenitySDJpaService implements AmenityService {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenitySDJpaService`</SwmToken> class. It uses the <SwmToken path="service/src/main/java/com/myhome/services/springdatajpa/AmenitySDJpaService.java" pos="83:5:5" line-data="    return communityRepository.findByCommunityIdWithAmenities(communityId)" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`findByCommunityIdWithAmenities`</SwmToken> method from the <SwmToken path="service/src/main/java/com/myhome/services/springdatajpa/AmenitySDJpaService.java" pos="83:3:3" line-data="    return communityRepository.findByCommunityIdWithAmenities(communityId)" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`communityRepository`</SwmToken> to get the community and its amenities.

```java
  public Set<Amenity> listAllAmenities(String communityId) {
    return communityRepository.findByCommunityIdWithAmenities(communityId)
        .map(Community::getAmenities)
        .orElse(new HashSet<>());
  }
```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/controllers/AmenityController.java" line="56" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==">

---

The <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="56:10:10" line-data="  public ResponseEntity&lt;Set&lt;GetAmenityDetailsResponse&gt;&gt; listAllAmenities(" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> method is used in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="41:4:4" line-data="public class AmenityController implements AmenitiesApi {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityController`</SwmToken> class to get all amenities for a specific community and return them in a response.

```java
  public ResponseEntity<Set<GetAmenityDetailsResponse>> listAllAmenities(
      @PathVariable String communityId) {
    Set<Amenity> amenities = amenitySDJpaService.listAllAmenities(communityId);
    Set<GetAmenityDetailsResponse> response =
        amenityApiMapper.amenitiesSetToAmenityDetailsResponseSet(amenities);
    return ResponseEntity.ok(response);
```

---

</SwmSnippet>

### Background

Mike did a research on the expected amenities that sets the foundation. You can find the full list here: [docs.google.com/d/1lMk5V](https://docs.google.com/spreadsheets/d/1lMk5V-uJ4QCVkwCCrCHSarOAZanDvI_iW07VRdOhFCM/edit#gid=0). Anything not on the list are added by our users over the years.

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

<SwmMeta version="3.0.0"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
