# Comparo Web (comparoapp.com)

Sitio web del producto **Comparo**: una app de iOS, en español, que ayuda a quien busca empleo a decidir si una oferta supera a su trabajo actual, después de salario, bonos, beneficios e impuestos dominicanos (ISR + TSS). Muestra una comparación por categoría, la diferencia de ingreso neto y una proyección sencilla de ahorro a 12 meses.

Este proyecto es **solo el sitio web**. El código de la app vive en otro repositorio (privado) y no debe copiarse ni mencionarse aquí.

Responsable: Rogelio (program manager). No es desarrollador web ni de iOS: explica en lenguaje sencillo lo que no sea obvio.

## Idioma (importante)

- El sitio, la documentación, los commits y la conversación van **en español**, con acentos, puntuación y gramática correctos.
- El sitio de la v1 es **solo en español** (la app también). El inglés queda para una versión posterior.
- Código: identificadores (clases CSS, variables, nombres de archivo del código) en inglés o español de forma consistente; comentarios en español.

## Qué es Comparo (para escribir sin inventar)

**Hechos confirmados de la app v1:**
- Compara el **empleo actual** (azul) contra **una oferta** (naranja), una comparación a la vez.
- Calcula el neto después de **ISR y TSS** dominicanos (tablas 2026 y 2027), con bonos (con frecuencia anual, mensual o quincenal y opción de «Paga ISR»), regalía pascual (Salario 13) y beneficios.
- Beneficios: monto fijo, tope de reembolso, porcentaje del salario y no monetarios (estos se muestran lado a lado, pero nunca se suman al dinero). En los seguros de salud, dental, visión y vida se puede anotar lo que paga el empleado al mes.
- Moneda DOP o USD, con tasa de cambio **manual**.
- Resultados mensuales y anuales, veredicto, y **proyección de ahorro a 12 meses** con gráfica.
- Comparaciones guardadas, exportación a CSV y «Borrar todos mis datos».
- Funciona **sin conexión**, sin cuentas, sin analítica y sin rastreo. Todo se guarda **solo en el iPhone**.
- Solo **iPhone**, iOS 17 o superior, en **español**.
- Es una app **de pago**, con precio bajo, sin plan gratuito, sin compras dentro de la app y sin anuncios. **El precio aún no es definitivo**: por ahora el sitio indica «Precio previsto: 4.99 USD» (decisión de Rogelio, 2026-11-18). Siempre con la palabra «previsto» y nunca en la política de privacidad.
- Las cifras son **estimaciones** (una retención estimada, no la declaración anual de impuestos). No es asesoría fiscal, legal ni financiera. Para empleos sin retenciones locales (contratista o empleador en el exterior) la app no calcula impuestos y recomienda consultar a un contador.

**Lo que NO se debe afirmar (aún):**
- Que la app **ya está en la App Store**: todavía no está publicada. Sin enlace ni insignia hasta que exista (usa un aviso honesto de «Próximamente»).
- **iCloud, sincronización entre dispositivos, versión para iPad, inglés, impuestos de EE. UU., tasas de cambio en vivo, planificación de deudas, cuentas de usuario**: todo eso queda fuera de la v1. No lo prometas ni lo insinúes con fechas. (iCloud se retiró de la v1 el 2026-11-16; la política de privacidad actual ya no lo menciona.)
- Que los cálculos están «validados por un contador» o son «exactos»: solo se validó verbalmente una regla (la de los bonos) con un contador. Habla de estimaciones.
- Cifras de ahorro o testimonios inventados. Los números de las capturas son **datos de ejemplo**.
- Un precio distinto del previsto, fecha de lanzamiento (la meta interna es febrero de 2027, pero es una meta y no una promesa pública) o cifras de descargas.

Si dudas de lo que hace Comparo, **pregúntale a Rogelio**; no lo supongas.

## Páginas del sitio

Tres páginas obligatorias para la v1 (más lo que Rogelio apruebe después de ver el plan):

1. **Inicio:** qué es Comparo, para quién es (quien busca empleo en República Dominicana y compara una oferta), cómo funciona en pocos pasos, capturas y el llamado a la acción («Próximamente en la App Store» hasta que haya enlace).
2. **Política de privacidad:** el texto debe ser **idéntico al de la política dentro de la app** (ver más abajo).
3. **Soporte:** correo **soporte@comparoapp.com** y preguntas frecuentes (los cálculos son orientativos, qué impuestos cubre, cómo borrar los datos, cómo exportar a CSV, que la app no necesita conexión ni cuenta, consultar a un contador). No inventes preguntas sobre funciones que la app no tiene.

Ideas por decidir con Rogelio (no las construyas sin su plan aprobado): página de «Términos de uso», página 404, enlace desde la app (Ajustes → «Ver en la web»), etiquetas Open Graph para compartir.

### La política de privacidad (importante)

- La política vive en dos lugares que **deben coincidir palabra por palabra**: la pantalla dentro de la app y la web. En la app, una prueba automática vigila que no se separen. Si cambias el texto aquí, avisa a Rogelio para que se cambie también en la app.
- El texto vigente está en `referencia/politica-de-privacidad-actual.html`. Puedes rediseñarlo con la marca, pero **no cambies las palabras**. Sus secciones: resumen, qué información guarda la app, dónde se guarda, qué no hacemos, exportar a CSV, copias de seguridad, cómo borrar los datos, cambios a la política y contacto.
- **Fecha de vigencia:** «20 de noviembre de 2027», definitiva según Rogelio (2026-11-20). Debe ser idéntica en la app; si cambia, avisar para actualizar ambos lados.
- La **URL pública** de la política (por ejemplo `https://comparoapp.com/privacidad`) se pondrá luego en la app y en App Store Connect. Decide con Rogelio una ruta estable y no la cambies después.
- La política de la web no debe contradecir lo que hace el sitio (ver «Privacidad del sitio»).

