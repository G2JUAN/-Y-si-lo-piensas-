# ¿Y si lo piensas?

## README --- documentación funcional y técnica

**Tipo de proyecto:** sitio web educativo de reflexión ética.\
**Idioma:** español.\
**Tecnologías identificadas:** HTML, CSS y JavaScript del lado del
cliente.\
**Publicación conocida:** GitHub Pages.\
**URL conocida:** https://g2juan.github.io/-Y-si-lo-piensas-/

> Esta documentación se basa en las páginas y fragmentos del proyecto
> disponibles durante su desarrollo. No se ha inspeccionado aquí una
> copia íntegra y actualizada de todos los archivos del repositorio. Los
> puntos sobre los que no existe evidencia suficiente se señalan como
> aspectos por verificar.

------------------------------------------------------------------------

# 1. Propósito del proyecto

**¿Y si lo piensas?** es un sitio educativo orientado a presentar temas
de reflexión ética y promover el pensamiento crítico. Busca que los
visitantes no solo lean información, sino que también analicen
argumentos, consideren consecuencias, expresen una postura propia y
respondan actividades relacionadas con los contenidos.

Sus objetivos generales son:

-   Presentar temas de interés ético y social.
-   Explicar conceptos y ofrecer perspectivas para analizar cada tema.
-   Estimular la reflexión y la argumentación personal.
-   Proponer cuestionarios con diferentes formas de respuesta.
-   Organizar la navegación entre temas, evaluaciones y páginas
    informativas.
-   Mantener un historial de cambios del sitio.
-   Documentar las herramientas y la organización técnica del proyecto.

El sitio es un recurso educativo. No debe considerarse sustituto de
asesoramiento médico, psicológico, jurídico o profesional. Los
contenidos sensibles deben tratarse con respeto, fuentes confiables y
lenguaje apropiado para el público.

# 2. Secciones y navegación

La barra de navegación compartida en la plantilla contiene los
siguientes destinos:

  ------------------------------------------------------------------------------------
  Sección                 Ruta de la plantilla                 Función
  ----------------------- ------------------------------------ -----------------------
  Inicio                  `/51694/site/home.html`              Punto de entrada al
                                                               sitio.

  Publicaciones - Temas   `/51694/site/temas.html`             Acceso a temas y
                                                               contenidos.

  Cuestionarios           `/51694/site/cuestionarios.html`     Acceso a actividades.

  Actualizaciones         `/51694/site/actualizaciones.html`   Historial de versiones
                                                               y cambios.

  Desarrollo Web          `/51694/site/desarrollo.html`        Información del
                                                               proyecto y de su
                                                               construcción.

  Log Out                 `/51694/site/index.html`             Enlace de salida o
                                                               regreso al acceso; el
                                                               comportamiento real
                                                               depende del código de
                                                               autenticación.
  ------------------------------------------------------------------------------------

**Importante:** las rutas anteriores proceden de la plantilla compartida
y deben compararse con la estructura real del repositorio. En GitHub
Pages, una web puede publicarse dentro de una subruta correspondiente al
repositorio. Por eso, las rutas que comienzan con `/` pueden apuntar a
la raíz del dominio y causar errores 404. Las rutas relativas ---por
ejemplo `temas.html`, `./temas.html` o `../temas.html`--- dependen de la
ubicación de cada archivo y deben elegirse según la estructura real.

## 2.1 Inicio

La página de inicio orienta al visitante y facilita el acceso a las
demás secciones. Debe mantener enlaces coherentes con la barra de
navegación y con la estructura del repositorio.

## 2.2 Publicaciones y temas

Se han trabajado contenidos como:

-   Sustancias psicoactivas.
-   Trascendencia humana.
-   Dictadura del dinero y materialismo.
-   Relaciones sexuales casuales.
-   Relaciones abiertas y poliamor.
-   El acto sexual como entrega amorosa.

Esta lista recoge temas trabajados durante el desarrollo; no confirma
que todos estén publicados en la versión actual.

Una estructura recomendable para cada tema es: introducción, desarrollo
del enfoque ético, argumentos o consecuencias, reflexión y enlace a un
cuestionario relacionado. Cuando se añade un tema, también deben
revisarse los enlaces desde el índice y las rutas de imágenes y
recursos.

## 2.3 Cuestionarios

