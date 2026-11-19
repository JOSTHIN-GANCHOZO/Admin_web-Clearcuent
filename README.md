# ClearCuent AdminWeb — carpeta local de preparación

**Estado (19/11/2026):** entorno Angular 22.3 preparado por D-03 con `package.json`, lockfile y base standalone; `npm ci`, lint, typecheck, build y formato verificados. Aún no es un repositorio Git local. Las operaciones Git siguen exclusivamente las autorizaciones, revisiones, flujo y límites de la sección **Git** de `../AGENTS.md`; nunca se sobrescribe trabajo existente.

## Alcance aprobado para v1 (RF-56 a RF-61; AM-47)

- Angular + TypeScript para una interfaz ADMIN independiente de la app móvil comercial.
- Inicio/cierre de sesión; total de cuentas `MERCHANT` (RF-59), registros diarios/semanales/mensuales en **tablas**, sin gráficos (RF-60), y lista paginada con id, nombre, negocio y fecha de registro (RF-61).
- Consultas autorizadas por el backend mediante `/api/v1/admin/*`, fuera de `/sync`. Sin acceso a finanzas de comerciantes ni datos de sus clientes (RF-56, RNF-17). Sin desactivar comerciantes, estado activo/inactivo ni suscripciones en v1.

## Antes de iniciar el proyecto web

- El diseño 0.3 está en `../docs/diseno/adminweb-g2.md`: G1/D-22/D-03 están cerradas, pero A6 debe revisar y Josthin aprobar G2 antes de implementar. Faltan OpenAPI versionado, integración con el esquema base de `Usuario` y casos PR-56–61 por CA.
- Vitest/jsdom y Playwright están configurados. Chromium, Firefox y WebKit están descargados en la caché local y arrancan correctamente; pueden eliminarse y reinstalarse después. Aún no hay casos funcionales ni CI.
- A4 puede preparar raíz/configuración/código excepto reglas y pruebas; A5 cubre pruebas/configuración exclusiva. A3 conserva backend. La base generada no implementa autenticación ni RF.
- A2 `disenador` puede proponer pantallas, navegación y estados de AdminWeb en Markdown/SVG en `../docs/diseno/ui-ux/**`; A6 revisa y Josthin aprueba. No implementa Angular ni decide sesión, contratos o seguridad; la aprobación UI/UX no sustituye G2 técnico/web.
- Consultar los requisitos canónicos en `../docs/DERCAS.md` y la marca en `../docs/diseno/`. No duplicar el contrato ni mantener documentos de requisitos divergentes aquí.
