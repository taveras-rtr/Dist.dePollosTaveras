# Especificación de Requisitos del Sistema

**Proyecto:** Dist. de Pollos Taveras  
**Documento:** Especificación de requisitos de software  
**Versión:** 1.0  
**Asignatura:** Ingeniería de Software I  
**Institución:** Universidad Abierta para Adultos (UAPA)

---

## 1. Introducción

La ingeniería de requisitos constituye una etapa fundamental del ciclo de vida del software, ya que permite identificar, analizar, documentar y validar las necesidades que el sistema debe satisfacer.

El presente documento establece la especificación inicial de requisitos del sistema Dist. de Pollos Taveras, una solución informática propuesta para apoyar la administración de las operaciones comerciales de una empresa dedicada a la distribución de pollos.

La especificación define las funcionalidades principales, las restricciones técnicas, los atributos de calidad y los criterios generales de aceptación que servirán como referencia para las actividades posteriores de diseño, implementación y pruebas.

Este documento constituye una base para mantener la coherencia entre las necesidades identificadas, los modelos UML, la arquitectura propuesta y las tareas de desarrollo registradas en GitHub.

## 2. Propósito del sistema

El propósito del sistema es facilitar la gestión y el control de las operaciones comerciales de Dist. de Pollos Taveras mediante una aplicación informática que permita administrar productos, precios, inventario, ventas, facturas, clientes, pagos y cuentas por cobrar.

La solución busca centralizar la información relevante del negocio, reducir la duplicidad de registros y facilitar la consulta de datos necesarios para las operaciones comerciales.

## 3. Alcance del sistema

El sistema contempla las siguientes áreas funcionales:

- Gestión de productos.
- Administración de precios.
- Control de inventario.
- Registro y consulta de ventas.
- Gestión de facturas.
- Administración de clientes.
- Seguimiento de cuentas por cobrar.
- Registro y consulta de pagos.

El alcance se limita a las funciones relacionadas con la administración comercial descrita en este documento.

La incorporación de nuevas funcionalidades deberá evaluarse según las necesidades identificadas, su prioridad y su impacto en la planificación del proyecto.

## 4. Identificación de los interesados y usuarios

Los interesados son las personas o grupos que pueden influir en el sistema o verse afectados por sus resultados.

Para este proyecto académico se identifican los siguientes perfiles:

| Interesado o usuario | Responsabilidad o interés |
|---|---|
| Propietario o administrador | Supervisar las operaciones comerciales y consultar información del negocio. |
| Personal de ventas | Consultar productos y precios, y registrar las operaciones de venta que le correspondan. |
| Personal de inventario | Consultar existencias y registrar los movimientos autorizados. |
| Personal administrativo | Consultar facturas, clientes, pagos y cuentas por cobrar. |
| Equipo de desarrollo | Analizar, diseñar, documentar y dar seguimiento a la solución propuesta. |

Esta identificación constituye una propuesta inicial. Los perfiles definitivos y sus permisos deberán establecerse de acuerdo con las necesidades del negocio.

## 5. Clasificación de los requisitos

Los requisitos se clasifican en dos categorías principales:

### 5.1. Requisitos funcionales

Describen los servicios, operaciones y comportamientos que el sistema debe proporcionar.

### 5.2. Requisitos no funcionales

Establecen las condiciones de calidad, seguridad, rendimiento, mantenimiento y funcionamiento que deberá satisfacer la solución.

Esta clasificación permite analizar las necesidades del sistema desde una perspectiva funcional y técnica.

## 6. Requisitos funcionales

Los siguientes requisitos definen las principales operaciones contempladas para el sistema.

| Código | Nombre | Descripción | Prioridad |
|---|---|---|---|
| RF-01 | Gestión de productos | El sistema deberá permitir registrar, consultar y actualizar la información de los productos. | Alta |
| RF-02 | Gestión de precios | El sistema deberá permitir consultar y administrar los precios asociados a los productos. | Alta |
| RF-03 | Control de inventario | El sistema deberá permitir registrar y consultar los movimientos de inventario. | Alta |
| RF-04 | Registro de ventas | El sistema deberá permitir registrar las operaciones de venta y calcular sus importes correspondientes. | Alta |
| RF-05 | Gestión de facturas | El sistema deberá permitir registrar y consultar la información de las facturas relacionadas con las operaciones comerciales. | Alta |
| RF-06 | Gestión de clientes | El sistema deberá permitir registrar, consultar y actualizar la información de los clientes. | Alta |
| RF-07 | Cuentas por cobrar | El sistema deberá permitir consultar las facturas pendientes y dar seguimiento a los importes pendientes de pago. | Alta |
| RF-08 | Gestión de pagos | El sistema deberá permitir registrar y consultar los pagos asociados a las operaciones comerciales. | Alta |