El proyecto contempla tres modalidades:

### Opción múltiple

El usuario selecciona una opción entre varias. En el HTML revisado, una
pregunta puede contener un atributo como `data-correct="b"` y las
opciones se construyen con `input type="radio"`. El valor de la opción
elegida debe coincidir con el valor declarado como correcto. Puede
usarse `data-explanation` para asociar una explicación.

Al editar una pregunta hay que actualizar el enunciado, las opciones,
sus valores, la respuesta correcta y la explicación. El JavaScript debe
leer esos datos, comprobar la selección y calcular el resultado.

### Respuestas abiertas

El usuario redacta una respuesta con sus propias palabras. La plantilla
revisada usa `maxlength="2000"` para limitar cada campo a 2.000
caracteres y un contador visual. El resultado puede mostrar una revisión
de lo escrito, pero no asigna una nota automática a la respuesta abierta
porque requiere valoración personal.

Cada campo necesita un `id` único. Si un contador o una función de
revisión hace referencia a ese identificador, también debe actualizarse
cuando se duplica una pregunta.

### Mixto

Combina preguntas calificables de opción múltiple con preguntas
abiertas. La plantilla revisada contempla una nota automática para las
preguntas de selección múltiple y una revisión de las respuestas
escritas sin calificarlas automáticamente. Debe comprobarse que la
lógica de puntuación no cuente las respuestas abiertas como preguntas
calificables.

Una fórmula habitual para el porcentaje es:

**Porcentaje = (respuestas correctas / preguntas calificables) × 100**

El código debe manejar el caso en que no existan preguntas calificables
y definir qué ocurre con las preguntas sin respuesta.

## 2.4 Actualizaciones

La página `actualizaciones.html` presenta versiones mediante tarjetas
con secciones de cambios implementados, arreglados y quitados. En el
contenido revisado, la versión 1.0.0 tiene fecha 25/10/2026 y registra,
entre otros cambios, modalidades de cuestionario, sistema de acceso, un
tema adicional, mejoras de distribución y correcciones de redirecciones.
También aparece una tarjeta de ejemplo para la versión 0.9.0 con fecha
23/10/2026.

Antes de publicar el historial, debe comprobarse que cada novedad esté
implementada realmente. Una descripción en el historial no ejecuta una
función: solo documenta un cambio.

## 2.5 Desarrollo Web

La página `desarrollo.html` contiene campos para editor de código,
programador, hosting, tecnologías, idea principal y una lista de
componentes o tareas. En el archivo revisado, algunos textos usan
`contenteditable="true"` para poder editarse en pantalla.

`contenteditable` no guarda automáticamente el archivo fuente. Los
cambios pueden perderse al recargar la página. Para conservarlos hay que
editar el HTML y volver a publicarlo, salvo que se haya programado
expresamente una función de persistencia.

# 3. Tecnologías y arquitectura

## 3.1 HTML

HTML define la estructura y el contenido de la página. En los archivos
revisados aparecen elementos como:

-   `<!DOCTYPE html>`: declara el documento HTML.
-   `<html lang="es">`: indica el idioma principal.
-   `<head>`: contiene metadatos, título, icono y estilos.
-   `<meta charset="UTF-8">`: permite mostrar correctamente tildes y
    caracteres especiales.
-   `<meta name="viewport" content="width=device-width, initial-scale=1.0">`:
    facilita la adaptación a móviles.
-   `<title>`: establece el título de la pestaña.
-   `<link rel="icon">`: define el icono del sitio.
-   `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` y
    `<footer>`: organizan las áreas de contenido.
-   `<a>`: crea enlaces.
-   `<form>`, `<input>`, `<textarea>` y `<button>`: permiten construir
    formularios y controles.
-   `class`: agrupa elementos para aplicar estilos o seleccionarlos
    desde JavaScript.
-   `id`: identifica un elemento concreto; debe ser único en el
    documento.
-   Atributos ARIA, como `aria-label` y `aria-labelledby`, pueden
    mejorar la accesibilidad.

## 3.2 CSS

CSS controla colores, tipografía, tamaños, márgenes, disposición,
bordes, sombras y animaciones. En las páginas revisadas, buena parte del
CSS se encuentra dentro de una etiqueta `<style>` en el propio HTML.
Esto permite que cada archivo sea relativamente autónomo, aunque puede
duplicar estilos.

