# Datos

Los datos no se versionan en este repositorio. Esta carpeta explica cómo obtenerlos.

## Dataset: Give Me Some Credit

Datos de clientes de un banco para predecir si caerán en morosidad grave
(90 días o más de atraso) en los próximos 2 años.

- **Fuente:** [Kaggle — Give Me Some Credit](https://www.kaggle.com/c/GiveMeSomeCredit/data)
- **Archivo usado:** `cs-training.csv` (150.000 filas, 11 columnas más el índice)
- **Variable objetivo:** `SeriousDlqin2yrs` (1 = morosidad grave, 0 = no).
  Está desbalanceada: la clase 1 es una minoría pequeña.

## Cómo dejarlo disponible

1. Descarga `cs-training.csv` desde Kaggle.
2. Guárdalo en `data/raw/cs-training.csv`.

## Diccionario de variables

| Variable | Descripción |
| --- | --- |
| `SeriousDlqin2yrs` | Morosidad de 90 días o más (objetivo) |
| `RevolvingUtilizationOfUnsecuredLines` | Saldo de tarjetas y líneas sobre el límite total |
| `age` | Edad del cliente |
| `NumberOfTime30-59DaysPastDueNotWorse` | Veces con atraso de 30 a 59 días |
| `DebtRatio` | Pagos mensuales de deuda sobre ingreso mensual |
| `MonthlyIncome` | Ingreso mensual |
| `NumberOfOpenCreditLinesAndLoans` | Créditos y líneas abiertas |
| `NumberOfTimes90DaysLate` | Veces con atraso de 90 días o más |
| `NumberRealEstateLoansOrLines` | Créditos hipotecarios o inmobiliarios |
| `NumberOfTime60-89DaysPastDueNotWorse` | Veces con atraso de 60 a 89 días |
| `NumberOfDependents` | Número de dependientes |

## Valores faltantes conocidos

`MonthlyIncome` y `NumberOfDependents` tienen valores nulos.

## Estructura

- `raw/`: datos originales, sin modificar. No se versionan.
- `processed/` (opcional): datos limpios o derivados. Tampoco se versionan.