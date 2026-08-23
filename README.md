# Buzón de Sugerencias — Bienestar Universitario

Backend en Node.js con Express que recibe, guarda y muestra sugerencias sobre el área de Bienestar Universitario. Proyecto desarrollado 100% desde el navegador con StackBlitz, GitHub y Render, como parte del taller de la asignatura Programación Aplicada.

## Contexto

La institución quería un canal digital simple para que cualquier persona dejara sugerencias sobre bienestar universitario. El backend recibe nombre (opcional), categoría y mensaje desde un formulario, los guarda en memoria mientras el servidor corre, y los expone en un panel de administración.

## Historias de usuario

```
Como estudiante
quiero enviar una sugerencia sobre los servicios de bienestar universitario
para que el equipo encargado la revise y mejore el servicio

Como estudiante que prefiere no identificarse
quiero poder enviar una sugerencia sin escribir mi nombre
para sentirme cómodo compartiendo mi opinión sin temor a represalias

Como encargado del área de bienestar universitario
quiero ver todas las sugerencias recibidas en un panel
para identificar problemas recurrentes y priorizar acciones
```

## Tecnologías

- Node.js + Express
- Almacenamiento en memoria (sin base de datos)
- Frontend en HTML/CSS/JS puro, servido como estático desde `public/`

## Estructura del proyecto

```
public/
  ├── index.html   → formulario que ve el usuario
  ├── script.js    → envía el formulario al servidor con fetch
  └── admin.html   → panel que lista las sugerencias
index.js            → servidor Express
package.json
```

## Endpoints

| Método | Ruta | Descripción |
|---|---|---|
| POST | `/api/sugerencias` | Recibe y guarda una nueva sugerencia |
| GET | `/api/sugerencias` | Devuelve la lista de sugerencias en JSON |
| * | cualquier otra ruta | Devuelve `404` con `{"error":"Ruta no encontrada"}` |

## Casos de prueba

| Acción | Resultado esperado | ¿Pasó? |
|---|---|---|
| Enviar sugerencia completa | Se guarda y limpia el formulario | ✅ |
| Enviar con mensaje vacío | El servidor no la guarda (bloqueado por validación `required`) | ✅ |
| Ver panel de administración | Aparece la lista completa de sugerencias | ✅ |
| Visitar una ruta inexistente (`/api/noexiste`) | Devuelve error 404 en formato JSON | ✅ |

## Retrospectiva

**¿Qué funcionó bien?**
[Completar]

**¿Qué nos costó más trabajo?**
Ubicar correctamente los archivos `admin.html` y `script.js` dentro de la carpeta `public` (al inicio quedaron fuera, lo que generaba errores como `Cannot GET /admin.html`), y recordar reiniciar el servidor con `npm start` para que tomara los cambios en el código, como el manejo de errores 404.

**¿Qué harían distinto si empezaran de nuevo?**
[Completar]

**¿Qué le agregarían al buzón en una siguiente versión?**
[Completar — ideas: guardar las sugerencias en una base de datos real en vez de memoria, mostrar la fecha en el panel de administración, filtrar sugerencias por categoría, agregar autenticación al panel admin]

## Enlaces

- Repositorio: https://github.com/karolquicenoospina680-coder/buzon-bienestar-karol
- Aplicación publicada: https://buzon-bienestar-karol.onrender.com
Sugerencias: https://buzon-bienestar-karol.onrender.com/admin.html