Si el sitio crece, puede ser útil mover estilos compartidos a una hoja
común, como `css/style.css`, pero se deben actualizar las rutas y probar
todas las páginas después del cambio.

### Variables CSS

El uso de `:root` permite definir colores y otras medidas reutilizables:

``` css
:root {
  --fondo: #edf5fc;
  --texto: #17212d;
  --secundario: #5e6b7b;
  --azul: #2777c7;
  --azul-claro: #dceeff;
}
```

Los colores exactos varían por página. Las variables ayudan a mantener
una paleta consistente y a cambiarla desde un solo lugar.

### Diseño responsive

Las reglas `@media` adaptan la distribución según el ancho de pantalla.
En las plantillas revisadas aparecen puntos de ruptura alrededor de
`1050px` para la navegación y `560px` para ciertos formularios y
botones. Es necesario probar en escritorio, tableta y móvil, incluyendo
ventanas estrechas.

### Efecto Liquid Glass

La barra superior emplea un fondo translúcido oscuro, bordes claros,
esquinas redondeadas, sombras y propiedades como
`backdrop-filter: blur(...)`. El resultado es un efecto visual de
cristal. Debe mantenerse un fondo legible incluso en navegadores que no
apliquen el desenfoque.

### Animaciones y accesibilidad

Las animaciones deben ser discretas y no dificultar la lectura. Una
regla `@media (prefers-reduced-motion: reduce)` permite reducir el
movimiento para usuarios que lo solicitan. También se recomienda
contraste suficiente, foco visible, botones con nombres claros y
navegación mediante teclado.

## 3.3 JavaScript

JavaScript añade comportamiento interactivo. En las plantillas revisadas
se utiliza o se contempla para:

-   Abrir y cerrar el menú móvil.
-   Cerrar el menú con `Escape` o al elegir un enlace.
-   Calcular resultados de selección múltiple.
-   Mostrar explicaciones y resultados.
-   Actualizar contadores de caracteres.
-   Revisar las respuestas abiertas.
-   Añadir o retirar elementos de una lista editable.

Una clase CSS o un atributo HTML no implementan por sí solos una acción:
debe existir código JavaScript que conecte los controles con ese
comportamiento. El script debe ejecutarse cuando los elementos HTML ya
estén disponibles y debe buscar los identificadores correctos.

Ejemplo conceptual de una pregunta:

``` html
<section class="question"
         data-correct="b"
         data-explanation="Evalúa las opciones y sus consecuencias.">
  <h2>¿Qué implica decidir responsablemente?</h2>
  <label>
    <input type="radio" name="q1" value="a">
    Actuar sin pensar.
  </label>
  <label>
    <input type="radio" name="q1" value="b">
    Evaluar las opciones.
  </label>
</section>
```

Este fragmento solo representa la estructura de la pregunta; necesita
JavaScript adicional para calificarla.

# 4. Barra de navegación

La barra común contiene el logo, los enlaces y un botón de menú para
pantallas pequeñas. En escritorio, los enlaces se muestran en una fila;
en móvil, pueden aparecer dentro de un menú desplegable. La clase
`active`, si está definida en CSS, permite resaltar la página actual.

Para cambiar un destino, edita el `href` del enlace y comprueba la ruta
desde cada página. Si el logo usa `images/logo1.png` y el icono de
pestaña usa `images/logo2.png`, esos archivos deben existir en las rutas
indicadas.

Si cada página contiene una copia de la barra, los cambios deben
replicarse en todas las páginas. Para evitar diferencias, se puede
mantener una plantilla común, pero un sitio estático no incluye
automáticamente un sistema de componentes compartidos: hay que
implementarlo o utilizar una herramienta de construcción.

# 5. Inicio de sesión y seguridad

El historial declara que se incorporó un sistema de inicio de sesión.
Sin el código completo no es posible confirmar si valida usuarios en un
servidor, utiliza almacenamiento del navegador o es una demostración del
lado del cliente.

La diferencia es importante:

-   HTML construye el formulario.
-   CSS controla su aspecto.
-   JavaScript del navegador puede validar campos o simular un acceso.
-   La autenticación segura requiere validar identidad y permisos en un
    servidor o proveedor adecuado.

