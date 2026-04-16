# EP1 - Pipeline base DevOps

## Integrantes
- Estudiante 1: Juan Pavez

## Descripción del microservicio
Para esta evaluación se trabajó con un microservicio simple llamado **saludo-service**, desarrollado en **Python con Flask**.  
Se optó por una solución pequeña y funcional para poder enfocarnos en lo que pedía el encargo: control de versiones, trabajo con ramas, documentación del repositorio y automatización básica con GitHub Actions.

El microservicio responde en formato JSON y cuenta con dos endpoints principales:

- `GET /` → entrega información general del servicio
- `GET /health` → permite validar el estado básico del microservicio

Aunque es un proyecto sencillo, cumple con el objetivo de servir como base para aplicar prácticas iniciales de DevOps dentro de un repositorio real.

---

## Estrategia de ramificación elegida: GitFlow

Para este trabajo se eligió **GitFlow** como estrategia de ramificación.

La razón principal es que este modelo se ajusta de forma más clara a lo solicitado en la evaluación, ya que permite separar el trabajo estable, el trabajo en desarrollo, las nuevas funcionalidades y las correcciones urgentes en ramas distintas.  
Esto hace más fácil ordenar el repositorio, entender qué se hizo en cada etapa y mantener trazabilidad de los cambios.

### Ramas utilizadas
- `main`: contiene la versión estable del proyecto
- `develop`: concentra los cambios en desarrollo antes de pasar a la rama principal
- `feature/<nombre>`: se utiliza para crear nuevas funcionalidades o mejoras
- `hotfix/<nombre>`: se utiliza para correcciones puntuales o urgentes

### ¿Por qué GitFlow y no Trunk-Based Development?
GitFlow entrega una estructura más marcada, lo que ayuda bastante cuando se está aprendiendo a trabajar con ramas y con flujos colaborativos.  
Por otro lado, **Trunk-Based Development** funciona con integraciones mucho más frecuentes sobre una rama principal única y ramas de corta duración. Es un modelo muy útil en entornos ágiles, pero en este caso GitFlow nos permitió evidenciar de manera más clara cada etapa pedida en la pauta.

En resumen, se eligió GitFlow porque entrega mayor orden, mejor separación de responsabilidades y una trazabilidad más visible dentro del repositorio.

---

## Simulación de trabajo colaborativo

Para cumplir con el flujo colaborativo solicitado, se trabajó con ramas separadas y se integraron los cambios mediante **Pull Requests**.

### Feature 1
- Rama: `feature/mensaje-bienvenida`
- Cambio realizado: se actualizó el mensaje principal del microservicio para mejorar la respuesta del endpoint raíz.

### Feature 2
- Rama: `feature/endpoint-health`
- Cambio realizado: se mejoró el endpoint `/health`, agregando una validación más completa del estado del servicio.

### Hotfix
- Rama: `hotfix/correccion-json`
- Cambio realizado: se corrigió un detalle puntual en la estructura del JSON para estandarizar mejor la respuesta del servicio.

### Flujo aplicado
1. Se creó la rama a partir de la rama base correspondiente.
2. Se realizaron cambios en el código del microservicio.
3. Se registraron los cambios mediante commits.
4. Se enviaron los cambios al repositorio remoto.
5. Se abrió un Pull Request para revisar e integrar el cambio.
6. Finalmente, se hizo merge de cada rama según el flujo definido.

Este proceso permitió reflejar un trabajo colaborativo simple, pero ordenado y trazable.

---

## Buenas prácticas del repositorio

### Naming de ramas
Para mantener orden y claridad, se usó una convención simple y fácil de entender:

- `feature/mensaje-bienvenida`
- `feature/endpoint-health`
- `hotfix/correccion-json`

Esto ayuda a identificar rápidamente qué tipo de cambio contiene cada rama.

### Convención de commits
Se utilizaron mensajes de commit breves, directos y relacionados con el cambio realizado.  
Ejemplos:

- `feat: actualiza mensaje de bienvenida`
- `feat: mejora endpoint health`
- `fix: corrige estructura json`
- `docs: actualiza readme`

La idea fue dejar mensajes comprensibles, para que cualquier integrante pueda revisar el historial y entender qué se modificó.

