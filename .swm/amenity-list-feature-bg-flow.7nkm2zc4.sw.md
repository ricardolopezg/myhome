---
title: Amenity list feature bg & flow
---
&nbsp;

### Background

Mike found a list of expected basic amenities as foundation, see here: [docs.google.com/d/1lMk5V](https://docs.google.com/spreadsheets/d/1lMk5V-uJ4QCVkwCCrCHSarOAZanDvI_iW07VRdOhFCM/edit#gid=0). It was gradually updated per users request (if enough people submitted proposals). So you're probably seeing fancy amenities like pool house, drive-in movie theatre, basketball court, music room etc.

&nbsp;

### <SwmToken path="/service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> Flow

The process of getting the common amenity list in a community involves using the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> method in the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="25:4:4" line-data="public interface AmenityService {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityService`</SwmToken> interface. This method is implemented in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="58:10:10" line-data="    Set&lt;Amenity&gt; amenities = amenitySDJpaService.listAllAmenities(communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`amenitySDJpaService`</SwmToken> class and used in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="41:4:4" line-data="public class AmenityController implements AmenitiesApi {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityController`</SwmToken> class.

<SwmSnippet path="/service/src/main/java/com/myhome/services/AmenityService.java" line="33" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==">

---

<SwmLink doc-title="How do we get the common amenity list appeared in the community?" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome" path=".swm/how-do-we-get-the-common-amenity-list-appeared-in-the-community.4zkhvx7m.sw.md">[How do we get the common amenity list appeared in the community?](https://app.swimm.io/repos/Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw%3D%3D/docs/4zkhvx7m)</SwmLink>:\
The <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`listAllAmenities`</SwmToken> method in the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="25:4:4" line-data="public interface AmenityService {" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">`AmenityService`</SwmToken> interface is designed to get all amenities for a specific community.

```java
  Set<Amenity> listAllAmenities(String communityId);
```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/controllers/AmenityController.java" line="56" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==">

---

<SwmLink doc-title="How do we get the common amenity list appeared in the community?" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome" path=".swm/how-do-we-get-the-common-amenity-list-appeared-in-the-community.4zkhvx7m.sw.md">[How do we get the common amenity list appeared in the community?](https://app.swimm.io/repos/Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw%3D%3D/docs/4zkhvx7m)</SwmLink>:\
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

<SwmMeta version="3.0.0"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
