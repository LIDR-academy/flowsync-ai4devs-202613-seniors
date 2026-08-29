# FlowSync

Proyecto de práctica del curso: gestión de tareas en equipo. API en AdonisJS 7 (`backend/`) + frontend en React 19 + Vite (`frontend/`).

## Empezar

Trabajas sobre **tu fork**, no sobre el repositorio del curso: aquí vas a crear una rama, commitear y abrir un pull request, y sobre un clon directo no tienes permiso de escritura.

```bash
# 1. Fork desde la web: botón "Fork" en github.com/LIDR-academy/flowsync-ai4devs

# 2. Clona TU fork y añade el del curso como "upstream"
git clone git@github.com:<tu-usuario>/flowsync-ai4devs.git
cd flowsync-ai4devs
git remote add upstream git@github.com:LIDR-academy/flowsync-ai4devs.git
git remote -v          # origin = tu fork, upstream = el del curso

# 3. Colócate en la rama de partida
git fetch upstream
git checkout -b s1/start upstream/s1/start
git push -u origin s1/start
```

> Si te sale `Permission denied (publickey)`, es SSH y no el fork. O subes una clave a tu cuenta de GitHub, o cambias las dos URLs por su versión HTTPS. Si el `clone` falla por otra cosa, avisa a tu TA.

## Backend (`backend/`)

```bash
cd backend
npm install
cp .env.example .env
node ace generate:key
node ace migration:run
npm run dev
```

Arranca en `http://localhost:3333`.

## Frontend (`frontend/`)

Abre otra terminal en la raíz del repo (el backend se queda corriendo en la primera):

```bash
cd frontend
npm install
npm run dev
```

Arranca en `http://localhost:5173`.

---

# El ejercicio

**Monta el harness y mide la diferencia.** Unos 45 minutos, con el reloj puesto, antes del directo.

El enunciado completo, con su formato y sus tres líneas de cierre, está en la lección **"Tu turno"** del Módulo 1. Esto es el resumen operativo.

## Parte A: dos copias, un solo encargo

1. **Duplica el proyecto.** Tu clon es la copia con harness (es la que tiene los remotos y desde la que entregas); la otra se queda pelada y no se toca en todo el ejercicio.

   ```bash
   # desde el directorio que CONTIENE tu clon, no desde dentro
   cp -R flowsync-ai4devs flowsync-sin-harness
   ```

2. **Monta el harness solo en una**, con al menos dos piezas de familias distintas: una que **oriente antes** (un archivo de instrucciones en la raíz que el agente lee siempre, con las convenciones del proyecto y lo que está prohibido) y una que **compruebe después** (algo que se dispare solo al terminar una edición, o un revisor al que delegues la lectura crítica).

3. **Escribe un encargo pequeño y realista como elemento de trabajo en tu tablero de Jira**, en lenguaje de producto y con sus criterios de aceptación. No lo escribas como una especificación técnica.

4. **Lánzalo en las dos copias.** Lo que le llega al agente tiene que ser el mismo texto, palabra por palabra. Si en la copia con harness lo empaquetas en un atajo, en la pelada escribes ese mismo texto a mano.

5. **Compara**, con estas casillas por cada lado: qué archivos tocó (contados) · qué convenciones respetó y cuáles no (nombrándolas) · cuántas veces tuviste que intervenir · qué te tocaría arreglar a mano antes de enseñárselo a alguien.

> No rescates a la copia pelada. Guiarla a mano es exactamente la variable que estás midiendo.
>
> Cuando suene el reloj, para. Una casilla en blanco es información; una rellenada de memoria, no.

## Parte B: las tres líneas

Debajo de la comparación, en el mismo archivo. **Esta parte no se puede fallar.**

1. Qué piezas montaste y cuál te costó más de lo que esperabas.
2. La primera diferencia que viste entre las dos salidas, y en qué te fijaste para verla.
3. Algo que dejaste escrito en el harness y que el agente no cumplió igualmente.

---

# Cómo se entrega

**Un pull request desde tu fork**, con dos cosas dentro y ni una más:

1. **Tu archivo de comparación**, en `docs/harness/comparacion.md`. Ese directorio no existe todavía: créalo.
2. **`prompts.md`**, en la raíz. Ya está aquí con la plantilla puesta: cada prompt en su bloque de código, tal cual lo lanzaste, con su modelo y su herramienta. Incluye también los que no funcionaron.

```bash
git checkout -b harness-<tus-iniciales>
git add docs/harness prompts.md
git commit -m "harness: comparacion con y sin harness, mas prompts"
git push -u origin harness-<tus-iniciales>
```

Con la rama empujada, GitHub te ofrece el botón para abrir el pull request. Va **contra el repositorio del curso**, no contra tu fork.

**Plazo: antes del directo.** Lo que llegue a tiempo lo revisa tu TA antes de la sesión, que es el único momento en que ese feedback te sirve. Lo que llegue después se marca como recibido, pero ya no se revisa.

> Entrégalo con lo que tenga, sin maquillarlo: lo que le falta es la mitad de lo interesante.

---

Las instrucciones completas de prework (checklist de entorno + priming) están en el Módulo 1 del asíncrono del curso.
