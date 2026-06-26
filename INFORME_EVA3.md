# Informe de Evaluación Parcial N°3: Ingeniería DevOps

**Estudiante:** Juan Pedro Pavez Cancino  
**Asignatura:** Ingeniería DevOps  
**Fecha:** 26 de junio de 2026

## 1. Introducción
El presente informe detalla la implementación de mecanismos de observabilidad y cumplimiento normativo en un pipeline CI/CD, utilizando Kubernetes, Prometheus y Grafana para garantizar la disponibilidad y calidad del microservicio.

## 2. Infraestructura y Orquestación (IE2)
Se realizó el despliegue del microservicio en un entorno orquestado utilizando Minikube, permitiendo la gestión de contenedores de forma automatizada.
* **Evidencia:**



## 3. Observabilidad y Monitoreo (IE1, IE3)
Se integró el stack `kube-prometheus-stack` mediante Helm, permitiendo la visualización de métricas críticas como uso de CPU y memoria a través de paneles personalizados en Grafana.
* **Evidencia del Dashboard:**


## 4. Calidad y Cumplimiento (IE5, IE6)
Se implementó un "Quality Gate" en SonarCloud. Gracias a la configuración `sonar.qualitygate.wait=true` en el pipeline, el sistema detiene automáticamente cualquier despliegue que no cumpla con los estándares mínimos de seguridad y calidad del código.

## 5. Reflexión y Aprendizaje (IE4)
La integración de herramientas de monitoreo nos permite pasar de un enfoque reactivo a uno proactivo. Al visualizar el uso de recursos en tiempo real, podemos tomar decisiones técnicas informadas, como el escalado de pods ante picos de demanda.

## 6. Declaración de uso de IA
Para el desarrollo técnico de este encargo, se utilizó asistencia de inteligencia artificial (ChatGPT) para la estructuración de archivos YAML, comandos de Helm y resolución de errores de configuración, validando siempre cada paso en el entorno local de Codespaces.
