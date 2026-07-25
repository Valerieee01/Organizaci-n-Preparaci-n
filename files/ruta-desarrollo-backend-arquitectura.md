# Ruta de Desarrollo: Backend → Full-Stack → Arquitectura de Software
### Complementaria a tu rol de PO/QA — 10 semanas

> Objetivo: profundizar en backend, entender infraestructura moderna de punta a punta, y pensar en arquitectura con criterio de negocio (rentabilidad, sostenibilidad, agilidad). Esto no compite con tu ruta de PO — la potencia: vas a priorizar mejor porque vas a entender el costo real de lo que pides.

---

## Bloque 1 — Backend profundo (Semanas 1-3)
**Ya tienes SQL Server sólido (stored procedures, T-SQL, IDENTITY, homologación). Este bloque cierra huecos y sube el nivel.**

### Semana 1 — SQL avanzado más allá de lo operativo
- Índices: cuándo y por qué (clustered vs non-clustered), análisis de planes de ejecución
- Transacciones e isolation levels (esto es clave si sigues tocando RNDC/DIAN)
- Normalización vs desnormalización — cuándo romper la regla y por qué
- **Entregable:** analiza el plan de ejecución de una consulta lenta real de RNDC y documenta el hallazgo

### Semana 2 — Diseño de APIs
- REST bien hecho: verbos, códigos de estado, versionado, paginación
- Introducción a GraphQL (solo para saber cuándo NO usar REST)
- Autenticación/autorización: JWT, OAuth2 — conceptos, no implementación exhaustiva
- **Entregable:** diseña (en papel/Swagger) el contrato de una API para un módulo del app de gestión empresarial

### Semana 3 — Backend moderno en la práctica
- Si SYSCOM usa .NET: profundiza en C# moderno (async/await, LINQ, inyección de dependencias)
- Patrones básicos: Repository, Unit of Work, Service Layer
- Testing de backend: unit tests vs integration tests, mocking de dependencias externas
- **Entregable:** un endpoint simple con su test unitario correspondiente

### Semana 3.5 — QA técnico y automatización (tu área directa)
- **Cypress a fondo:** estructura de proyecto, comandos custom, fixtures, interceptación de requests (`cy.intercept`), manejo de datos de prueba
- **Selenium a fondo:** WebDriver, localizadores robustos (evitar XPath frágil), Page Object Model
- Cómo decidir Cypress vs Selenium según el caso (Cypress para apps modernas SPA, Selenium para compatibilidad cross-browser amplia o stacks legacy)
- Integración de pruebas automatizadas en el pipeline CI/CD de GitLab — que corran en cada merge request, no solo manualmente
- Métricas de QA: cobertura de pruebas, densidad de defectos, tasa de falsos positivos en pruebas automatizadas
- **Entregable:** un flujo crítico del sistema (ej. creación de un registro RNDC) cubierto con una prueba automatizada end-to-end, corriendo en el pipeline

---

## Bloque 2 — Full-Stack con foco en infraestructura moderna (Semanas 4-6)

### Semana 4 — Frontend lo suficiente para hablar el mismo idioma
- No necesitas ser experto: entiende componentes, estado, ciclo de vida (React es buena apuesta, ya la usan en el ecosistema Claude/Vercel)
- Cómo el frontend consume una API — de dónde vienen los errores típicos que ya debuggeas en Vercel
- **Entregable:** ninguno formal, esto es comprensión, no producción

### Semana 5 — Infraestructura y despliegue
- Contenedores: qué es Docker y por qué importa (no necesitas ser DevOps, sí entender el concepto)
- CI/CD real: ya tienes GitLab, profundiza en pipelines — build, test, deploy automatizado
- Diferencia entre ambientes (dev/staging/prod) y por qué el rollback de Vercel falla cuando falla
- **Entregable:** documenta el pipeline actual de un proyecto tuyo (as-is) e identifica un punto de mejora

### Semana 6 — Servicios y comunicación entre sistemas
- Monolito vs microservicios — trade-offs reales, no dogma
- Colas de mensajes (conceptual): cuándo un proceso debe ser asíncrono (piensa en los timeouts que ya viste en P6 Cumplidos de Manifiesto)
- APIs externas e integraciones (tu experiencia con RNDC/DIAN ya es esto en la práctica — ahora le pones el marco teórico)
- **Entregable:** diagrama de arquitectura actual de la integración RNDC (as-is), con anotaciones de puntos frágiles

