# Arquitectura del Sistema

**Proyecto:** SDP - Sistema de Distribución de Pollos                                                                                                                            
**Documento:** Especificación de la arquitectura de software                                                         
**Versión:** 1.0

## 1. Introducción

La arquitectura de software constituye una parte fundamental del proceso de diseño de un sistema, ya que permite definir su estructura, identificar los componentes principales y establecer las relaciones entre ellos.

Este documento presenta la arquitectura propuesta para Dist. de Pollos Taveras, un sistema de información orientado a gestionar las operaciones comerciales de una empresa dedicada a la distribución de pollos.

La propuesta establece una organización por capas que permite separar las responsabilidades relacionadas con la presentación de la información, el procesamiento de las reglas de negocio y el acceso a los datos.

Esta separación busca facilitar la comprensión del sistema, favorecer su mantenimiento y establecer una estructura que permita incorporar nuevas funcionalidades de manera organizada.

## 2. Objetivos de la arquitectura

### 2.1. Objetivo general

Definir una arquitectura de software que organice los componentes de SDP (Sistema de Distribución de Pollos) mediante la separación de responsabilidades, facilitando el mantenimiento, la evolución y la gestión de la información del sistema.

### 2.2. Objetivos específicos

- Separar la presentación de la información de las reglas de negocio.
- Centralizar las operaciones relacionadas con el procesamiento de las funcionalidades.
- Organizar el acceso a la base de datos.
- Reducir las dependencias innecesarias entre los componentes.
- Facilitar las pruebas, la detección de errores y el mantenimiento.
- Establecer una estructura que permita ampliar las funcionalidades del sistema.

## 3. Arquitectura seleccionada

Se propone una **arquitectura lógica por capas**, organizada en tres niveles principales:

1. Capa de presentación.
2. Capa de lógica de negocio.
3. Capa de acceso a datos.

SQL Server constituye el sistema gestor de la base de datos utilizado para almacenar y administrar la información.

La arquitectura por capas permite asignar responsabilidades específicas a cada nivel y establecer reglas de comunicación entre ellos.

### 3.1. Justificación de la arquitectura

La selección de esta arquitectura responde a las características del sistema y a la necesidad de organizar sus funcionalidades de forma comprensible y mantenible.

Entre sus principales ventajas se encuentran:

- **Separación de responsabilidades:** cada capa cumple una función específica.
- **Mantenibilidad:** los cambios pueden realizarse en un componente sin modificar innecesariamente los demás.
- **Modularidad:** las funcionalidades pueden organizarse en componentes con responsabilidades definidas.
- **Facilidad de pruebas:** permite evaluar las reglas de negocio y las operaciones de acceso a datos de manera diferenciada.
- **Escalabilidad estructural:** facilita la incorporación de nuevas funcionalidades dentro de la arquitectura existente.

Estas ventajas dependen de que las capas se implementen con límites claros y dependencias controladas.

## 4. Descripción de las capas arquitectónicas

### 4.1. Capa de presentación

La capa de presentación constituye el punto de interacción entre el usuario y el sistema.

Para la solución propuesta, esta capa utiliza C# y Windows Forms como tecnologías de interfaz de escritorio.

Sus responsabilidades principales son:

- Presentar formularios y controles de interacción.
- Capturar los datos introducidos por los usuarios.
- Mostrar productos, clientes, precios y movimientos comerciales.
- Presentar los resultados de las operaciones.
- Comunicar las acciones del usuario a la capa de negocio.
- Mostrar mensajes de validación y notificaciones comprensibles.

Esta capa no debería contener reglas de negocio complejas ni ejecutar directamente operaciones SQL. Su función principal consiste en gestionar la interacción con el usuario y delegar el procesamiento correspondiente.

### 4.2. Capa de lógica de negocio

La capa de lógica de negocio contiene las reglas que determinan cómo deben ejecutarse las operaciones del sistema.

Su propósito es procesar las solicitudes recibidas desde la presentación, aplicar las validaciones correspondientes y coordinar las operaciones necesarias para satisfacer cada funcionalidad.

Entre sus responsabilidades se encuentran:

- Validar las operaciones comerciales.
- Aplicar las reglas relacionadas con productos y precios.
- Coordinar el registro de ventas y facturas.
- Gestionar las reglas de actualización del inventario.
- Procesar las operaciones relacionadas con clientes y cuentas por cobrar.
- Validar las condiciones necesarias para registrar pagos.
- Coordinar las operaciones de acceso a datos.
- Gestionar los resultados y errores de las operaciones.

