---
title: Where do we get the common amenities list?
---
### \
Deciding on amenities

<SwmMention uid="CZeI81ju5XMJ39Obh3HLKzgwKeq2">[Eden Hermelin](mailto:eden@swimm.io)</SwmMention> found a list of expected basic amenities as foundation. It was gradually updated per users request (if enough people submitted proposals).

### 

### List All Amenities Flow

The process of getting the common amenities list in the 'myhome' repository involves using the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listAllAmenities`</SwmToken> method in the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="25:4:4" line-data="public interface AmenityService {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`AmenityService`</SwmToken> interface. This method is implemented in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="41:4:4" line-data="public class AmenityController implements AmenitiesApi {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`AmenityController`</SwmToken> class. However, it's important to note that there might be other ways to retrieve this list that are not mentioned in the info I found.

<SwmSnippet path="/service/src/main/java/com/myhome/services/AmenityService.java" line="33" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==">

---

The <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="33:6:6" line-data="  Set&lt;Amenity&gt; listAllAmenities(String communityId);" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listAllAmenities`</SwmToken> method in the <SwmToken path="service/src/main/java/com/myhome/services/AmenityService.java" pos="25:4:4" line-data="public interface AmenityService {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`AmenityService`</SwmToken> interface is designed to get all amenities for a specific community.

```java
  Set<Amenity> listAllAmenities(String communityId);
```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/controllers/AmenityController.java" line="56" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==">

---

The <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="56:10:10" line-data="  public ResponseEntity&lt;Set&lt;GetAmenityDetailsResponse&gt;&gt; listAllAmenities(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listAllAmenities`</SwmToken> method is used in the <SwmToken path="service/src/main/java/com/myhome/controllers/AmenityController.java" pos="41:4:4" line-data="public class AmenityController implements AmenitiesApi {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`AmenityController`</SwmToken> class to get all amenities for a specific community and return them in a response.

```java
  public ResponseEntity<Set<GetAmenityDetailsResponse>> listAllAmenities(
      @PathVariable String communityId) {
    Set<Amenity> amenities = amenitySDJpaService.listAllAmenities(communityId);
    Set<GetAmenityDetailsResponse> response =
        amenityApiMapper.amenitiesSetToAmenityDetailsResponseSet(amenities);
    return ResponseEntity.ok(response);
  }
```

---

</SwmSnippet>

<SwmMeta version="3.0.0"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