---

## Bloque 3 — Arquitectura de software con criterio de negocio (Semanas 7-9)
**Esta es tu ventaja diferencial: pensar arquitectura no solo técnica sino en términos de rentabilidad y sostenibilidad.**

### Semana 7 — Principios de arquitectura
- SOLID aplicado con ejemplos reales (no memorizado, aplicado)
- Clean Architecture / Arquitectura hexagonal — el concepto de separar negocio de infraestructura
- Deuda técnica: cómo medirla y cuándo vale la pena pagarla vs. postergarla (esto ya lo tienes de tu rol PO)

### Semana 8 — Decisiones de arquitectura con lente de negocio
- Cómo evaluar "build vs. buy" — cuándo desarrollar algo propio vs. usar una herramienta existente
- Costo de oportunidad técnico: tiempo de desarrollo vs. velocidad al mercado
- Escalabilidad real vs. escalabilidad prematura (sobre-ingeniería es un error común y costoso)
- **Entregable:** documento de 1 página evaluando una decisión arquitectónica real de tu equipo con criterio costo/beneficio

### Semana 9 — Arquitectura y automatización unidas
- Cómo diseñar sistemas testeables desde el principio: `data-testid` consistentes, selectores estables, estados predecibles — arquitectura que facilita Cypress/Selenium en vez de estorbarlos
- Contract testing — verificar que frontend y backend no se rompan entre sí
- Estrategia de pirámide de testing: unit > integration > e2e, y por qué el orden importa para la sostenibilidad (muchos e2e lentos y frágiles es una señal de arquitectura débil, no de falta de esfuerzo en QA)
- Gestión de datos de prueba en entornos automatizados: seeds, fixtures, aislamiento entre pruebas para que Cypress/Selenium no fallen por dependencias entre casos
- **Entregable:** audita un flujo actual de RNDC que sea difícil de automatizar y propone 2-3 cambios de arquitectura (no de test) que lo harían más testeable

---

## Bloque 4 — Consolidación (Semana 10)
- Toma un módulo real del proyecto de gestión empresarial (el que arman con tus compañeros) y hazle:
  1. Diagrama de arquitectura propuesto (to-be)
  2. Justificación de negocio: por qué esa arquitectura es rentable, sostenible y ágil de mantener
  3. Plan de testing/automatización asociado
- Esto se convierte en tu pieza de portafolio que demuestra la combinación dev + visión de negocio

---

## Cómo se cruza con tu ruta de PO
| Semana | Ruta PO (ya armada) | Ruta Dev (nueva) |
|---|---|---|
| 1-3 | Fundamentos + priorización | SQL avanzado + APIs + Cypress/Selenium a fondo |
| 4-6 | Métricas + facilitación | Full-stack + infraestructura |
| 7-9 | Calidad + certificación | Arquitectura con criterio de negocio + arquitectura testeable |
| 10 | Simulación final | Consolidación en proyecto real |

> Nota: la Ruta B ahora tiene 11 puntos de trabajo (10 semanas + la semana 3.5 de QA técnico). Si quieres mantenerla estrictamente en 10 semanas, puedes fusionar la 3.5 con la semana 3, o extender la ruta a 11 semanas — tú decides según tu ritmo real.

**Sugerencia práctica:** no las corras en paralelo full-time — alterna. Semanas impares foco PO, semanas pares foco dev, o dedica mañanas a uno y tardes a otro según tu energía. Ambas rutas se alimentan: cada concepto de arquitectura que aprendas te hace mejor priorizando, y cada sesión de refinamiento te da un caso real para aplicar arquitectura.

## Por qué esto es tu ventaja competitiva real
La mayoría de POs prioriza sin entender el costo técnico real. La mayoría de developers no piensa en rentabilidad ni sostenibilidad del negocio. Tú vas directo al punto donde ambos mundos se cruzan — eso es raro y muy valioso en un mercado donde las empresas necesitan gente que hable los dos idiomas sin traductor.
