# Especificación de Requisitos del Sistema

**Proyecto:** SDP - Sistema de Distribución de Pollos  
**Documento:** Especificación de requisitos de software  
**Versión:** 1.0  
**Asignatura:** Ingeniería de Software I  
**Institución:** Universidad Abierta para Adultos (UAPA)

---

## 1. Introducción

El presente documento establece los requisitos funcionales y no funcionales del SDP (Sistema de Distribución de Pollos). Su propósito es definir las funcionalidades principales, las condiciones de funcionamiento y los criterios de aceptación que servirán como referencia para el diseño, la planificación y la evaluación del sistema.

## 2. Propósito del sistema

SDP tiene como propósito organizar y facilitar la gestión de las principales operaciones comerciales relacionadas con la distribución de pollos, permitiendo consultar productos, actualizar precios, controlar las existencias y registrar las ventas.

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

Para este proyecto se identifican los siguientes perfiles:

| Interesado o usuario | Responsabilidad o interés |
|---|---|
| Propietario o administrador | Supervisar las operaciones comerciales y consultar información del negocio. |
| Personal de ventas | Consultar productos y precios, y registrar las operaciones de venta que le correspondan. |
| Personal de inventario | Consultar existencias y registrar los movimientos autorizados. |

Esta identificación constituye una propuesta inicial. Los perfiles definitivos y sus permisos deberán establecerse de acuerdo con las necesidades comerciales.

## 5. Clasificación de los requisitos

Los requisitos se clasifican en dos categorías principales:

### 5.1. Requisitos funcionales

Describen los servicios, operaciones y comportamientos que el sistema debe proporcionar.

### 5.2. Requisitos no funcionales

Establecen las condiciones de calidad, seguridad, rendimiento, mantenimiento y funcionamiento que deberá satisfacer la solución.

Esta clasificación permite analizar las necesidades del sistema desde una perspectiva funcional y técnica.

## 6. Requisitos funcionales

Los requisitos funcionales establecen las principales operaciones que deberá realizar SDP, de acuerdo con las necesidades identificadas.

| Código | Descripción | Prioridad | Criterio de aceptación |
|---|---|---|---|
| RF-01 | Consultar los productos registrados. | Alta | El usuario podrá visualizar los productos disponibles y su información. |
| RF-02 | Actualizar los precios de los productos. | Alta | El administrador podrá modificar los precios y guardar los nuevos valores. |
| RF-03 | Consultar y actualizar el inventario. | Alta | El usuario podrá consultar las existencias y actualizar las cantidades. |
| RF-04 | Registrar las ventas realizadas. | Alta | El usuario podrá registrar productos y cantidades y completar la venta. |
| RF-05| Consultar las cuentas por cobrar pendientes. | Alta | El administrador podrá visualizar las cuentas pendientes y consultar la información correspondiente. |

### 6.1. Dependencias entre requisitos

Las funcionalidades presentan las siguientes relaciones:

| Requisito | Dependencia principal |
|---|---|
| RF-01: Consulta de productos | Información de los productos registrados. |
| RF-02: Actualización de precios | Productos registrados. |
| RF-03: Control de inventario | Productos y existencias registradas. |
| RF-04: Registro de ventas | Productos disponibles, precios y cantidades. |
| RF-05: Consulta de cuentas | Cuentas pendientes y la información correspondiente. |

Estas dependencias deberán considerarse al organizar las funcionalidades y verificar su funcionamiento.

## 7. Requisitos no funcionales

Los requisitos no funcionales establecen las condiciones de seguridad, integridad y usabilidad que deberá cumplir SDP.

| Código | Descripción | Prioridad | Criterio de aceptación |
|---|---|---|---|
| RNF-01 | Requerir autenticación para acceder a las funciones protegidas. | Alta | Los usuarios deberán iniciar sesión para acceder al sistema. |
| RNF-02 | Controlar el acceso según los permisos del usuario. | Alta | Cada usuario podrá acceder únicamente a las funciones autorizadas. |
| RNF-03 | Mantener la integridad de la información almacenada. | Alta | Las operaciones no deberán generar datos duplicados o inconsistentes. |
| RNF-04 | Proporcionar una interfaz sencilla y fácil de utilizar. | Media | Los usuarios podrán realizar las operaciones principales de forma clara y comprensible. |

Estos requisitos permiten establecer condiciones para verificar la seguridad, la consistencia de los datos y la facilidad de uso del sistema.

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
| RF-01 | Productos | HU-01 - Consulta de productos, casos de uso y tareas relacionadas.|
| RF-02 | Precios | HU-02 - Gestión de precios, reglas de precios y tareas relacionadas. |
| RF-03 | Inventario | HU-03 - Control de inventario, movimientos de inventario y pruebas correspondientes. |
| RF-04 | Ventas | HU-04 - Registro de ventas y facturación, flujo de ventas y pruebas correspondientes. |
| RF-05 | Cuentas por cobrar | HU-05 - Gestión de cuentas por cobrar y tareas relacionadas. |


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

Este documento constituye una especificación inicial de requisitos elaborada como parte del proyecto académico.

Los requisitos aquí definidos representan las necesidades funcionales y técnicas contempladas para la solución propuesta.

El documento deberá actualizarse cuando se aprueben modificaciones en el alcance, se incorporen nuevos requisitos o se identifiquen inconsistencias durante el análisis y diseño.

La versión de la documentación deberá mantenerse coherente con los modelos UML, la arquitectura y el seguimiento del proyecto en GitHub.

## 14. Autoría

**Proyecto:** SDP - Sistema de Distribución de Pollos

**Asignatura:** Ingeniería de Software I

**Institución:** Universidad Abierta para Adultos (UAPA)
