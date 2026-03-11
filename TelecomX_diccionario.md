# 📖 Diccionario de Datos — TelecomX

Este diccionario describe cada variable presente en el dataset utilizado para el análisis de churn de clientes de TelecomX.

---

## 🆔 Identificación

| Campo | Descripción |
|-------|-------------|
| `customerID` | Número de identificación único de cada cliente |
| `Churn` | Indica si el cliente abandonó (`Yes`) o no (`No`) la empresa |

---

## 👤 Datos del Cliente (`customer`)

| Campo | Descripción |
|-------|-------------|
| `gender` | Género del cliente: `Male` (masculino) o `Female` (femenino) |
| `SeniorCitizen` | Indica si el cliente tiene 65 años o más: `1` (sí) o `0` (no) |
| `Partner` | Indica si el cliente tiene pareja: `Yes` / `No` |
| `Dependents` | Indica si el cliente tiene dependientes a su cargo: `Yes` / `No` |
| `tenure` | Cantidad de meses que el cliente lleva contratado con la empresa |

---

## 📞 Servicios Telefónicos (`phone`)

| Campo | Descripción |
|-------|-------------|
| `PhoneService` | Indica si el cliente está suscrito al servicio telefónico: `Yes` / `No` |
| `MultipleLines` | Indica si el cliente tiene más de una línea telefónica: `Yes` / `No` / `No phone service` |

---

## 🌐 Servicios de Internet (`internet`)

| Campo | Descripción |
|-------|-------------|
| `InternetService` | Proveedor de internet contratado: `DSL`, `Fiber optic` o `No` |
| `OnlineSecurity` | Suscripción adicional de seguridad en línea: `Yes` / `No` / `No internet service` |
| `OnlineBackup` | Suscripción adicional de respaldo en línea: `Yes` / `No` / `No internet service` |
| `DeviceProtection` | Suscripción adicional de protección del dispositivo: `Yes` / `No` / `No internet service` |
| `TechSupport` | Suscripción adicional de soporte técnico (menor tiempo de espera): `Yes` / `No` / `No internet service` |
| `StreamingTV` | Suscripción de televisión por cable/streaming: `Yes` / `No` / `No internet service` |
| `StreamingMovies` | Suscripción de streaming de películas: `Yes` / `No` / `No internet service` |

---

## 💳 Datos de Cuenta (`account`)

| Campo | Descripción |
|-------|-------------|
| `Contract` | Tipo de contrato: `Month-to-month`, `One year` o `Two year` |
| `PaperlessBilling` | Indica si el cliente prefiere recibir la factura en línea: `Yes` / `No` |
| `PaymentMethod` | Forma de pago: `Electronic check`, `Mailed check`, `Bank transfer (automatic)`, `Credit card (automatic)` |
| `Charges.Monthly` | Total mensual cobrado al cliente por todos sus servicios (numérico) |
| `Charges.Total` | Total acumulado gastado por el cliente durante su permanencia (numérico) |

---

## 📝 Notas

- El dataset proviene de una API en formato JSON con estructura anidada. Durante el proceso ETL se normaliza a un DataFrame plano.
- Los campos `Charges.Monthly` y `Charges.Total` pueden contener valores en formato string que deben convertirse a `float`.
- Los valores vacíos (`""`) en `Charges.Total` deben tratarse como `NaN` y luego imputarse o eliminarse según corresponda.