Si las credenciales o reglas secretas están incluidas en JavaScript
público, pueden inspeccionarse. Ocultar enlaces o redirigir páginas no
protege por sí solo los archivos estáticos. Si el sitio solo usa HTML,
CSS y JavaScript sin backend, no debe tratarse como un sistema seguro
para información confidencial.

El enlace llamado `Log Out` tampoco garantiza que se cierre una sesión
real; se debe revisar el código que gestiona la autenticación y la
salida.

Recomendaciones:

-   No guardar contraseñas en texto plano dentro del HTML o JavaScript.
-   No publicar claves privadas, tokens secretos ni credenciales.
-   No recopilar datos personales innecesarios.
-   Si se guardan respuestas, informar qué se almacena, para qué,
    durante cuánto tiempo y quién puede acceder.
-   Si se requiere acceso seguro o almacenamiento centralizado, utilizar
    un backend o proveedor de autenticación apropiado.

# 6. Publicación en GitHub Pages

GitHub Pages permite publicar sitios estáticos desde un repositorio. Los
archivos HTML, CSS, JavaScript, imágenes y fuentes se envían al
navegador del visitante. No debe suponerse que exista un servidor de
backend solo por usar GitHub Pages.

URL conocida del proyecto:

`https://g2juan.github.io/-Y-si-lo-piensas-/`

Una estructura posible ---solo ilustrativa, debe compararse con el
repositorio real--- sería:

``` text
-Y-si-lo-piensas-/
├── index.html
├── home.html
├── temas.html
├── cuestionarios.html
├── actualizaciones.html
├── desarrollo.html
├── css/
├── js/
├── images/
└── fonts/
```

### Rutas relativas y absolutas

-   `href="temas.html"`: busca el archivo relativo a la página actual.
-   `href="./temas.html"`: apunta a un archivo en la carpeta actual.
-   `href="../temas.html"`: sube un nivel de carpeta.
-   `href="/temas.html"`: busca desde la raíz del dominio.

En una publicación bajo `https://usuario.github.io/nombre-repositorio/`,
una ruta que comienza por `/` puede buscar el archivo fuera de la
carpeta del proyecto. Por eso es importante comprobar la ubicación real
de los archivos antes de cambiar las rutas.

### Proceso de publicación

1.  Editar el archivo en el editor.
2.  Guardar los cambios.
3.  Probar la página localmente.
4.  Revisar los enlaces y la consola del navegador.
5.  Subir los cambios al repositorio.
6.  Esperar a que termine el despliegue de GitHub Pages.
7.  Probar la URL pública, incluidas imágenes, estilos, cuestionarios y
    redirecciones.

Si una página abre directamente pero falla al llegar desde otra, revisa
especialmente los `href`, las rutas relativas, las redirecciones y la
URL base.

# 7. Mantenimiento del contenido

## Añadir un tema

1.  Crear o duplicar una página siguiendo el diseño existente.
2.  Cambiar título, introducción, desarrollo y reflexión.
3.  Crear o actualizar el cuestionario relacionado.
4.  Añadir un enlace desde el índice de temas.
5.  Revisar imágenes, estilos, scripts y rutas.
6.  Probar todo el recorrido desde la página de inicio publicada.

## Añadir una pregunta de opción múltiple

1.  Copiar una pregunta existente.
2.  Cambiar número y enunciado.
3.  Modificar las opciones y sus valores.
4.  Asegurar que las opciones de una misma pregunta compartan `name`.
5.  Usar un `name` diferente para cada pregunta.
6.  Establecer `data-correct` con el valor de la opción correcta.
7.  Actualizar `data-explanation` si se utiliza.
8.  Confirmar que el JavaScript incluya la nueva pregunta al calcular la
    nota.

## Añadir una pregunta abierta

1.  Copiar una sección de pregunta.
2.  Cambiar el enunciado.
3.  Asignar un `id` único al `textarea`.
4.  Revisar `maxlength`.
5.  Actualizar la referencia del contador.
6.  Verificar que el resultado final incluya la respuesta.

## Actualizar el historial

Cada versión debería indicar número, fecha, resumen y listas de cambios
implementados, corregidos o retirados. No se deben registrar como
terminadas funciones que todavía no están disponibles en la versión
publicada.

## Actualizar la barra

