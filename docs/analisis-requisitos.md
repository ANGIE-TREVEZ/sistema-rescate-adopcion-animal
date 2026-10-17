# Análisis de requisitos del Sistema de Gestión de Rescate y Adopción Animal (SIGRA)

## 1. Descripción del problema

Los refugios de animales necesitan llevar un control organizado de los rescates, tratamientos veterinarios, responsables asignados y procesos de adopción. Cuando esta información se administra manualmente, pueden producirse pérdidas de registros, duplicación de datos y dificultades para realizar el seguimiento de los animales.

Para solucionar esta problemática se propone diseñar el Sistema de Gestión de Rescate y Adopción Animal (SIGRA), una plataforma que permita registrar animales rescatados, clasificar las especies, asignar responsables y gestionar las diferentes etapas de atención.

## 2. Objetivo del sistema

Diseñar la arquitectura lógica de un sistema que facilite la administración de rescates y adopciones de animales, aplicando principios SOLID, patrones de diseño de software y control de versiones mediante Gitflow.

## 3. Actores principales

**Ciudadano o reportante:** Persona encargada de informar sobre animales abandonados, heridos o en situación de peligro.

**Voluntario:** Colaborador que participa en el rescate, traslado y cuidado de los animales.

**Veterinario:** Profesional responsable de evaluar la salud de los animales, registrar diagnósticos y controlar los tratamientos.

**Administrador del refugio:** Usuario que gestiona los expedientes, asigna responsables y supervisa el proceso de rescate y adopción.

## 4. Requerimientos funcionales

- **RF01:** Permitir registrar nuevos reportes de rescate con ubicación, fecha, descripción y datos del animal.
- **RF02:** Clasificar los animales rescatados en perros, gatos y fauna silvestre.
- **RF03:** Crear expedientes individuales para cada animal rescatado.
- **RF04:** Permitir al administrador asignar voluntarios o veterinarios a los casos.
- **RF05:** Gestionar los estados del caso: Rescatado, En tratamiento, En recuperación, Disponible para adopción y Adoptado.
- **RF06:** Notificar automáticamente a los voluntarios cuando se les asigne un nuevo rescate.
- **RF07:** Registrar diagnósticos, tratamientos y observaciones veterinarias.
- **RF08:** Consultar el historial y el estado actual de cada expediente.
- **RF09:** Registrar los procesos de adopción de animales domésticos.
- **RF10:** Gestionar la recuperación y posible liberación de fauna silvestre según la autorización de las autoridades competentes.

## 5. Requerimientos no funcionales

- **RNF01 - Escalabilidad:** La arquitectura debe permitir incorporar nuevos módulos sin modificar completamente el sistema.
- **RNF02 - Mantenibilidad:** El código debe organizarse en componentes independientes y aplicar principios SOLID.
- **RNF03 - Trazabilidad:** Los cambios del proyecto deben registrarse mediante commits y ramas Gitflow.
- **RNF04 - Seguridad:** El sistema debe contemplar autenticación y permisos según el rol del usuario.
- **RNF05 - Usabilidad:** La interfaz debe ser comprensible para ciudadanos, voluntarios, veterinarios y administradores.
- **RNF06 - Disponibilidad:** El diseño debe permitir la consulta de expedientes durante la operación habitual del refugio.

## 6. Reglas de negocio

- Cada expediente debe tener un identificador único.
- Un caso puede tener uno o varios responsables asignados.
- Solamente los usuarios autorizados pueden modificar expedientes.
- Los animales domésticos deben cumplir los requisitos de atención y recuperación antes de estar disponibles para adopción.
- La fauna silvestre no debe ingresar automáticamente al proceso de adopción; su destino depende de la evaluación profesional y de las autoridades competentes.
- Los cambios de estado deben conservarse en el historial del expediente.

## 7. Patrones de diseño seleccionados

**Singleton:** Se utilizará para controlar una instancia compartida del servicio central de gestión de casos.

**Observer:** Permitirá informar automáticamente a los observadores registrados cuando ocurra un evento de rescate o asignación.

**Factory Method:** Facilitará la creación de expedientes especializados según el tipo de animal.

**MVC:** Permitirá separar la interfaz de usuario, el procesamiento de solicitudes y los modelos del sistema.

## 8. Metodología de control de versiones

El proyecto utilizará Gitflow con las ramas master, develop y feature. La rama master conservará la versión estable, develop integrará los avances y las ramas feature permitirán desarrollar funcionalidades independientes antes de incorporarlas mediante Pull Requests.