Las prioridades representan una clasificación inicial propuesta para el proyecto. Podrán ajustarse durante la planificación, según las necesidades de los usuarios y las dependencias entre funcionalidades.

### 6.1. Dependencias entre requisitos

Algunas funcionalidades requieren información o servicios proporcionados por otras áreas del sistema.

| Requisito | Dependencia principal |
|---|---|
| RF-01: Gestión de productos | Información básica de los productos. |
| RF-02: Gestión de precios | Productos registrados. |
| RF-03: Control de inventario | Productos y reglas de movimiento de inventario. |
| RF-04: Registro de ventas | Productos, precios y reglas comerciales. |
| RF-05: Gestión de facturas | Información de ventas y clientes, cuando corresponda. |
| RF-06: Gestión de clientes | Registro y consulta de clientes. |
| RF-07: Cuentas por cobrar | Facturas y registro de pagos relacionados. |
| RF-08: Gestión de pagos | Operaciones comerciales y documentos pendientes de pago, según corresponda. |

Estas dependencias deberán tenerse en cuenta al diseñar los módulos, establecer el orden de desarrollo y preparar las pruebas de integración.

## 7. Requisitos no funcionales

Los requisitos no funcionales definen las condiciones de calidad que deberá satisfacer el sistema.

| Código | Atributo | Requisito |
|---|---|---|
| RNF-01 | Seguridad | El sistema deberá controlar el acceso a las funcionalidades y proteger las credenciales y la información según los permisos definidos. |
| RNF-02 | Integridad | Las operaciones deberán preservar la consistencia de los datos mediante validaciones, restricciones y transacciones cuando corresponda. |
| RNF-03 | Usabilidad | La interfaz deberá presentar información comprensible y permitir que los usuarios identifiquen las operaciones disponibles. |
| RNF-04 | Mantenibilidad | El diseño deberá favorecer la separación de responsabilidades y reducir las dependencias innecesarias entre componentes. |
| RNF-05 | Rendimiento | Las consultas y operaciones deberán responder en tiempos adecuados para el volumen de información y las condiciones de uso previstas. |
| RNF-06 | Recuperación | Deberán definirse mecanismos de respaldo y procedimientos de recuperación de la información. |
| RNF-07 | Compatibilidad | La aplicación deberá ejecutarse en los entornos Windows y las versiones de .NET que se determinen como compatibles con la solución. |
| RNF-08 | Trazabilidad | Los requisitos deberán identificarse mediante códigos únicos y relacionarse con los modelos, las tareas y las pruebas correspondientes. |

Estos requisitos describen objetivos de calidad. Sus criterios específicos de medición deberán definirse y verificarse durante las etapas de diseño y pruebas.

## 8. Restricciones y decisiones técnicas

La propuesta considera las siguientes tecnologías:

| Tecnología | Función dentro de la solución |
|---|---|
| C# | Lenguaje de programación de la aplicación. |
| Windows Forms | Tecnología propuesta para la interfaz de escritorio. |
| .NET | Plataforma de ejecución de la aplicación. |
| SQL Server | Sistema gestor de la base de datos. |
| Visual Studio | Entorno de desarrollo. |
| Git | Control de versiones del proyecto. |
| GitHub | Alojamiento del repositorio y colaboración. |
| GitHub Issues | Registro y seguimiento de tareas, incidencias y riesgos. |
| GitHub Projects | Organización y seguimiento del avance. |

La arquitectura propuesta contempla la separación lógica entre presentación, negocio y acceso a datos.

La selección de estas tecnologías deberá mantenerse coherente con las decisiones de arquitectura y las características de la solución desarrollada.

## 9. Criterios de aceptación

Los criterios de aceptación establecen las condiciones que deberán verificarse para determinar si un requisito se satisface.

Los siguientes criterios generales se aplicarán a las funcionalidades según corresponda:

