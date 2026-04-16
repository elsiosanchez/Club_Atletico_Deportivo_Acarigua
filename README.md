# 🦅 Club Atlético Deportivo Acarigua - Sistema de Gestión Deportiva

Este proyecto es una aplicación web integral diseñada para la recopilación, monitoreo y análisis antropométrico del rendimiento deportivo de los atletas del **Club Atlético Deportivo Acarigua**.

## 📖 Descripción del Proyecto

El sistema centraliza la información técnica y médica del club, facilitando el seguimiento del progreso físico de los jugadores a través de mediciones periódicas, control de asistencias y generación de reportes técnicos detallados.

### 🌟 Características Principales

- **Gestión de Atletas:** Registro detallado de deportistas con información personal, técnica, médica y de contacto (incluyendo representante y dirección detallada).
- **Monitoreo Antropométrico:** Seguimiento de peso, altura, envergadura e índices de masa corporal.
- **Evaluación de Rendimiento:** Registro de tests físicos especializados (Fuerza, Resistencia, Velocidad, Coordinación y Reacción).
- **Ficha Médica Digital:** Historial de salud, alergias, condiciones crónicas y gestión de carnet de discapacidad.
- **Control de Asistencias:** Registro diario de presencia en los entrenamientos por categorías.
- **Gestión del Plantel:** Administración de entrenadores y personal del club con roles específicos.
- **Reportes Técnicos en PDF:** Generación e impresión de fichas técnicas individuales con gráficos y métricas de progreso.
- **Seguridad:** Sistema de permisos basado en roles (RBAC) y autenticación segura mediante **JSON Web Tokens (JWT)**.

### 🛡️ Seguridad y Roles (RBAC)

El sistema implementa un modelo de Control de Acceso Basado en Roles para garantizar la integridad y privacidad de la información:

- **Súper Usuario / Administrador:** Acceso total a todos los módulos, incluyendo la configuración del sistema, gestión de usuarios y personal. Debido a la ausencia de un médico de planta constante, el administrador tiene permisos para actualizar fichas médicas.
- **Entrenador:** Orientado al seguimiento técnico. Puede registrar asistencias y actualizar datos de **Rendimiento y Antropometría** de los atletas. Tiene acceso de solo lectura a los datos personales y médicos básicos. No tiene acceso a la configuración ni a la gestión de personal.

#### Matriz de Permisos

| Módulo | Súper / Admin | Entrenador |
| :--- | :---: | :---: |
| **Atletas (Datos Personales)** | Escritura | Lectura |
| **Ficha Médica** | Escritura | Lectura |
| **Rendimiento y Antropometría** | Escritura | **Escritura** |
| **Control de Asistencias** | Escritura | Escritura |
| **Gestión del Plantel** | Escritura | Sin Acceso |
| **Configuración del Sistema** | Escritura | Sin Acceso |
| **Reportes** | Todos | Todos |
