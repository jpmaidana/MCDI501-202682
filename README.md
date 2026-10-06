# MCDI501-202682

**Estadística Computacional para la Toma de Decisiones (MCDI501)**
Magíster en Ciencia de Datos e Inteligencia Artificial — Universidad Andrés Bello (UNAB)
Periodo académico: **2026-82**

Repositorio personal de estudio y trabajo del curso: apuntes ejecutables en Jupyter,
diapositivas de apoyo, ejemplos de evaluaciones y plantillas de informe. El caso de
aplicación transversal es el dataset **Give Me Some Credit** (riesgo crediticio).

---

## Contenido

- [Estructura del repositorio](#estructura-del-repositorio)
- [Contenidos del curso](#contenidos-del-curso)
- [Evaluaciones](#evaluaciones)
- [Puesta en marcha](#puesta-en-marcha)
- [Datos](#datos)
- [Plantillas de informe](#plantillas-de-informe)
- [Convenciones](#convenciones)
- [Créditos y licencia](#créditos-y-licencia)

---

## Estructura del repositorio

```
MCDI501-202682/
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
│
├── data/
│   ├── README.md                  # cómo obtener el dataset
│   └── raw/                       # cs-training.csv (ignorado por git)
│
├── 01-apuntes/                    # notebooks de clase, uno por tema
│   ├── semana-01-eda-inferencia/
│   ├── semana-02-simulacion-remuestreo/
│   └── semana-03-modelamiento-predictivo/
│
├── 02-diapositivas/               # PDF de apoyo por semana
│
├── 03-evaluaciones/               # trabajo de las evaluaciones
│   ├── formativa-1-eda-inferencia/
│   ├── sumativa-1-analisis-exploratorio-inferencial/
│   ├── formativa-2-modelamiento-predictivo/
│   ├── sumativa-2-validacion-simulacion-remuestreo/
│   └── sumativa-3-modelamiento-predictivo-integrado/
│       ├── notebook.ipynb         # código
│       └── informe.pdf            # entregable
│
├── 04-plantillas/
│   ├── latex/                     # una subcarpeta por evaluación + logo compartido
│   └── word/                      # versiones .docx
│
└── assets/
    └── logo_unab.png              # logo único, compartido
```

Cada carpeta numerada responde a una pregunta distinta: *qué aprendí* (`01`),
*en qué me apoyé* (`02`), *qué entregué* (`03`) y *con qué formato* (`04`).

## Contenidos del curso

| Semana | Tema | Notebooks (`01-apuntes/`) |
| --- | --- | --- |
| 1 | Análisis exploratorio e inferencia | Tipos de variables, visualización, tendencia central, dispersión, media, prueba *t*/*Z*, inferencia |
| 2 | Simulación, validación y remuestreo | Aleatoriedad, simulación, Ley de los Grandes Números, Monte Carlo, estimación de parámetros, convergencia, datos sintéticos, bootstrap |
| 3 | Modelamiento predictivo | Aprendizaje supervisado, preparación de datos, regresión lineal múltiple, diagnóstico de supuestos, regresión logística, selección de variables y comparación de modelos |

## Evaluaciones

| Evaluación | Fase | Ponderación | Foco |
| --- | --- | --- | --- |
| Formativa 1 | 2 | 0 % | EDA e inferencia |
| Sumativa 1 | 2 | 20 % | Análisis exploratorio e inferencial |
| Formativa 2 | 3 | 0 % | Modelamiento predictivo |
| Sumativa 2 | 3 | 20 % | Validación, simulación y remuestreo |
| Sumativa 3 | 4 | 60 % | Modelamiento predictivo integrado |

Los ejemplos incluidos corresponden a trabajos de referencia sobre *Give Me Some Credit*.
Úsalos como guía de estructura y nivel de análisis, no como base para copiar.

## Puesta en marcha

Requisitos: Python 3.10 o superior y Git.

```bash
git clone https://github.com/<usuario>/MCDI501-202682.git
cd MCDI501-202682

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt

jupyter lab
```

Librerías principales usadas en los notebooks: `numpy`, `pandas`, `scipy`,
`statsmodels`, `scikit-learn`, `imbalanced-learn`, `matplotlib`, `seaborn`, `joblib`.

También puedes abrir cualquier notebook en Google Colab o VS Code sin instalar nada local.

## Datos

El dataset **Give Me Some Credit** (`cs-training.csv`) no se versiona en el repositorio.
Los notebooks lo buscan en `data/raw/cs-training.csv` y, si no lo encuentran, lo
descargan desde un espejo público.

Para dejarlo disponible localmente:

1. Descárgalo desde [Kaggle — Give Me Some Credit](https://www.kaggle.com/c/GiveMeSomeCredit/data).
2. Guárdalo como `data/raw/cs-training.csv`.

Detalle del diccionario de variables en [`data/README.md`](data/README.md).

## Plantillas de informe

Hay una plantilla por evaluación, en LaTeX y en Word.

**LaTeX (recomendado: Overleaf)**
1. En Overleaf: *New Project → Upload Project*.
2. Sube `plantilla.tex` junto con `assets/logo_unab.png` (deben quedar en el mismo proyecto).
3. Completa los datos de portada y desarrolla cada sección donde dice `[Desarrollen aquí]`.

**LaTeX local**
```bash
cd 04-plantillas/latex/sumativa-1-analisis-exploratorio-inferencial
pdflatex plantilla.tex && pdflatex plantilla.tex
```

**Word**: usa los archivos de `04-plantillas/word/`.

Paquetes LaTeX requeridos: `geometry`, `graphicx`, `xcolor`, `titlesec`, `fancyhdr`,
`tcolorbox`, `hyperref`, `booktabs`, `enumitem`, `array`.

## Convenciones

- **Nombres de archivo:** minúsculas, guiones, sin espacios ni tildes (`regresion-logistica.ipynb`).
- **Notebooks:** se versionan con las salidas limpias; si se quiere conservar el resultado
  renderizado, exportar a PDF o HTML.
- **Semillas:** fijar `random_state` / `np.random.seed` para reproducibilidad.
- **Commits:** mensajes cortos en español en modo imperativo
  (`Agrega apunte de bootstrap`, `Corrige ruta de datos`).
- **Datos y credenciales:** nada de datos crudos, claves ni archivos `.env` en el repositorio.

## Créditos y licencia

Material del curso MCDI501, UNAB. Las diapositivas y enunciados pertenecen a sus autores y
a la institución; el código y los apuntes propios se publican bajo la licencia indicada en
[`LICENSE`](LICENSE).

El dataset *Give Me Some Credit* pertenece a Kaggle / Credit Fusion y se rige por sus propios
términos de uso.
