# AGENTS.md — AdminWeb de ClearCuent

Aplicar `../AGENTS.md` y `../docs/DERCAS.md` desde el hub. Este archivo solo especializa el alcance web: RF-56 a RF-61, RNF-17, AM-16 y AM-47 (revisión autorizada por Josthin el 14/11/2026).

- Angular + TypeScript para ADMIN; app móvil React Native solo para `MERCHANT`. Presentar resumen, registros por período en tablas y listado paginado. No gráficos, pagos, gestión de comerciantes ni datos financieros.
- Para consultas usar solo endpoints administrativos autenticados (`/api/v1/admin/*`); el login/recuperación web necesitará endpoints de autenticación separados según G2. Nunca usar `/sync` ni conexión directa a PostgreSQL. El backend comprueba el rol: la protección de rutas del navegador no autoriza datos (RF-56, RNF-17).
- Las decisiones de sesión, CSRF, aprovisionamiento/revocación, límites y pruebas están en `../docs/diseno/adminweb-g2.md` y D-22. D-03 instaló el entorno; el diseño sigue pendiente A6/G2 y no debe implementarse todavía. No usar Web Storage para credenciales ni colocar secretos en archivos públicos.
- Existe Angular 22.3 con lockfile; `npm ci`, lint, typecheck, build y formato pasan. Vitest/jsdom y Playwright están configurados; Chromium, Firefox y WebKit arrancan. Los runners descubren cero casos: no afirmar RF probados ni CI verde.
- Esta carpeta aún no es un repositorio Git local. Las operaciones Git siguen las autorizaciones, revisiones, flujo y límites de la sección **Git** de `../AGENTS.md`; ningún agente despliega aplicaciones ni publica releases. A4 puede editar raíz/configuración/código salvo reglas y pruebas; A5 cubre Vitest/Playwright y configuración exclusiva. D-03 está ejecutada, pero G2 sigue bloqueando código funcional ADMIN.
- A2 `disenador` propone UI/UX web únicamente en `../docs/diseno/ui-ux/**` usando paleta/logos existentes; no edita esta carpeta ni diseña cookies/tokens/CSRF. A6 revisa y Josthin aprueba la interfaz; esa aprobación no sustituye G2 web técnico.
