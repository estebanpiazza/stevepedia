# Despliegue de stevepedia

Revisado el 21/09/2026 contra configuracion versionada y evidencia local. Repositorio: https://gitlab.com/estebanpiazza51/stevepedia. Rama de referencia: `main`.

## Destino y procedimiento

Pagina estatica index.html y assets/. Pipeline Pages copia a pages-dist; verificar recursos relativos y rutas en la URL real de Pages. No requiere npm. Dominio personalizado no confirmado en esta auditoria.

## GitLab CI

La configuracion vigente esta en [.gitlab-ci.yml](.gitlab-ci.yml). Contiene publicacion GitLab Pages. Revisar sus reglas de rama antes de publicar. Un pipeline de otra rama, cancelado o solo de verificacion no prueba publicacion. Para la URL y dominios vigentes abrir Deploy > Pages en este proyecto; no construir una URL suponiendo que coincide con el slug. Esperar el job Pages exitoso del SHA solicitado y comprobar el sitio por HTTPS.

## Cloud y criterio de terminado

El checkout Cloud no hereda archivos ignorados, sesiones de CLI ni secretos de esta PC. Usar variables/secretos del entorno o el gestor vigente; mantenerlos fuera de commits, argumentos visibles y logs. Si falta autenticacion, indicar proveedor y paso pendiente sin pedir contrasenas por chat.

Para una tarea de publicacion: identificar URL y proveedor, validar el cambio, integrar el commit en la rama que corresponda, ejecutar el mecanismo anterior y comprobar el cambio visible en esa URL. Informar commit, estado del despliegue y comprobacion realizada. Diferenciar codigo subido, build aprobado y sitio actualizado. Una respuesta HTTP 200 o un push por si solos no prueban que el cambio solicitado este publicado. Cuando no hay destino confirmado, registrar esa falta y no afirmar un despliegue.