## Tecnología

- **HTML y CSS puros**, sin frameworks y sin paso de compilación, salvo que Rogelio lo pida. JavaScript solo si hace falta, mínimo y sin dependencias externas.
- **Hosting:** Cloudflare Pages, conectado al repositorio **`comparo-web`** en GitHub (público, solo para el sitio: aquí no va código de la app). Cada `git push` a `main` publica el sitio. **Solo se publica la carpeta `public/`** (directorio de salida en Cloudflare): `assets/`, `referencia/`, `CLAUDE.md` y `BRAND.md` son material de trabajo y no deben quedar en la web. Dominio: **comparoapp.com**.
- Mobile first, accesible (WCAG AA), rápido y con muy poco peso.
- Metadatos correctos: `lang="es"`, título y descripción por página, `viewport`, favicon (a partir de `assets/icono/`), `theme-color`.
- Sin secretos, claves ni tokens en el repositorio.

### Privacidad del sitio

El sitio debe ser **coherente con la política de la app**: sin cookies, sin rastreo, sin analítica de terceros, sin píxeles, sin formularios que recojan datos, sin incrustar contenido de terceros.
- **Nada de Google Fonts ni CDN externos:** las fuentes (Nunito) se alojan en el propio sitio (`assets/fuentes/`).
- Tampoco scripts, mapas, vídeos ni iconos cargados desde otro dominio.
- No actives la analítica web de Cloudflare ni ninguna otra. Si se quisiera medir visitas, se decide aparte con Rogelio y se actualiza la política.
- Los enlaces de salida (por ejemplo la App Store) son enlaces normales, sin parámetros de seguimiento.
- Soporte es un enlace `mailto:soporte@comparoapp.com`, no un formulario.

## Marca

Todo el detalle está en **`BRAND.md`** (léelo antes de diseñar). Lo esencial:
- **Azul = empleo actual; naranja = oferta.** Siempre, y nunca distinguirlos solo por color: acompañar con la etiqueta «Actual» / «Oferta». El azul y el naranja de marca son *rellenos*; para texto usa azul 700 / naranja 700.
- **Tipografía:** Nunito (Black/ExtraBold/Bold) para marca, títulos y botones; fuentes del sistema para el cuerpo. Alojadas localmente.
- **Colores semánticos** con modo claro y oscuro (`assets/comparo-tokens.json`). El verde «mejor» solo señala la oferta ganadora.
- **Eslogan:** «Compara ofertas. Decide con claridad.»
- **Tono:** amable, claro, optimista, frases cortas, dinero mostrado sin adornos («RD$ 17,830 más al mes»). Se celebra la mejor oferta y nunca se avergüenza a la otra («Menos favorable», no «Peor»). Nada de promesas de ahorro ni de «asesoría».
- **La proyección es de 12 meses**, no de 5 años; los mockups antiguos que dicen «Oferta A / Oferta B» o «5 años» están obsoletos.

## Materiales incluidos

```
CLAUDE.md                      Este archivo
BRAND.md                       Guía de marca (versión web, en español)
assets/
  comparo-tokens.json          Colores, tipografía, radios y espaciado
  logo/                        Marca de texto y versiones (SVG y PNG)
  icono/                       Ícono de la app (PNG y SVG)
  fuentes/                     Nunito Bold, ExtraBold, Black + licencia OFL
  capturas-app-store/          6 capturas definitivas de App Store (1320×2868, es)
  capturas-reales/             25 capturas reales de la app + LEEME.md
referencia/
  politica-de-privacidad-actual.html   Texto vigente de la política (no cambiar las palabras)
```

Las capturas tienen un tamaño grande (1320×2868): en la web usa copias redimensionadas y comprimidas (WebP o PNG optimizado) con `width`/`height` y `loading="lazy"`.

## Cómo trabajar conmigo (importante)

Por defecto, **primero el plan**.
1. Antes de crear páginas, cambiar la estructura o añadir archivos o carpetas: muestra un **plan corto**, explica por qué y **espera mi aprobación**.
2. Lo pequeño (textos, ajustes de estilo, corregir un error): hazlo y dime qué cambió.
3. Código completo y funcional, nunca pseudocódigo. Explica en lenguaje sencillo lo que no sea obvio.
4. **Nunca ejecutes `git push`** y nunca hagas commit sin preguntarme. Sugiere un mensaje de commit (en español) y espera. Sin la línea `Co-Authored-By`.
5. Si algo del producto, del texto legal o de la marca es ambiguo o puede estar desactualizado, **dilo** en lugar de adivinar. La política de privacidad tiene valor legal.
6. Si algo de este proyecto contradice la guía de marca o la política de la app, avísame en vez de desviarte en silencio.

## Pendientes conocidos (no inventes valores: confírmalos conmigo)

- URL final de la política y de soporte.
- Precio definitivo y enlace de la App Store (la app aún no está publicada; falta inscribirse en el Apple Developer Program).
- Si habrá página de «Términos de uso».
- Revisión manual de la app por Rogelio y un par de validaciones fiscales con un contador (por eso: «estimaciones»).