1.  Crear la nueva página.
2.  Añadir su enlace en la navegación.
3.  Marcar la sección activa en la página correspondiente.
4.  Probar los enlaces desde todas las páginas.
5.  Probar el menú móvil y la navegación con teclado.

# 8. Persistencia y manejo de respuestas

Mostrar información no es lo mismo que guardarla. Hay varias
posibilidades:

-   **Mostrar:** los datos aparecen en la página.
-   **Mantener durante la sesión:** siguen disponibles mientras la
    página permanece abierta.
-   **Guardar localmente:** se almacenan en el navegador, por ejemplo
    con `localStorage` o `sessionStorage`.
-   **Enviar:** se transmiten a un servicio.
-   **Guardar en servidor:** se registran en una base de datos u otro
    sistema centralizado.

No debe afirmarse que el sitio guarda resultados permanentemente sin
comprobar el código. Si no hay almacenamiento explícito, las respuestas
pueden perderse al cerrar o recargar la página.

# 9. Accesibilidad y experiencia de usuario

Buenas prácticas recomendadas:

-   Usar `lang="es"` y una jerarquía lógica de encabezados.
-   Asociar etiquetas claras a los campos de formulario.
-   Añadir texto alternativo a imágenes informativas.
-   Mantener foco visible al navegar con teclado.
-   Evitar comunicar resultados únicamente mediante color.
-   Respetar las preferencias de movimiento reducido.
-   Mantener contraste suficiente.
-   Evitar menús, tarjetas o botones que se salgan de la pantalla en
    móvil.
-   Probar en diferentes tamaños de pantalla y navegadores.

# 10. Lista de pruebas antes de publicar

## Navegación

-   [ ] El logo abre el destino correcto.
-   [ ] Inicio funciona.
-   [ ] Publicaciones - Temas abre el índice.
-   [ ] Cada tema se puede abrir.
-   [ ] Cuestionarios abre la sección prevista.
-   [ ] Actualizaciones muestra las versiones correctas.
-   [ ] Desarrollo Web abre su página.
-   [ ] Log Out tiene el comportamiento esperado.
-   [ ] No hay errores 404.
-   [ ] Las rutas funcionan en la URL publicada de GitHub Pages.

## Diseño

-   [ ] La barra funciona en escritorio y móvil.
-   [ ] Las imágenes cargan.
-   [ ] No hay desplazamiento horizontal involuntario.
-   [ ] Los textos son legibles y tienen contraste.
-   [ ] Los botones funcionan con teclado.
-   [ ] Las animaciones no dificultan el uso.

## Cuestionarios

-   [ ] Las opciones se pueden seleccionar.
-   [ ] Las respuestas correctas están configuradas.
-   [ ] El cálculo de la nota es coherente.
-   [ ] Las preguntas sin respuesta se manejan correctamente.
-   [ ] Los contadores de caracteres funcionan.
-   [ ] Las respuestas abiertas aparecen en la revisión final.
-   [ ] El cuestionario mixto diferencia las preguntas calificables y
    abiertas.
-   [ ] Los botones finales llevan al destino correcto.

## Publicación y privacidad

-   [ ] Se probó la versión publicada, no solo la local.
-   [ ] La consola no muestra errores importantes.
-   [ ] No se publicaron credenciales.
-   [ ] Se comprobó el comportamiento en una sesión nueva.
-   [ ] El historial refleja cambios reales.
-   [ ] Se informa adecuadamente si se recopilan respuestas o datos
    personales.

# 11. Solución de problemas

## Error 404

Causas posibles: nombre de archivo incorrecto, ruta absoluta que ignora
la subcarpeta de GitHub Pages, archivo ubicado en otra carpeta,
diferencia entre mayúsculas y minúsculas o despliegue aún no terminado.

Pasos: copiar la URL que falla, confirmar que el archivo exista,
comparar su ubicación con el `href`, ajustar la ruta y probar de nuevo
en la URL pública.

## La página aparece sin estilos

Comprueba la ruta de la hoja CSS, la ubicación de los recursos, la
extensión y el nombre del archivo. Si los estilos están dentro de
`<style>`, revisa que se esté abriendo el HTML correcto y que no haya
errores de sintaxis.

## El menú móvil no responde

