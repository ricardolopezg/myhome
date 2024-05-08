---
title: 'Payments, booking, and schedules '
---
<SwmSnippet path="/assets/FEATURES.md" line="48" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">

---

&nbsp;

```markdown
| Feature                            | Description                                                  | Notes |
| ---------------------------------- | ------------------------------------------------------------ | ----- |
| Schedule payment for house members | Community admins should be able to schedule payments for a house |       |
| Schedule recurring payments        | Community admins should be able to schedule recurring payments for a house |       |
| Marking payments as complete       | House members should be able to mark payments as paid.       |       |

```

---

</SwmSnippet>

<SwmSnippet path="/service/src/main/java/com/myhome/services/PaymentService.java" line="30" repo-id="Z2l0aHViJTNBJTNBbXlob21lJTNBJTNBc3dpbW1pbw==" repo-name="myhome">

---

&nbsp;

```java
public interface PaymentService {
  PaymentDto schedulePayment(PaymentDto request);

  Optional<PaymentDto> getPaymentDetails(String paymentId);

  Set<Payment> getPaymentsByMember(String memberId);

  Page<Payment> getPaymentsByAdmin(String adminId, Pageable pageable);

  Optional<HouseMember> getHouseMember(String memberId);
}
```

---

</SwmSnippet>

&nbsp;

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc2h1anUtbXlob21lJTNBJTNBcmljYXJkb2xvcGV6Zw==" repo-name="shuju-myhome"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
