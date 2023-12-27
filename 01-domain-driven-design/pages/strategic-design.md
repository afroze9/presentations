---
title: Strategic Design
---

# Strategic Design

<br/>

## The high-level design decisions that shape the architecture and organization of the software

<div class="parent">

<!-- Div 1 -->
<div style="grid-area: 1 / 1 / 1 / 1;" v-click="1">

## Aggregates

<div style="margin-left: auto; margin-right: auto;">

```mermaid
classDiagram
    Order: +DateTime OrderDate
    Order: +Address Address
    Order: +int BuyerId
    Order: +OrderStatus OrderStatus
    Order: +string Description
    Order: +bool IsDraft
    Order: +List&ltOrderItem&gt OrderItems
    Order: +int PaymentMethodId
```
</div>

</div>

<!-- Div 2 -->
<div style="grid-area: 1 / 2 / 1 / 2;" v-click="2">

## Repositories

<div style="margin-left: auto; margin-right: auto;">

```mermaid
flowchart TD
    DB1[(Orders Database)]
```

```mermaid
flowchart TD
    DB2[(Products Database)]
```

```mermaid
flowchart TD
    DB3[(Payments Database)]
```
</div>

</div>

<!-- Div 3 -->
<div style="grid-area: 1 / 3 / 1 / 3;" v-click="3">

## Services

<div style="margin-left: auto; margin-right: auto;">

```mermaid
flowchart TD
    OS[Ordering Service]
```

```mermaid
flowchart TD
    PS[Product Service]
```

```mermaid
flowchart TD
    PS[Payment Service]
```
</div>

</div>


</div>

<style>
.parent {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 1fr;
  grid-column-gap: 24px;
  grid-row-gap: 0px;
}
</style>