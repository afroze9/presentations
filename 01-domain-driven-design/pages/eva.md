
# Entities, Value Objects, and Aggregates

<div class="eva-parent">

<!-- Div 1 -->
<div style="grid-area: 1 / 1 / 1 / 1;" v-click="1">

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

</div>

<!-- Div 2 -->
<div style="grid-area: 1 / 2 / 1 / 2;" v-click="2">

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

</div>

<!-- Div 3 -->
<div style="grid-area: 1 / 3 / 1 / 3;" v-click="3">

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


</div>


</div>

<style>
.eva-parent {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 1fr;
  grid-column-gap: 24px;
  grid-row-gap: 0px;
}
</style>