Comprueba que el botón y el menú tengan los identificadores o clases
esperados por JavaScript, que el script se ejecute cuando el DOM esté
disponible y que la consola no muestre errores.

## El cuestionario califica mal

Revisa `data-correct`, los valores de las opciones, los nombres `name` y
que cada pregunta tenga una identidad propia. Confirma que el script
recorra todas las preguntas que deben calificarse.

## Los cambios editados en pantalla desaparecen

`contenteditable` permite editar temporalmente en el navegador, pero no
modifica el archivo publicado ni lo guarda por sí solo. Cambia el
archivo fuente y vuelve a publicarlo, o implementa expresamente una
función de guardado.

# 12. Convenciones recomendadas

-   Usar nombres de archivo descriptivos.
-   Mantener nombres de clases consistentes.
-   No duplicar identificadores.
-   Mantener separados estructura, estilos y comportamiento cuando sea
    práctico.
-   Añadir comentarios breves donde ayuden al mantenimiento.
-   Eliminar textos de ejemplo que puedan confundirse con contenido
    definitivo.
-   Probar después de cambios importantes.
-   Mantener copias de seguridad o utilizar el historial de Git.
-   Actualizar este README cuando cambie el funcionamiento real.

# 13. Glosario

-   **HTML:** lenguaje de marcado para la estructura de la página.
-   **CSS:** lenguaje para el diseño visual.
-   **JavaScript:** lenguaje que añade interactividad en el navegador.
-   **Responsive:** diseño que se adapta a diferentes tamaños de
    pantalla.
-   **DOM:** representación de los elementos HTML que JavaScript puede
    consultar o modificar.
-   **`id`:** identificador de un elemento.
-   **`class`:** nombre compartido por elementos para aplicar estilos o
    seleccionarlos.
-   **`href`:** atributo que define el destino de un enlace.
-   **Ruta relativa:** ruta interpretada en relación con la ubicación
    del archivo actual.
-   **Ruta absoluta:** ruta que parte de una raíz determinada.
-   **`data-*`:** atributos para asociar datos personalizados a
    elementos HTML.
-   **`contenteditable`:** permite editar el contenido de un elemento en
    el navegador; no implica guardado permanente.
-   **`localStorage`:** almacenamiento local del navegador; no es una
    base de datos de servidor.
-   **Backend:** parte del sistema que se ejecuta en servidor.
-   **Hosting:** servicio que aloja y entrega los archivos del sitio.
-   **GitHub Pages:** servicio para publicar sitios estáticos desde un
    repositorio.
-   **404:** error HTTP que indica que el recurso solicitado no se
    encontró.
-   **Caché:** almacenamiento temporal que puede acelerar cargas
    posteriores.
-   **Accesibilidad:** prácticas que permiten que personas con
    diferentes capacidades utilicen el sitio.
-   **Calificación automática:** cálculo basado en reglas definidas en
    el programa; no equivale necesariamente a valorar la calidad de una
    argumentación.

# 14. Aspectos que deben verificarse

Antes de tratar este documento como una especificación definitiva, hay
que comprobar en el repositorio:

1.  La lista exacta de archivos y carpetas.
2.  La implementación completa del inicio de sesión.
3.  Si las respuestas se guardan, se envían o solo se muestran.
4.  Las rutas reales de todos los enlaces.
5.  Qué funciones del historial están disponibles en producción.
6.  El nombre real del editor, programador y alojamiento.
7.  Qué temas están publicados actualmente.
8.  La compatibilidad con los navegadores y dispositivos previstos.

Una función mencionada aquí o en el historial no demuestra por sí sola
que exista en todos los archivos. La implementación debe verificarse
mediante el código real y pruebas.

# 15. Conclusión

¿Y si lo piensas? combina contenido educativo, reflexión ética y
cuestionarios interactivos mediante tecnologías web estándar. Su calidad
depende de que los textos sean claros y responsables, las preguntas
estén bien configuradas, la navegación funcione y la publicación
mantenga rutas correctas.

La documentación debe evolucionar junto con el proyecto. Cuando se
agregue una página, cambie la autenticación, se modifiquen las rutas o
se incorpore almacenamiento de respuestas, este README debe actualizarse
para seguir siendo una guía fiable.

**Regla principal de mantenimiento:** no dar por terminada una función
hasta haber probado su comportamiento en la versión publicada.
