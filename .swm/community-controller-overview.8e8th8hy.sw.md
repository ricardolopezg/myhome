---
title: Community Controller Overview
---
# Main classes/functions/files related to Community Controller

The <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="59:4:4" line-data="public class CommunityController implements CommunitiesApi {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityController`</SwmToken> class contains several methods for handling community-related requests. These include <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="64:8:8" line-data="  public ResponseEntity&lt;CreateCommunityResponse&gt; createCommunity(@Valid @RequestBody" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`createCommunity`</SwmToken>, <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="76:8:8" line-data="  public ResponseEntity&lt;GetCommunityDetailsResponse&gt; listAllCommunity(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listAllCommunity`</SwmToken>, <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="91:8:8" line-data="  public ResponseEntity&lt;GetCommunityDetailsResponse&gt; listCommunityDetails(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listCommunityDetails`</SwmToken>, <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="105:8:8" line-data="  public ResponseEntity&lt;ListCommunityAdminsResponse&gt; listCommunityAdmins(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listCommunityAdmins`</SwmToken>, <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="119:8:8" line-data="  public ResponseEntity&lt;GetHouseDetailsResponse&gt; listCommunityHouses(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`listCommunityHouses`</SwmToken>, <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="133:8:8" line-data="  public ResponseEntity&lt;AddCommunityAdminResponse&gt; addCommunityAdmins(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`addCommunityAdmins`</SwmToken>, <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="150:8:8" line-data="  public ResponseEntity&lt;AddCommunityHouseResponse&gt; addCommunityHouses(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`addCommunityHouses`</SwmToken>, and <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="168:8:8" line-data="  public ResponseEntity&lt;Void&gt; removeCommunityHouse(" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`removeCommunityHouse`</SwmToken>. Each of these methods corresponds to a specific HTTP request and uses the <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="60:5:5" line-data="  private final CommunityService communityService;" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityService`</SwmToken> and <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="61:5:5" line-data="  private final CommunityApiMapper communityApiMapper;" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityApiMapper`</SwmToken> to process the request and generate a response.This document will cover the Community Controller in the MyHome project. We'll cover:

1. What is the Community Controller
2. The main classes/functions/files that are related to the Community Controller

# What is the Community Controller

The <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="59:4:4" line-data="public class CommunityController implements CommunitiesApi {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityController`</SwmToken> is a class in the <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="17:2:6" line-data="package com.myhome.controllers;" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`com.myhome.controllers`</SwmToken> package. It implements the <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="59:8:8" line-data="public class CommunityController implements CommunitiesApi {" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunitiesApi`</SwmToken> interface and is responsible for handling HTTP requests related to communities. It uses <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="60:5:5" line-data="  private final CommunityService communityService;" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityService`</SwmToken> for business logic and <SwmToken path="/service/src/main/java/com/myhome/controllers/CommunityController.java" pos="61:5:5" line-data="  private final CommunityApiMapper communityApiMapper;" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="myhome">`CommunityApiMapper`</SwmToken> for converting between DTOs and domain objects.

<SwmSnippet path="/service/src/main/java/com/myhome/controllers/CommunityController.java" line="56" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==">

---

&nbsp;

```java
@RequiredArgsConstructor
@RestController
@Slf4j
public class CommunityController implements CommunitiesApi {
  private final CommunityService communityService;
  private final CommunityApiMapper communityApiMapper;

  @Override
  public ResponseEntity<CreateCommunityResponse> createCommunity(@Valid @RequestBody
      CreateCommunityRequest request) {
    log.trace("Received create community request");
    CommunityDto requestCommunityDto =
        communityApiMapper.createCommunityRequestToCommunityDto(request);
    Community createdCommunity = communityService.createCommunity(requestCommunityDto);
    CreateCommunityResponse createdCommunityResponse =
        communityApiMapper.communityToCreateCommunityResponse(createdCommunity);
    return ResponseEntity.status(HttpStatus.CREATED).body(createdCommunityResponse);
  }

  @Override
  public ResponseEntity<GetCommunityDetailsResponse> listAllCommunity(
```

---

</SwmSnippet>

*This is an auto-generated document by Swimm AI 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