1. La operación deberá permitir realizar la función descrita en el requisito.
2. Los datos obligatorios deberán validarse antes de completar la operación.
3. Los valores introducidos deberán cumplir las reglas de negocio aplicables.
4. Los resultados deberán presentarse de forma comprensible.
5. Las operaciones que modifiquen información deberán preservar su integridad.
6. Los errores deberán tratarse de manera controlada, evitando mensajes técnicos innecesarios para el usuario.
7. La funcionalidad deberá superar las pruebas definidas para el requisito.

Los criterios específicos deberán ampliarse durante el análisis detallado de cada funcionalidad.

## 10. Trazabilidad de los requisitos

La trazabilidad permite relacionar los requisitos con los elementos del proceso de desarrollo y facilita el análisis del impacto de los cambios.

Para este proyecto, se propone relacionar cada requisito con los siguientes elementos:

- Modelos UML relacionados.
- Componentes de la arquitectura.
- Historias de usuario o tareas de desarrollo.
- Issues de GitHub asociados.
- Casos de prueba correspondientes.

La siguiente tabla presenta una estructura inicial de trazabilidad:

| Código | Área funcional | Elementos relacionados |
|---|---|---|
| RF-01 | Productos | Casos de uso, diseño de la funcionalidad y tareas relacionadas. |
| RF-02 | Precios | Casos de uso, reglas de precios y tareas relacionadas. |
| RF-03 | Inventario | Casos de uso, movimientos de inventario y pruebas correspondientes. |
| RF-04 | Ventas | Casos de uso, flujo de ventas y pruebas correspondientes. |
| RF-05 | Facturación | Casos de uso, diseño de facturación y pruebas correspondientes. |
| RF-06 | Clientes | Casos de uso, estructura de información y tareas relacionadas. |
| RF-07 | Cuentas por cobrar | Casos de uso, reglas de seguimiento y pruebas correspondientes. |
| RF-08 | Pagos | Casos de uso, operaciones de pago y pruebas correspondientes. |

Esta tabla constituye una base para la trazabilidad. Las relaciones definitivas deberán completarse a partir de los modelos UML, los Issues y los casos de prueba efectivamente documentados.

## 11. Gestión de cambios en los requisitos

Los requisitos pueden cambiar como consecuencia de nuevas necesidades, aclaraciones o decisiones de diseño.

Para controlar estos cambios, se propone el siguiente procedimiento:

1. Registrar la solicitud de cambio.
2. Identificar los requisitos afectados.
3. Analizar el impacto en la arquitectura, los modelos UML y las tareas planificadas.
4. Evaluar el esfuerzo y las dependencias relacionadas.
5. Determinar si el cambio será incorporado al alcance del proyecto.
6. Actualizar la documentación correspondiente cuando el cambio sea aprobado.
7. Registrar el seguimiento en GitHub mediante Issues y commits.

Este procedimiento permite mantener un historial de las decisiones y reducir el riesgo de introducir modificaciones sin evaluar sus consecuencias.

## 12. Relación con la arquitectura de software

Los requisitos funcionales y no funcionales sirven como base para definir la arquitectura del sistema.

La arquitectura propuesta por capas distribuye las responsabilidades de la siguiente manera:

- **Capa de presentación:** interacción con los usuarios y visualización de la información.
- **Capa de lógica de negocio:** aplicación de reglas, validaciones y procesamiento de operaciones.
- **Capa de acceso a datos:** comunicación con SQL Server y gestión de las operaciones de persistencia.

Esta separación permite organizar la implementación de las funcionalidades y facilita la identificación de los componentes que deberán modificarse cuando cambie un requisito.

La correspondencia definitiva entre requisitos y componentes deberá verificarse durante el diseño detallado.

## 13. Estado y mantenimiento del documento

Este documento constituye una especificación inicial de requisitos elaborada como parte del proyecto académico Dist. de Pollos Taveras.

Los requisitos aquí definidos representan las necesidades funcionales y técnicas contempladas para la solución propuesta.

El documento deberá actualizarse cuando se aprueben modificaciones en el alcance, se incorporen nuevos requisitos o se identifiquen inconsistencias durante el análisis y diseño.

La versión de la documentación deberá mantenerse coherente con los modelos UML, la arquitectura y el seguimiento del proyecto en GitHub.

## 14. Autoría

**Proyecto:** Dist. de Pollos Taveras

**Asignatura:** Ingeniería de Software I

**Área académica:** Ingeniería de Software

**Institución:** Universidad Abierta para Adultos (UAPA)