La lógica de negocio debe mantenerse diferenciada de la interfaz y de los mecanismos concretos utilizados para consultar o modificar la base de datos.

Esta separación facilita la reutilización de las reglas y permite probarlas sin depender directamente de los formularios.

### 4.3. Capa de acceso a datos

La capa de acceso a datos actúa como intermediaria entre la lógica de negocio y el sistema gestor de la base de datos.

Su responsabilidad consiste en ejecutar las operaciones necesarias para consultar, registrar, actualizar y recuperar información.

Entre sus funciones se encuentran:

- Establecer la comunicación con SQL Server.
- Ejecutar consultas y comandos parametrizados.
- Invocar procedimientos almacenados cuando corresponda.
- Recuperar los resultados de las consultas.
- Gestionar las operaciones de persistencia.
- Propagar los errores de acceso a datos para su tratamiento adecuado.
- Evitar que los detalles de conexión y consulta se distribuyan innecesariamente por toda la aplicación.

Esta capa debe proporcionar mecanismos controlados para acceder a los datos, evitando que la presentación dependa directamente de los detalles internos de la base de datos.

### 4.4. Sistema gestor de base de datos

SQL Server constituye el componente responsable de almacenar y administrar la información persistente del sistema.

Entre las entidades de información contempladas se encuentran:

- Productos.
- Clientes.
- Precios.
- Inventario.
- Facturas.
- Pagos.
- Cuentas por cobrar.

La estructura de almacenamiento se define mediante las tablas, relaciones, restricciones y procedimientos almacenados establecidos en el modelo de datos.

La integridad de la información debe protegerse mediante validaciones apropiadas, restricciones de base de datos y transacciones cuando las operaciones lo requieran.

## 5. Diagrama de arquitectura

El siguiente diagrama representa la organización lógica propuesta para el sistema.

```text
┌──────────────────────────────────────────┐
│                  USUARIO                 │
└─────────────────────┬────────────────────┘
                      │
                      ▼
┌──────────────────────────────────────────┐
│          CAPA DE PRESENTACIÓN            │
│                                          │
│            C# - Windows Forms            │
│                                          │
│  Formularios, controles y visualización  │
└─────────────────────┬────────────────────┘
                      │
                Solicitudes
                      │
                      ▼
┌──────────────────────────────────────────┐
│          CAPA DE NEGOCIO                 │
│                                          │
│  Reglas de negocio                       │
│  Validaciones                            │
│  Procesamiento de operaciones            │
│  Coordinación de funcionalidades         │
└─────────────────────┬────────────────────┘
                      │
                Operaciones de datos
                      │
                      ▼
┌──────────────────────────────────────────┐
│          CAPA DE ACCESO A DATOS          │
│                                          │
│  Consultas y comandos                    │
│  Procedimientos almacenados              │
│  Persistencia y recuperación             │
└─────────────────────┬────────────────────┘
                      │
                      ▼
┌──────────────────────────────────────────┐
│                 SQL SERVER               │
│                                          │
│  Tablas, relaciones y restricciones      │
│  Información persistente del sistema     │
└──────────────────────────────────────────┘
```

**Nota:** el diagrama representa una propuesta de organización lógica. No implica que las cuatro partes estén implementadas actualmente como proyectos independientes.

## 6. Flujo de comunicación entre las capas

La interacción entre los componentes se propone de la siguiente manera:

1. El usuario realiza una acción desde la interfaz.
2. La capa de presentación recopila los datos y solicita la operación correspondiente.
3. La capa de negocio valida la solicitud y aplica las reglas correspondientes.
4. Cuando se requiere consultar o modificar información, la capa de negocio solicita la operación a la capa de acceso a datos.
5. La capa de acceso a datos ejecuta la operación correspondiente en SQL Server.
6. SQL Server devuelve los resultados de la operación.
7. La capa de acceso a datos entrega los resultados a la capa de negocio.
8. La capa de negocio procesa el resultado y devuelve una respuesta a la presentación.
9. La interfaz muestra el resultado al usuario.

Este flujo establece una separación entre la interacción, las reglas del sistema y la persistencia de la información.

La comunicación debe realizarse mediante interfaces y contratos definidos, evitando que una capa dependa de detalles internos que corresponden a otra.

## 7. Organización funcional del sistema

La arquitectura debe permitir organizar las funcionalidades de acuerdo con sus responsabilidades.

