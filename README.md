# Método 360 · Ficha de Contexto y Generador de prompts

Mini herramienta de dos pestañas para el curso gratuito.
Versión 1.6. Un solo archivo, sin librerías externas, sin servidor.

## Qué hace

**Pestaña 1. Mi Ficha de Contexto.** Once campos en tres bloques: quién eres,
qué hace tu entidad y bajo qué reglas operas. El campo de actividad pide cuatro
frentes, productos, clientes, zonas y operaciones, porque son los que la IA
necesita para el análisis posterior. La herramienta no supone ningún marco
normativo: lo declara el usuario. El aviso de arriba distingue describir, que
sí va en la Ficha, de calificar por riesgo, que no.

**Pestaña 2. Generador de prompts.** Los seis pasos del método, en orden: rol,
contexto, tarea, datos, formato y límites. Trae un botón que pega la Ficha en
el paso 2, un constructor de carga documental en el paso 4 y los límites base
en el paso 6. El paso 5 está explicado en tres decisiones, cómo lo estructura,
dónde va a terminar y con qué extensión y tono, con ejemplos que se insertan
al pulsarlos. El bloque del destino enseña cuándo pedir el archivo ya armado y
cuándo pedir solo el contenido, para pegarlo en una plantilla propia.

**La herramienta abre precargada** con el caso de Banco Modelo, una entidad
ficticia, y con el prompt de revisión de un capítulo del Manual de Cumplimiento
ya armado en la pestaña 2. Así el alumno ve desde el primer segundo qué se
espera de cada campo y puede escribir encima. El botón Limpiar lo vacía todo, y
el botón Recargar el ejemplo lo trae de vuelta. En cuanto el usuario escribe
algo, eso es lo que se conserva al recargar la página, no el ejemplo.

En el paso 4 se elige qué debe hacer la IA cuando un dato no está en los
documentos cargados: investigarlo y marcarlo aparte, o no salir de ellos. La
segunda es la regla de auditoría y es la que trae el ejemplo.

Lo que el alumno escribe se guarda solo en la memoria de su navegador. Nada
viaja a ningún servidor. El botón Limpiar lo borra.

## Cómo publicarlo

### 1. Subirlo a GitHub

1. Entra a github.com y crea un repositorio nuevo. Puede ser privado.
2. En la pantalla del repositorio vacío, pulsa **uploading an existing file**.
3. Arrastra **el contenido de esta carpeta**, no la carpeta. Es decir:
   `index.html`, `netlify.toml`, `robots.txt`, `404.html` y `README.md`.
4. Pulsa **Commit changes**.

### 2. Conectarlo a Netlify

1. Entra a netlify.com, pulsa **Add new site** y luego **Import an existing project**.
2. Elige GitHub y selecciona el repositorio que acabas de crear.
3. No cambies nada en la pantalla de configuración. El archivo `netlify.toml`
   ya trae lo necesario. Pulsa **Deploy**.
4. En un minuto tendrás una dirección tipo `nombre-al-azar.netlify.app`.
   La cambias en **Site configuration**, luego **Change site name**.

Cada vez que subas un cambio a GitHub, Netlify vuelve a publicar solo.

### 3. Insertarlo en la plataforma del curso

En la lección donde va la herramienta, pega este bloque y sustituye la dirección
por la tuya:

```html
<iframe src="https://TU-SITIO.netlify.app/"
        style="width:100%;height:1400px;border:1px solid #e2e0e8;border-radius:10px"
        title="Ficha de Contexto y Generador de prompts"></iframe>
```

Si tu plataforma no permite pegar HTML, deja simplemente el enlace al sitio.

## Qué contiene cada archivo

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La herramienta completa. Todo va aquí dentro |
| `netlify.toml` | Le dice a Netlify qué publicar y pone la página fuera de buscadores |
| `robots.txt` | Refuerza que los buscadores no la indexen |
| `404.html` | Página de error con el botón de regreso |
| `.gitignore` | Evita subir basura del sistema |

## Si quieres cerrar el iframe a tu dominio

Por defecto la herramienta se puede insertar desde cualquier sitio. Para que
solo funcione dentro de tu plataforma, abre `netlify.toml`, quita el signo `#`
de la última línea y pon ahí tus dominios reales.

## Para cambiar textos

Todo está dentro de `index.html`. Los textos visibles están en español y en
claro, sin código intermedio. Los límites base y los documentos del paso 4 están
en dos listas al principio del bloque `<script>`, marcadas como `DOCS` y
`LIMITES`.

---

Método 360 · Maribel Vázquez Menchaca · GMC360 y 360educa
