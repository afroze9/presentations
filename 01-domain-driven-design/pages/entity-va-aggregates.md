---
layout: three-col
title: Entities, Value Objects, and Aggregates
---

::header::
# Entities, Value Objects, and Aggregates

::left::
## Entities
Objects that have a distinct identity

e.g. Product
<LightOrDark>
    <template #light>
      <img src="images/car-black.png" width="250">
    </template>
    <template #dark>
      <img src="images/car-white.png" width="250">
    </template>
</LightOrDark>

::center::
## Value Objects
Objects without a distinct identity; defined by their attributes

e.g. Price
<LightOrDark>
    <template #light>
      <img src="images/apple-black.png" width="250">
    </template>
    <template #dark>
      <img src="images/apple-white.png" width="250">
    </template>
</LightOrDark>


::right::
## Aggregates
Clusters of related entities and value objects

e.g. Order

<div style="margin-left: auto; margin-right: auto;">
```mermaid
classDiagram
    Order: +DateTime OrderDate
    Order: +Address Address
    Order: +int BuyerId
    Order: +OrderStatus OrderStatus
    Order: +string Description
    Order: +bool IsDraft
    Order: +List<OrderItem> OrderItems
    Order: +int PaymentMethodId
```
</div>

<!-- <LightOrDark>
    <template #light>
      <img src="images/order-aggregate-black.png" >
    </template>
    <template #dark>
      <img src="images/order-aggregate-white.png" >
    </template>
</LightOrDark> -->