### Flujo de merge
- Las ramas `feature/*` se integran hacia `develop`
- Las ramas `hotfix/*` se integran hacia `main`
- Luego, si es necesario, se sincroniza el cambio con `develop`

Este flujo permite separar nuevas funcionalidades de correcciones urgentes, evitando mezclar todo en una sola rama.

### Estrategia de revisión
Antes de aceptar un Pull Request se revisó:
- que la rama tuviera el nombre correcto
- que el cambio fuera coherente con el objetivo de la rama
- que el código siguiera funcionando
- que el workflow de GitHub Actions se ejecutara correctamente
- que el historial del repositorio quedara claro y ordenado

---

## Estructura del repositorio

```bash
EP1-pipeline-devops/
├── .github/
│   └── workflows/
│       └── ci.yml
├── src/
│   └── app.py
├── requirements.txt
├── .gitignore
├── README.md
```

### Explicación breve de la estructura
- `.github/workflows/ci.yml`: contiene el workflow de GitHub Actions
- `src/app.py`: archivo principal del microservicio
- `requirements.txt`: dependencias necesarias del proyecto
- `.gitignore`: archivos y carpetas que no deben versionarse
- `README.md`: documentación general del repositorio

---

## Automatización con GitHub Actions

Se configuró una acción básica de **GitHub Actions** para ejecutar validaciones automáticas en dos casos:

- cuando hay `push` a la rama `develop`
- cuando se crea un `pull request` hacia `main`

### Rol dentro de CI/CD
GitHub Actions cumple un rol importante en los procesos de integración continua, ya que permite automatizar tareas repetitivas y validar cambios antes de integrarlos.

En este proyecto, la automatización se usó para:
- descargar el repositorio
- configurar Python
- instalar dependencias
- validar la sintaxis del archivo principal del microservicio

Aunque es una automatización básica, representa una primera aproximación real a un flujo CI/CD, ya que ayuda a detectar errores simples antes de continuar con la integración.

---

## Importancia de la documentación

Documentar el repositorio fue importante porque:
- facilita la comprensión del proyecto
- permite a otros integrantes entender más rápido la estructura
- deja claras las reglas de trabajo
- mejora la mantención del repositorio a futuro

El archivo `README.md` funciona como una guía principal del proyecto, reuniendo la descripción general, la estrategia de trabajo, las buenas prácticas utilizadas y la automatización aplicada.

---

## Declaración de uso de IA
Para este trabajo se utilizó IA como apoyo en la organización de ideas, redacción de documentación y estructuración del repositorio.  
De todas formas, el contenido fue revisado, ajustado y validado antes de dejarlo como versión final del proyecto.

---

## Conclusión
En esta evaluación se logró implementar una base de trabajo DevOps utilizando Git, GitHub y GitHub Actions.  
A través del uso de ramas, commits, pull requests y una automatización básica, fue posible ordenar el desarrollo del microservicio y dejar evidencia del flujo de trabajo realizado.

Además, la documentación permitió complementar el proyecto con reglas claras de versionamiento, colaboración y revisión, lo que hace que el repositorio no solo funcione, sino que también quede entendible y mantenible.

En general, este trabajo ayudó a comprender de mejor manera cómo se conectan la organización del código, la colaboración en equipo y la automatización dentro de un entorno DevOps inicial.

---

## Reflexión individual estudiante 1
En lo personal, esta actividad me ayudó a entender mucho mejor cómo funciona el trabajo con ramas en GitHub. Antes lo veía como algo más teórico, pero al tener que crear ramas feature, develop y hotfix, además de hacer pull requests y merges, pude entender mejor para qué sirve cada una y cómo se aplican en un proyecto real. También me quedó más claro que documentar el repositorio no es solo un trámite, sino una forma de ordenar el trabajo y dejar todo más entendible.

## Reflexión individual estudiante 2
Durante este trabajo pude comprender mejor la importancia de mantener un flujo ordenado dentro del repositorio. Aprendí que no se trata solo de subir archivos, sino de trabajar con una estructura clara, usando ramas, commits y revisiones que permitan seguir la trazabilidad del proyecto. También fue útil ver cómo una acción básica de GitHub Actions puede apoyar la validación del código y servir como primer acercamiento a la integración continua.

