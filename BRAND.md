# Guía de marca de Comparo (versión para el sitio web)

Actualizada el 2026-11-18 a partir de `docs/diseno/BRAND.md` del repositorio de la app (hecha con Claude Design). Cambia respecto al original: está en español, refleja las decisiones tomadas después (A/B → «Actual»/«Oferta», proyección de 12 meses, eslogan elegido, capturas nuevas) y añade una sección para el sitio web. Los valores legibles por máquina están en `assets/comparo-tokens.json`.

## Personalidad

Amable y optimista, como un entrenador que ayuda. Claro, cálido, nunca sermoneador. Español sencillo, frases cortas y el dinero mostrado sin adornos («RD$ 17,830 más al mes»). Se celebra la mejor oferta y nunca se avergüenza a la otra («Menos favorable», no «Peor»).

## Idea central

Dos ofertas se convierten en una decisión clara.

- **Azul Comparo** = el empleo **actual**.
- **Naranja Amanecer** = la **oferta** nueva.
- **Azul Decisión (navy)** = donde se encuentran: el cruce en el ícono, el panel de resultado en la app y el texto principal.

En la app el azul es siempre «Actual» y el naranja siempre «Oferta» (tarjetas, barras, leyendas). El sitio debe respetar el mismo código. (Los archivos originales del kit decían «Oferta A / Oferta B»; la v1 de la app usa «Actual» y «Oferta».)

## Eslogan

**«Compara ofertas. Decide con claridad.»** Es el eslogan elegido. Las otras opciones que se barajaron (descartadas): «Dos ofertas, una decisión clara», «Elige la oferta que más te conviene», «Tu próximo trabajo, bien comparado».

## Ícono de la app

Archivos en `assets/icono/`.