| Área funcional | Responsabilidad principal |
|---|---|
| Productos | Gestionar la información de los productos. |
| Precios | Administrar los precios asociados a los productos. |
| Inventario | Registrar y consultar los movimientos de inventario. |
| Ventas | Procesar las operaciones de venta. |
| Facturación | Gestionar la información de las facturas. |
| Clientes | Administrar la información de los clientes. |
| Cuentas por cobrar | Consultar facturas pendientes y gestionar su seguimiento. |
| Pagos | Registrar y consultar los pagos realizados. |

Estas áreas representan una organización funcional del dominio del sistema. No implican necesariamente que cada una corresponda a un proyecto, ensamblado o módulo independiente.

## 8. Principios de diseño aplicables

La arquitectura propuesta toma como referencia los siguientes principios de diseño de software.

### 8.1. Separación de responsabilidades

Cada componente debe concentrarse en las tareas que le corresponden, evitando mezclar la presentación, las reglas de negocio y el acceso a datos.

### 8.2. Alta cohesión

Las clases y componentes deben agrupar responsabilidades relacionadas entre sí, facilitando su comprensión y mantenimiento.

### 8.3. Bajo acoplamiento

Las dependencias entre componentes deben mantenerse controladas para reducir el impacto de los cambios.

### 8.4. Encapsulamiento

Los detalles internos de cada componente deben ocultarse cuando no sean necesarios para los demás.

### 8.5. Validación e integridad

Las operaciones deben verificar los datos recibidos y preservar la consistencia de la información almacenada.

Estos principios constituyen criterios de diseño que deberán comprobarse durante la implementación y las revisiones técnicas.

## 9. Tecnologías propuestas

| Tecnología | Responsabilidad |
|---|---|
| C# | Desarrollo de la lógica de la aplicación. |
| Windows Forms | Construcción de la interfaz de escritorio. |
| .NET | Plataforma de ejecución de la aplicación. |
| SQL Server | Gestión y almacenamiento de datos. |
| Visual Studio | Entorno de desarrollo. |
| Git | Control de versiones. |
| GitHub | Alojamiento del repositorio y colaboración. |
| GitHub Issues | Registro y seguimiento de tareas, riesgos e incidencias. |
| GitHub Projects | Organización y seguimiento del avance del proyecto. |

## 10. Consideraciones de seguridad y mantenimiento

La arquitectura deberá contemplar medidas que contribuyan a la protección de la información y a la mantenibilidad del sistema.

Entre las consideraciones principales se encuentran:

- Utilizar consultas parametrizadas para reducir los riesgos de inyección SQL.
- Proteger las credenciales y los datos de conexión.
- Aplicar los permisos necesarios para el acceso a la base de datos.
- Validar las operaciones antes de modificar información persistente.
- Utilizar transacciones cuando una operación requiera mantener la consistencia de varios cambios.
- Registrar los errores de manera que faciliten su diagnóstico.
- Mantener procedimientos de respaldo y recuperación de datos.
- Documentar las modificaciones arquitectónicas relevantes.
- Realizar pruebas de las funcionalidades y sus interacciones.

Estas medidas deberán definirse y verificarse de acuerdo con los requisitos y las características de la implementación.

## 11. Alcance y estado de la propuesta arquitectónica

Este documento presenta la arquitectura lógica propuesta para Dist. de Pollos Taveras como parte del análisis y diseño realizado en la asignatura Ingeniería de Software I.

La arquitectura establece cómo deberían organizarse las responsabilidades de presentación, negocio y acceso a datos.

Su implementación deberá contrastarse con la estructura real del código fuente, las clases existentes y los mecanismos de acceso a SQL Server.

Las futuras modificaciones deberán mantener la coherencia entre los requisitos, los modelos UML, la arquitectura documentada y las decisiones de implementación.

## 12. Conclusión

La arquitectura por capas proporciona una estructura conceptual para organizar SDP de forma modular y comprensible.

La separación entre presentación, lógica de negocio y acceso a datos permite establecer responsabilidades claras y facilita el análisis de las dependencias entre los componentes.

La aplicación consistente de estos principios puede contribuir a mejorar la mantenibilidad del sistema, facilitar las pruebas y proporcionar una base organizada para su evolución.

## 13. Autoría

**Proyecto:** SDP - Sistema de Distribución de Pollos

**Asignatura:** Ingeniería de Software I

**Institución:** Universidad Abierta para Adultos (UAPA)
