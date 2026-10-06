# Plantillas MCDI501 — Estadística Computacional para la Toma de Decisiones

Plantillas en LaTeX para las evaluaciones formativas y sumativas del curso,
alineadas con los enunciados y rúbricas publicados en Canvas. Cada carpeta
corresponde a una evaluación y es **autocontenida**: trae su propio archivo
`.tex`, el logo institucional y un PDF de muestra, sin depender de nada fuera
de la carpeta.

## Estructura del repositorio

```
.
├── formativa-1-eda-inferencia/
│   ├── plantilla.tex
│   ├── logo_unab.png
│   └── preview.pdf
├── sumativa-1-analisis-exploratorio-inferencial/
│   ├── plantilla.tex
│   ├── logo_unab.png
│   └── preview.pdf
├── sumativa-2-validacion-simulacion-remuestreo/
│   ├── plantilla.tex
│   ├── logo_unab.png
│   └── preview.pdf
├── formativa-2-modelamiento-predictivo/
│   ├── plantilla.tex
│   ├── logo_unab.png
│   └── preview.pdf
└── sumativa-3-modelamiento-predictivo-integrado/
    ├── plantilla.tex
    ├── logo_unab.png
    └── preview.pdf
```

| Carpeta | Evaluación | Fase | Ponderación |
| --- | --- | --- | --- |
| `formativa-1-eda-inferencia` | Formativa 1 | Fase 2 | 0 % |
| `sumativa-1-analisis-exploratorio-inferencial` | Sumativa 1 | Fase 2 | 20 % |
| `sumativa-2-validacion-simulacion-remuestreo` | Sumativa 2 | Fase 3 | 20 % |
| `formativa-2-modelamiento-predictivo` | Formativa 2 | Fase 3 | 0 % |
| `sumativa-3-modelamiento-predictivo-integrado` | Sumativa 3 | Fase 4 | 60 % |

`preview.pdf` es solo una muestra de cómo se ve la plantilla compilada.
El archivo que se edita y se entrega es siempre `plantilla.tex`.

## Cómo usar la plantilla (para estudiantes)

### Opción A — Overleaf (recomendada, no requiere instalar nada)

1. Entra a [overleaf.com](https://www.overleaf.com) e inicia sesión.
2. Click en **New Project → Upload Project**.
3. Sube **los dos archivos de la carpeta correspondiente**: `plantilla.tex`
   y `logo_unab.png` (deben quedar juntos en el mismo proyecto).
4. Overleaf compila automáticamente. Si no, click en **Recompile**.
5. Completa los datos del grupo al inicio del documento (título del
   proyecto, integrantes, dataset, docente y fecha) y desarrolla cada
   sección donde dice `[Desarrollen aquí]`.

> Si subes solo el `.tex` sin el `.png`, la portada no va a compilar
> porque no encuentra el logo. Asegúrate de subir ambos archivos juntos.

**Alternativa dentro de Overleaf:** en lugar de subir archivos sueltos,
puedes usar **New Project → Import from GitHub** y seleccionar la carpeta
de la evaluación directamente desde este repositorio (requiere vincular tu
cuenta de GitHub a Overleaf una vez).

### Opción B — Compilar localmente

Si tienes una distribución de LaTeX instalada (TeX Live, MiKTeX, MacTeX):

```bash
cd sumativa-1-analisis-exploratorio-inferencial
pdflatex plantilla.tex
pdflatex plantilla.tex   # segunda pasada: arma el índice correctamente
```

El PDF resultante (`plantilla.pdf`) queda en la misma carpeta.

## Requisitos técnicos

Las plantillas usan paquetes estándar, disponibles por defecto en Overleaf
y en cualquier distribución de TeX Live reciente:

`geometry`, `graphicx`, `xcolor`, `titlesec`, `fancyhdr`, `tcolorbox`,
`hyperref`, `booktabs`, `enumitem`, `array`.

No requieren `babel` para compilar (las etiquetas en español —Índice,
Figura, Tabla, Bibliografía— están definidas manualmente), pero si tu
instalación incluye el paquete de idioma español, puedes activarlo
descomentando la línea correspondiente al inicio de cada `.tex` para
mejorar la silabación.

## Edición y personalización

Cada plantilla incluye, al inicio del archivo, dos comandos pensados para
que el docente los ajuste sin tocar el resto del documento:

- `\guia{...}` — descripción breve bajo cada título, con el puntaje de la
  rúbrica entre paréntesis.
- `\resp` — marca discreta `[Desarrollen aquí]` que indica al estudiante
  dónde completar; se puede borrar al entregar.

Los datos de portada (título del proyecto, integrantes, dataset, docente,
fecha, repositorio) se completan editando las líneas `\newcommand{\proy...}`
cerca del inicio del archivo.
