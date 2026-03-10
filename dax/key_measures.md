# 🧠 Core DAX Implementation

Advanced analytical measures designed to evaluate checkout funnel performance, detect friction points, and measure overall conversion efficiency.

---

## 🔵 1. Overall Conversion Rate (CR)

> **Business Logic:**
The primary North Star metric for the project. It evaluates funnel efficiency by calculating the ratio of successful transactions to sessions with add-to-cart events.

```DAX
Conversion Rate = 
DIVIDE (
    [Sales Transactions],
    [Sessions with Add-to-Cart]
)
```
---

## 🟢 2. Step-by-Step Conversion Analysis

> **Business Logic:**
This advanced measure uses variables (`VAR`) and context manipulation to calculate the retention rate between consecutive stages of the checkout funnel.

```DAX
Conversion by Step-by-Step = 
VAR PasoActual =
    SELECTEDVALUE ( 'Funnel Steps'[Orden Funnel] )

VAR UsuariosPasoActual =
    [Users with Add-to-Cart]

VAR UsuariosPasoAnterior =
    CALCULATE (
        [Users with Add-to-Cart],
        FILTER (
            ALL ( 'Funnel Steps' ),
            'Funnel Steps'[Orden Funnel] = PasoActual - 1
        )
    )

RETURN
IF (
    PasoActual = 1,
    BLANK(),
    DIVIDE ( UsuariosPasoActual, UsuariosPasoAnterior )
)
```
---


## 🔴3. Dynamic Top Friction Point Identification

> **Business Logic:**
A diagnostic measure designed to automatically scan the entire checkout process and identify the stage with the highest drop-off rate.

```DAX
Top Friction Point: Add to Cart to Checkout = 
MAXX (
    FILTER (
        ALL ( 'Funnel Steps' ),
        'Funnel Steps'[Orden Funnel] > 1
    ),
    [Drop-off by Checkout Step]
)

```
---

## 🟡 4. AVERAGE PRODUCTS PER BUYER
> **Business Logic:**
This metric defines the average volume of items purchased per customer. It is essential for understanding buying behavior and calculating the potential for Average Order Value (AOV) growth.

```DAX
Avg Products per Buyer = 
DIVIDE (
    [Total Units Sold],
    [Unique Purchasers]
)
```
---
