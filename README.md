# SDP - Sistema de Distribución de Pollos
## 1. Descripción del proyecto

SDP (Sistema de Distribución de Pollos) es un proyecto de desarrollo de software orientado al diseño de una solución informática para organizar y gestionar las operaciones comerciales relacionadas con la distribución de pollos.

La propuesta contempla la administración de productos, precios, inventario, ventas, facturación, clientes, pagos y cuentas por cobrar.

El proyecto aborda las distintas actividades del proceso de desarrollo de software, incluyendo el análisis de requisitos, el modelado mediante UML, el diseño arquitectónico, la gestión de tareas, la identificación de riesgos y el control de versiones.

Como parte de la asignatura Ingeniería de Software I, se utiliza GitHub para centralizar la documentación, registrar los cambios y organizar el seguimiento de las actividades del proyecto.

## 2. Problema que se busca resolver

La gestión comercial de las empresas dedicadas a la distribución de pollos requiere mantener información organizada sobre sus productos, precios, existencias, ventas, facturas y pagos.

La falta de una estructura adecuada para administrar esta información puede provocar inconsistencias en los registros, dificultades para consultar datos y problemas para dar seguimiento a las operaciones pendientes.

SDP propone una solución informática que permita centralizar la información comercial y facilitar su administración mediante funcionalidades organizadas de acuerdo con las necesidades de este sector comercial.

## 3. Objetivos del proyecto

### 3.1. Objetivo general

Diseñar una solución informática para la gestión de las principales operaciones comerciales de las distribuidoras de pollos, aplicando principios de ingeniería de software para organizar los requisitos, definir la arquitectura, modelar las funcionalidades y establecer mecanismos de seguimiento y control del desarrollo.

### 3.2. Objetivos específicos

- Identificar y documentar los requisitos funcionales y no funcionales.
- Representar las funcionalidades y la estructura del sistema mediante modelos UML.
- Definir una propuesta arquitectónica basada en la separación de responsabilidades.
- Identificar los componentes necesarios para gestionar la información comercial.
- Organizar las actividades y los riesgos mediante GitHub Issues y GitHub Projects.
- Aplicar el control de versiones para registrar los cambios en la documentación.
- Mantener la trazabilidad entre los requisitos, los modelos, la arquitectura y las tareas del proyecto.

## 4. Alcance funcional

El sistema contempla las siguientes áreas funcionales:

- **Gestión de productos:** administración de la información de los productos.
- **Gestión de precios:** administración de los precios asociados a los productos.
- **Control de inventario:** registro y consulta de movimientos de inventario.
- **Registro de ventas:** organización de las operaciones comerciales.
- **Facturación:** gestión de la información de las facturas.
- **Gestión de clientes:** administración de la información de los clientes.
- **Cuentas por cobrar:** seguimiento de facturas pendientes y abonos.
- **Gestión de pagos:** registro y consulta de pagos.

El alcance definitivo de cada funcionalidad deberá corresponder con los requisitos establecidos y con las características verificadas de la implementación.

## 5. Arquitectura del sistema

Se propone una arquitectura lógica por capas para separar las responsabilidades de presentación, procesamiento de las reglas de negocio y acceso a los datos.

La solución contempla las siguientes capas:

1. **Capa de presentación:** gestiona la interacción con el usuario mediante formularios y controles.
2. **Capa de lógica de negocio:** procesa las operaciones y aplica las reglas y validaciones correspondientes.
3. **Capa de acceso a datos:** gestiona las consultas y modificaciones de información en la base de datos.

SQL Server actúa como sistema gestor de la base de datos.

La separación de responsabilidades busca facilitar el mantenimiento, reducir las dependencias innecesarias y permitir una evolución organizada del sistema.

La arquitectura descrita constituye una propuesta de diseño cuya correspondencia con la implementación deberá verificarse mediante la revisión del código fuente.

Para consultar la documentación detallada, véase [Arquitectura del Sistema](docs/arquitectura/Arquitectura-del-Sistema.md).

## 6. Organización del frontend y backend

### 6.1. Frontend: capa de presentación

La interfaz de usuario se plantea mediante C# y Windows Forms.

Sus responsabilidades principales son:

- Presentar los formularios y controles.
- Recibir los datos introducidos por el usuario.
- Mostrar los resultados de las operaciones.
- Facilitar la consulta de información comercial.
- Comunicar las solicitudes a la lógica de negocio.

### 6.2. Backend: lógica de negocio y acceso a datos

El backend comprende las responsabilidades relacionadas con el procesamiento de las operaciones y la gestión del acceso a la información.

Sus funciones incluyen:

- Validar los datos recibidos.
- Aplicar las reglas de negocio.
- Procesar las operaciones comerciales.
- Coordinar las consultas y modificaciones de información.
- Gestionar la comunicación con SQL Server.

### 6.3. Comunicación entre los componentes

El flujo de comunicación propuesto es el siguiente:

1. El usuario realiza una acción desde la interfaz.
2. La capa de presentación envía la solicitud correspondiente.
3. La lógica de negocio valida y procesa la operación.
4. La capa de acceso a datos ejecuta las operaciones necesarias en SQL Server.
5. Los resultados regresan a la lógica de negocio.
6. La presentación muestra el resultado al usuario.

Esta organización representa una separación lógica de responsabilidades dentro de una aplicación de escritorio. No presupone la existencia de una API independiente ni de servicios desplegados por separado.

## 7. Herramientas y tecnologías

| Herramienta o tecnología | Aplicación en el proyecto |
|---|---|
| C# | Lenguaje de programación. |
| Windows Forms | Tecnología de interfaz de escritorio. |
| .NET | Plataforma de ejecución. |
| SQL Server | Sistema gestor de base de datos. |
| Visual Studio | Entorno de desarrollo. |
| Git | Control de versiones. |
| GitHub | Alojamiento del repositorio y colaboración. |
| GitHub Issues | Registro y seguimiento de tareas, riesgos e incidencias. |
| GitHub Projects | Organización y seguimiento del avance. |
| UML | Modelado de funcionalidades, estructura e interacciones del sistema. |

## 8. Organización del repositorio

El repositorio se organiza para facilitar la consulta de los documentos técnicos y las evidencias elaboradas durante el proyecto.

```text
Dist.-de-Pollos-Taveras/
│
├── README.md
│
*── docs/
     ├── requisitos/
     │   └── Requisitos-del-Sistema.md
     │
     ├── uml/
     │   ├── diagrama-actividades.jpg
     │   ├── diagrama-casos-de-uso.jpg
     │   ├── diagrama-clases.jpg
     │   ├── diagrama-componentes.jpg
     │   └── diagrama-secuencia.jpg
     │
     ├── arquitectura/
     │   └── Arquitectura-del-Sistema.md
     │
     └── gestion-proyecto/


```

## 9. Control de versiones y seguimiento

Git y GitHub se utilizan para mantener un historial de los cambios registrados en el repositorio.

GitHub Issues permite documentar incidencias, riesgos, mejoras y tareas pendientes. GitHub Projects facilita la organización de las actividades según su estado de avance.

Estas herramientas contribuyen a mantener la trazabilidad de las tareas y a documentar la evolución del proyecto.

## 10. Estado actual del proyecto

El repositorio se encuentra en proceso de organización y documentación de las evidencias técnicas correspondientes al proyecto.

Las actividades de cierre incluyen:

- Organización de los requisitos del sistema.
- Incorporación de los modelos UML.
- Documentación de la arquitectura.
- Actualización del README.
- Registro de los avances realizados.
- Selección de Issues relevantes para el seguimiento.
- Revisión del tablero de GitHub Projects.
- Elaboración de la nota técnica de versión.

El estado de implementación de las funcionalidades y de cada actividad se actualizará de acuerdo con las evidencias verificadas en el repositorio.

## 11. Próximos pasos

- Completar la organización de la documentación técnica.
- Incorporar los requisitos y modelos UML elaborados.
- Documentar la arquitectura del sistema.
- Revisar y actualizar los Issues y el tablero de seguimiento.
- Registrar los cambios relevantes en Git.
- Preparar una nota técnica que identifique el contenido de la versión y las actividades pendientes.

## 12. Autoría

**Proyecto:** SDP - Sistema de Distribución de Pollos                                                                                                                                
**Área académica:** Ingeniería de Software  
**Institución:** Universidad Abierta para Adultos (UAPA)

---
