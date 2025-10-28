(Este repositorio corresponde a la **Fase 1** del trabajo práctico, donde se define la arquitectura inicial del proyecto y su configuración base.)

# Sistema de Gestión de Turnos y Evaluaciones Vehiculares (VTVO) 🚗
<img width="1584" height="184" alt="Header" src="https://github.com/user-attachments/assets/fbb64e3c-6ee9-4077-a5fa-d07635f763a1" />

## 📌 Descripción del Proyecto

El sistema gestiona la revisión anual de vehículos en un centro de verificación técnica vehicular (VTVO).  
Permite solicitar turnos, registrar chequeos de seguridad y notificar resultados.

## 🎯 Objetivos funcionales
- Solicitud de turno por número de matrícula
- Confirmación y visualización del estado de un turno
- Evaluación del vehículo en 8 chequeos (1–10)
- Determinación del resultado según reglas:
  - ✅ Total > 80 → Vehículo Seguro
  - ❌ Total < 40 → Requiere rechequeo
  - ❌ Si algún punto < 5 → Requiere rechequeo
- Envío de observaciones al dueño del vehículo

## 🧱 Arquitectura del Proyecto

El sistema se organiza bajo una **arquitectura en 4 capas**:

- **GUI**: Interfaz con el usuario
- **Servicio**: Lógica de negocio y validaciones
- **Persistencia**: Acceso y gestión de la Base de Datos H2 mediante JDBC
- **Excepciones**: Manejo centralizado de errores
- **Modelo**: Entidades del dominio

📍  Lenguaje: Java  
📍  DB: H2 local (modo file system)  
📍  Control de versiones: GitHub  

## 📂 Estructura de carpetas

```plaintext
TP-Integrador-VTVO/
 ├── src/
 │    ├── gui/
 │    │    ├── LoginGUI.java
 │    │    ├── MenuDuenoGUI.java
 │    │    └── MenuInspectorGUI.java
 │    │
 │    ├── servicio/
 │    │    ├── UsuarioService.java
 │    │    ├── TurnoService.java
 │    │    └── EvaluacionService.java
 │    │
 │    ├── persistencia/
 │    │    ├── ConexionDB.java
 │    │    ├── UsuarioDB.java
 │    │    ├── VehiculoDB.java
 │    │    ├── TurnoDB.java
 │    │    └── EvaluacionDB.java
 │    │
 │    ├── excepciones/
 │    │    ├── UsuarioException.java
 │    │    ├── TurnoException.java
 │    │    └── EvaluacionException.java
 │    │
 │    └── modelo/
 │         ├── Usuario.java
 │         ├── Dueno.java
 │         ├── Inspector.java
 │         ├── Vehiculo.java
 │         ├── Turno.java
 │         ├── Chequeo.java
 │         ├── Evaluacion.java
 │         └── Notificacion.java
 │
 └── README.md
