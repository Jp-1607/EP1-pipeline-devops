# EP1 - Pipeline base DevOps

## Integrantes
- Estudiante 1: Juan Pedro Pavez

## Descripción del microservicio
Se creó un microservicio simple llamado **saludo-service**, desarrollado en Python con Flask.
Su función es entregar una respuesta JSON básica para simular un servicio pequeño, fácil de versionar y automatizar.

### Endpoints
- `GET /` → retorna información general del microservicio
- `GET /health` → retorna el estado del servicio

---

## Estrategia de ramificación elegida: GitFlow

Se eligió **GitFlow** porque organiza el trabajo en ramas separadas para desarrollo, funcionalidades y correcciones urgentes.  
En este encargo se exigieron explícitamente las ramas `main`, `develop`, `feature/<nombre>` y `hotfix/<nombre>`, por lo que GitFlow se adapta mejor al repositorio y facilita la trazabilidad del trabajo.

### Ramas utilizadas
- `main`: versión estable
- `develop`: integración de trabajo en desarrollo
- `feature/<nombre>`: nuevas funcionalidades
- `hotfix/<nombre>`: correcciones urgentes

### Comparación breve
- **GitFlow:** mejor para ordenar desarrollo, cambios y correcciones por separado.
- **Trunk-Based Development:** integra cambios frecuentes sobre una sola rama principal y funciona mejor con ramas muy cortas.

En este caso, GitFlow fue la mejor opción porque permite evidenciar claramente el flujo pedido en la evaluación.

---

## Simulación de trabajo colaborativo

### Feature 1
- Rama: `feature/mensaje-bienvenida`
- Cambio realizado: se ajustó el mensaje principal del endpoint `/`

### Feature 2
- Rama: `feature/endpoint-health`
- Cambio realizado: se agregó el endpoint `/health` para validar estado del microservicio

### Hotfix
- Rama: `hotfix/correccion-json`
- Cambio realizado: se corrigió la estructura de la respuesta JSON del servicio principal

### Flujo aplicado
1. Crear rama desde `develop`
2. Desarrollar cambio
3. Hacer commit con mensaje descriptivo
4. Hacer push al repositorio remoto
5. Crear Pull Request
6. Revisar y fusionar cambios

---

## Buenas prácticas del repositorio

### Naming de ramas
- `feature/mensaje-bienvenida`
- `feature/endpoint-health`
- `hotfix/correccion-json`

### Convención de commits
- `feat: agrega endpoint health`
- `feat: actualiza mensaje de bienvenida`
- `fix: corrige estructura json`
- `docs: actualiza readme`

### Flujo de merge
- Las ramas `feature/*` se fusionan hacia `develop`
- La rama `hotfix/*` se fusiona hacia `main`
- Luego se sincroniza `main` con `develop`

### Estrategia de revisión
Antes de aprobar un Pull Request se revisa:
- nombre correcto de la rama
- mensaje de commit claro
- funcionamiento básico del microservicio
- ejecución correcta del workflow

---

## Estructura del repositorio

```bash
EP1-pipeline-devops/
├── .github/
│   └── workflows/
│       └── ci.yml
├── src/
│   └── app.py
├── docs/
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Automatización con GitHub Actions

Se configuró un workflow básico que se ejecuta en:
- cada `push` a `develop`
- cada `pull_request` a `main`

### Rol en CI/CD
GitHub Actions automatiza tareas del repositorio, permitiendo validar el proyecto de forma temprana.
En este caso se utiliza como una base de integración continua, ya que comprueba la estructura del repositorio, instala dependencias y ejecuta una validación simple del código.

---

## Declaración de uso de IA
La IA se utilizó como apoyo para:
- ordenar la documentación
- proponer estructura base del repositorio
- generar ejemplos de commits, ramas y workflow

Todo el contenido fue revisado y adaptado por el equipo antes de su entrega.

---

## Conclusión del trabajo
**Esta parte debes escribirla tú y tu compañero/a con sus palabras.**

### Reflexión individual estudiante 1
[Escribir manualmente]

### Reflexión individual estudiante 2
[Escribir manualmente]
hola
