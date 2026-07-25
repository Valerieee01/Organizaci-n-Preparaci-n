# Prompt para Claude Code

Copia y pega esto directamente en Claude Code (terminal, VS Code o la app de escritorio).

---

```
Antes de escribir código, LEE estos dos archivos que están en esta misma carpeta para tener 
el contexto completo de mi ruta de aprendizaje:

- ruta-product-owner.md
- ruta-desarrollo-backend-arquitectura.md

(Si no los encuentras en la carpeta actual, pídeme la ruta exacta antes de continuar — no 
inventes ni resumas contenido sin haberlos leído.)

Con base en el contenido real de esos dos documentos, quiero que crees una página web sencilla 
(single-page, HTML/CSS/JS o React si lo prefieres, sin backend) que combine dos cosas:

1. UN MAPA/DIAGRAMA DE FLUJO de mi ruta de aprendizaje
2. UN HORARIO SEMANAL visual para organizar cuándo estudio

## CONTEXTO
Soy desarrolladora de software transicionando a un rol híbrido de Product Owner/QA/Business 
Analyst, y en paralelo quiero profundizar como desarrolladora backend con enfoque en 
arquitectura de software. Los dos documentos que leíste contienen:

- ruta-product-owner.md → Ruta A, 6 semanas (PO)
- ruta-desarrollo-backend-arquitectura.md → Ruta B, 10 semanas (Backend/Full-Stack/Arquitectura)

Extrae de cada documento: el título de cada semana, los temas principales, y el entregable 
(si lo hay), para usarlos como contenido real de cada nodo del diagrama — no lo resumas de 
más, pero tampoco copies el documento completo, quédate con lo esencial de cada semana.

Las rutas se alternan: semanas impares foco PO, semanas pares foco Dev (o las distribuyo por 
franjas de tiempo distintas, ver horario abajo).

## MI DISPONIBILIDAD REAL
- Noches entre semana (lunes a viernes): mi bloque principal de estudio, aprox. 1.5-2 horas 
  disponibles (asumamos 8:00pm-9:30pm, ajústalo si prefieres bloques distintos)
- En el trabajo: puedo robar 1 hora libre en algún punto del día (ej. hora de almuerzo o antes 
  de empezar), no siempre el mismo horario
- Fines de semana: al menos una sesión más larga (1-2h) para entregables o proyectos prácticos

## QUÉ NECESITO QUE CONSTRUYAS

### 1. Vista de Mapa/Flujo (lo principal)
- Diagrama visual tipo flowchart o roadmap horizontal/vertical mostrando las 10 semanas 
  combinadas (ambas rutas)
- Cada semana es un nodo/tarjeta clickeable que al abrirse muestra el detalle de esa semana 
  (temas + entregable)
- Diferencia visualmente la Ruta A (PO) de la Ruta B (Dev) con colores distintos, pero muestra 
  cómo se entrelazan en el tiempo
- Marca de progreso: poder click para marcar una semana como completada (guardarlo en 
  localStorage está bien para esta versión simple, no necesito persistencia en backend)

### 2. Vista de Horario Semanal
- Calendario semanal simple (lunes a domingo) con los bloques de tiempo disponibles ya 
  ubicados: noches entre semana, la hora libre en el trabajo (que yo pueda arrastrar o 
  reasignar a distintos días), y el bloque de fin de semana
- Cada bloque debe poder asignarse a "Ruta A" o "Ruta B" con un selector simple
- Vista limpia, no sobrecargada — priorizo claridad sobre funcionalidad compleja

### 3. Diseño
- Minimalista y moderno, que se vea bien en escritorio y en móvil (voy a revisarlo desde el celular)
- Paleta de colores clara con buen contraste, tipografía legible
- No necesito animaciones complejas ni librerías pesadas — prioriza que cargue rápido y sea 
  fácil de mantener

### 4. Estructura técnica
- Un solo archivo HTML si es posible (con CSS y JS embebido o en archivos separados simples), 
  para poder abrirlo directo en el navegador sin necesidad de servidor
- Si usas alguna librería para el diagrama de flujo, que sea liviana (evita dependencias 
  pesadas o que requieran build complejo)

Empieza por proponerme la estructura general antes de generar todo el código, para confirmar 
que el enfoque visual te quedó claro.
```

---

## Notas antes de usarlo
- **Importante:** guarda `ruta-product-owner.md` y `ruta-desarrollo-backend-arquitectura.md` en la misma carpeta donde vas a abrir Claude Code, con esos nombres exactos (o ajusta los nombres en el prompt si los guardas distinto). Descárgalos de esta conversación antes de empezar.
- Ajusta el horario de noches (8:00pm-9:30pm) si tu franja real es otra — está puesto como ejemplo.
- Si prefieres que Claude Code use React en vez de HTML plano, dilo explícito al inicio del prompt; el prompt actual deja la puerta abierta a ambas opciones pero prioriza simplicidad.
- Puedes pegar este prompt tal cual, o decirle a Claude Code "antes de generar código, hazme 2-3 preguntas si algo no está claro" si quieres afinar detalles primero.