- Dos hojas redondeadas inclinadas −9° (azul, atrás) y +9° (naranja, adelante). El cruce es azul Decisión. Encima, una «C» blanca gruesa y redondeada, abierta hacia la derecha.
- Sin líneas de documento en el ícono (ensucian los tamaños pequeños). Pueden aparecer en ilustraciones grandes.
- Variantes: clara (fondo Cloud), oscura (fondo #10142A, hojas más brillantes) y tintada (grises sobre negro).

| Variante | Fondo | Hoja actual | Hoja oferta | Cruce | C |
|---|---|---|---|---|---|
| Clara | #F3F6FB | #3A6DF0 | #FF9A3C | #1B2559 | #FFFFFF |
| Oscura | #10142A | #6E93FF | #FFB066 | #2C3A86 | #FFFFFF |
| Tintada | #000000 | #6B6B6B | #A8A8A8 | #3A3A3A | #FFFFFF |

## Logo

Archivos en `assets/logo/` (SVG con trazos convertidos, no necesita la fuente; y PNG).

- Marca de texto: «comparo» en minúsculas, Nunito Black, espaciado −3 %.
- Versiones: horizontal (ícono + texto), horizontal sobre navy (texto blanco) y apilada (ícono sobre texto).
- Sobre fondos claros, texto navy; sobre navy o fotos, blanco.
- Espacio libre alrededor: al menos la mitad del ancho del ícono. No recolorear, estirar, ponerle sombras al texto ni colocar el ícono sobre fondos recargados.

## Color

### Rampas de marca (fijas)

| Rampa | Pasos |
|---|---|
| Azul | 50 #EDF2FF · 100 #D6E2FF · 300 #8FAAF5 · **500 #3A6DF0** · 700 #2449B8 |
| Naranja | 50 #FFF3E6 · 100 #FFE0BF · 300 #FFC08A · **400 #FF9A3C** · 700 #B4560A |
| Navy | 100 #E1E7F2 · 300 #A9B3CC · 500 #5B6785 · 700 #34407A · **900 #1B2559** |
| Cloud | 50 #F3F6FB |

### Colores semánticos (claro / oscuro)

En la app existen como colores con nombre. En la web, defínelos como variables CSS (`--color-...`) con `prefers-color-scheme` para el modo oscuro. Los valores oscuros distintos del azul, el naranja y el verde de marca son propuestas.

| Nombre | Claro | Oscuro | Uso |
|---|---|---|---|
| brandBlue | #3A6DF0 | #6E93FF | Relleno del empleo actual, gráficas |
| brandOrange | #FF9A3C | #FFB066 | Relleno de la oferta |
| brandNavy | #1B2559 | #2C3A86 | Paneles de resultado y de decisión |
| blueText | #2449B8 | #8FAAF5 | Enlaces, botones, relleno del botón principal |
| orangeText | #B4560A | #FFC08A | Texto naranja |
| background | #F3F6FB | #0E1430 | Fondo de página |
| surface | #FFFFFF | #182046 | Tarjetas, tablas |
| surfaceRaised | #FFFFFF | #222C5A | Hojas y elementos elevados |
| separator | #E1E7F2 | #2C3A86 | Divisores y bordes |
| textPrimary | #1B2559 | #F3F6FB | Texto principal |
| textSecondary | #5B6785 | #A9B3CC | Texto secundario |
| better / betterText | #12A26B / #0B7A50 | #3DD598 | «Mejor oferta», valores ganadores |
| warning / warningText | #F2B227 / #8A6100 | #F2B227 / #F2C14E | «Atención» |
| worse / worseText | #E5484D / #B42328 | #FF6B6F / #FF8A8D | «Menos favorable» |

### Reglas

- Azul 500 y naranja 400 son **rellenos**, no texto. Sobre blanco, el texto usa azul 700 o naranja 700 (cumplen 4.5:1 de WCAG AA).
- Equilibrio aproximado en una pantalla: Cloud 55 %, blanco 20 %, azul 12 %, naranja 8 %, navy 5 %.
- El verde de «mejor oferta» solo señala «esta gana»; nunca es decoración.
- **Nunca distinguir lo actual y la oferta solo por color:** siempre junto a la etiqueta «Actual» / «Oferta».

## Tipografía

Archivos en `assets/fuentes/` (Nunito Bold, ExtraBold y Black; licencia SIL Open Font, gratuita y redistribuible; el texto de la licencia viene en `OFL.txt`).

| Estilo | Fuente | Tamaño/interlínea | Ejemplo |
|---|---|---|---|
| Display | Nunito Black | 34/41 | «Mejor oferta», cifras grandes |
| Título | Nunito ExtraBold | 28/34 | «Comparación» |
| Título de tarjeta | Nunito Black | 18 | «Actual», «Oferta» |
| Botón | Nunito ExtraBold | 18 | «Ver proyección» |
| Encabezado | SF Pro Semibold | 17/22 | «Salario neto mensual» |
| Cuerpo | SF Pro Regular | 17/22 | «La oferta te deja más dinero cada mes.» |
| Pie | SF Pro Regular | 13/18 | «Incluye ISR y TSS.» |

Cifras tabulares (`font-variant-numeric: tabular-nums`) para todo el dinero en tablas.

## Forma y espaciado

- Radio de esquina: chip 10, control 12, botón 16, tarjeta 18, panel 22.
- Margen de pantalla 16; separación entre elementos 8 (apretada) / 14 (normal); entre secciones 24.
- Áreas táctiles de al menos 44 px; botón principal de 54 px de alto.
- Sombras solo en elementos flotantes: navy suave con baja opacidad.

## Capturas de la app

- `assets/capturas-app-store/`: las **seis capturas definitivas de App Store** (1320×2868, español, proyección de 12 meses), hechas con Claude Design a partir de capturas reales: «Compara ofertas», «Empleo actual vs. oferta», «Cada peso, lado a lado», «La foto del año», «Ahorro a 12 meses» y «Tus datos son tuyos».
- `assets/capturas-reales/`: 25 capturas reales de la app (iPhone, 1320×2868) con un recorrido completo (`LEEME.md` explica los datos de ejemplo). Los números son datos de ejemplo, no un cálculo real de nadie. Sirven para mostrar la app en la web.
- La proyección de la v1 es de **12 meses**, no de 5 años. Cualquier mención a «5 años» en materiales viejos está obsoleta.

## Pantalla clave: Comparación (resultado)

1. Dos tarjetas lado a lado: «Actual» (azul) y «Oferta» (naranja). La ganadora lleva un borde de 2 px `better` y una insignia «Mejor» con una marca de verificación.
2. Panel de resultado (navy, radio 22): «La oferta te deja» + «RD$ X más al mes» en estilo Display, con dos barras (azul y naranja).
3. Selector Mensual / Anual.
4. Tabla de desglose: salario bruto, ISR, TSS, beneficios, neto (en negrita, con una línea navy arriba). El mejor valor de cada fila va en `betterText` y seminegrita.
5. Botón principal para ver la proyección de ahorro a 12 meses.

## Pantalla de apertura (splash)

Solo aplica a la app: hoja azul desde la izquierda y naranja desde la derecha, cruce navy, la «C» blanca cae con un golpe, y aparecen el texto «comparo» y el eslogan. Si el sitio quiere una animación de entrada, que sea breve y respete `prefers-reduced-motion` (mostrar el estado final sin movimiento).

---

## Sitio web (comparoapp.com)

Reglas específicas para la web; el resto de esta guía aplica igual.

**Tipografía en la web.** Nunito para títulos, botones y marca; para el cuerpo, la pila del sistema (`system-ui, -apple-system, "Segoe UI", Roboto, sans-serif`), ya que SF Pro no se puede incrustar fuera de Apple. **Las fuentes se alojan en el propio sitio** (los `.ttf` de `assets/fuentes/`, o `.woff2` si se convierten): nada de Google Fonts ni otras CDN, porque el sitio no debe hacer llamadas a terceros (ver «Privacidad» en `CLAUDE.md`).

**Tema claro y oscuro.** Variables CSS con los valores semánticos de arriba y `prefers-color-scheme: dark`. `color-scheme: light dark`.

**Accesibilidad (WCAG AA).** Contraste mínimo 4.5:1 para texto; foco visible; áreas táctiles de 44 px; texto que se agranda hasta 200 % sin romper el diseño; `alt` en las capturas (describe lo que muestran); `prefers-reduced-motion`; un solo `h1` por página.

**Capturas en la web.** Muestra capturas reales o las de App Store. No uses mockups con «Oferta A / Oferta B» ni «5 años». Las cifras de ejemplo deben decir que son un ejemplo.

**Insignia de la App Store.** Aún no hay enlace (la app no está publicada). Hasta entonces, un aviso de «Próximamente» honesto. Cuando exista, se usa la insignia oficial de Apple sin modificarla.

**Tono del texto.** El de la sección «Personalidad». Nada de promesas de ahorro, de «cálculos exactos» ni de «asesoría»: las cifras son estimaciones.
