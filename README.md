# ⚙️ Arquitectura Backend y Concurrencia Avanzada con Spring Boot

Este repositorio agrupa una colección de 6 proyectos prácticos desarrollados para explorar e implementar diferentes arquitecturas, patrones de diseño y modelos de concurrencia en el ecosistema de **Spring**. 

El objetivo global de estos proyectos es la resolución de problemas de alto rendimiento, escalabilidad y procesamiento asíncrono en aplicaciones empresariales.

---

## 🛠️ Stack Tecnológico

* **Lenguaje:** Java (17+)
* **Framework Principal:** Spring Boot
* **Módulos de Spring:** Spring Security, Spring WebFlux, Spring Cloud, Spring Batch, Spring AOP.
* **Bases de Datos:** MongoDB (Reactiva).
* **Herramientas y Protocolos:** REST APIs, Server-Sent Events (SSE), WebSockets, Thymeleaf.
* **Arquitectura:** Microservicios, Programación Orientada a Aspectos (AOP), Multihilo, Arquitectura Reactiva.

---

## 📂 Estructura de Proyectos

### 🛡️ Caso 1: Sistema de Seguridad Concurrente (Stark Industries)
Implementación de un sistema de procesamiento en tiempo real para múltiples sensores IoT.
* **Técnicas:** Gestión de ciclo de vida de Beans (IoC), procesamiento concurrente mediante `ExecutorService` y `@Async`.
* **Highlights:** Prevención de trampas de concurrencia (evitando la auto-invocación de métodos `@Async` dentro de la misma clase y asegurando el mapeo estricto de los nombres de los `@Bean`). Implementación de alertas en tiempo real con **WebSockets** y securización con **Spring Security**.

### ⏱️ Caso 2: Benchmarking de Estrategias Multihilo
API REST diseñada para realizar pruebas de estrés computacional y comparar tiempos de ejecución, aceleración (*speedup*) y eficiencia.
* **Estrategias evaluadas:** Ejecución secuencial, concurrencia manual (`FixedThreadPool` / `CachedThreadPool`) y ejecución asíncrona gestionada por el framework.

### 📦 Caso 3: Procesamiento de Pedidos E-commerce (AOP)
Simulador de procesamiento simultáneo de pedidos aplicando **Programación Orientada a Aspectos (AOP)** para mantener la lógica de negocio completamente limpia.
* **Técnicas:** Interceptores `@Around` y `@AfterThrowing` para auditoría, control de rendimiento y manejo de excepciones. Creación de anotaciones personalizadas (ej. `@Auditable`).

### ⚡ Caso 4: Notificaciones Reactivas en Tiempo Real
Sistema de mensajería no bloqueante utilizando **Spring WebFlux**.
* **Técnicas:** Flujos de datos infinitos (`Publisher`/`Subscriber` mediante `Flux` y `Mono`), integración con base de datos NoSQL mediante `ReactiveMongoRepository` y transmisión continua hacia el cliente mediante **Server-Sent Events (SSE)**.

### 🏙️ Caso 5: Gestión de Servicios de Smart City (Microservicios)
Ecosistema distribuido y tolerante a fallos apoyado en la suite de **Spring Cloud**.
* **Técnicas:** Descubrimiento de servicios (Eureka), balanceo de carga (Ribbon), resiliencia y Circuit Breaker (Hystrix), monitorización (Prometheus/Grafana) y trazabilidad distribuida (Sleuth/Zipkin).

### 🗄️ Caso 6: Procesamiento por Lotes (Spring Batch)
Motor de procesamiento de grandes volúmenes de datos mediante trabajos programados.
* **Técnicas:** Definición modular mediante `Job` y `Step`. Configuración de flujos basados en chunks (`ItemReader`, `ItemProcessor`, `ItemWriter`) con estrategias de reanudación y tolerancia a fallos mediante listeners.
