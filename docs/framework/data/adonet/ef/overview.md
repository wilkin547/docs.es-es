---
title: "Informaci&#243;n general de Entity Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Informaci&#243;n general de Entity Framework
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es un conjunto de tecnologías de ADO.NET que permiten el desarrollo de aplicaciones de software orientadas a datos.  Los arquitectos y programadores de aplicaciones orientadas a datos se han enfrentado a la necesidad de lograr dos objetivos muy diferentes.  Deben modelar las entidades, las relaciones y la lógica de los problemas empresariales que resuelven, y también deben trabajar con los motores de datos que se usan para almacenar y recuperar los datos.  Los datos pueden abarcar varios sistemas de almacenamiento, cada uno con sus propios protocolos; incluso las aplicaciones que funcionan con un único sistema de almacenamiento deben equilibrar los requisitos del sistema de almacenamiento con respecto a los requisitos de escribir un código de aplicación eficaz y fácil de mantener.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] permite a los desarrolladores trabajar con datos en forma de objetos y propiedades específicos del dominio, como clientes y direcciones de cliente, sin tener que preocuparse por las tablas y columnas de la base de datos subyacente donde se almacenan estos datos. Con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], los desarrolladores pueden trabajar en un nivel mayor de abstracción cuando tratan con datos, y pueden crear y mantener aplicaciones orientadas a datos con menos código que en las aplicaciones tradicionales.  Dado que [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es un componente de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)], las aplicaciones de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] se pueden ejecutar en cualquier equipo en el que esté instalado [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de la versión 3.5 SP1.  
  
 Las siguientes secciones de este tema proporcionan más detalles sobre [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
-   [Dar vida a los modelos](#LifeToModels)  
  
-   [Asignar objetos a datos](#MappingObjectsToData)  
  
-   [Obtener acceso a los datos de entidad y cambiarlos](#AccessingData)  
  
-   [Proveedores de datos](#DataProviders)  
  
-   [Herramientas de Entity Data Model](#Tools)  
  
-   [Obtener más información](#LearnMore)  
  
<a name="LifeToModels"></a>   
## Dar vida a los modelos  
 Un enfoque de diseño habitual para crear una aplicación o un servicio consiste en dividir la aplicación o el servicio en tres partes: un modelo de dominio, un modelo lógico y un modelo físico.  El modelo de dominio define las entidades y relaciones del sistema que se está modelando.  El modelo lógico de una base de datos relacional normaliza las entidades y relaciones en tablas con restricciones de claves externas.  El modelo físico abarca las capacidades de un motor de datos determinado especificando los detalles del almacenamiento en forma de particiones e índices.  
  
 Los administradores de bases de datos refinan el modelo físico para mejorar el rendimiento, pero los programadores que escriben el código de la aplicación principalmente se limitan a trabajar con el modelo lógico escribiendo consultas SQL y llamando a procedimientos almacenados.  Los modelos de dominio se suelen usar como una herramienta para capturar y comunicar los requisitos de una aplicación, con frecuencia como diagramas inertes que se ven y se explican en las primeras etapas de un proyecto, y a continuación se abandonan.  Muchos equipos de desarrolladores omiten la creación de un modelo conceptual y comienzan especificando las tablas, columnas y claves en una base de datos relacional.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] da vida a los modelos conceptuales permitiendo a los programadores consultar las entidades y relaciones en el modelo de dominio \(denominado modelo *conceptual* en [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\) al tiempo que se basan en [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] para traducir esas operaciones en los comandos específicos del origen de datos.  Esto libera a las aplicaciones de las dependencias codificadas de forma rígida en un origen de datos determinado.  
  
 Al trabajar con Code First, el modelo conceptual se asigna al modelo de almacenamiento en código.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] puede deducir el modelo conceptual basado en los tipos de objeto y configuraciones adicionales que define.  Los metadatos de asignación se generan durante el tiempo de ejecución basándose en una combinación de cómo se definen los tipos de dominio e información de configuración adicional que se proporciona en código.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] genera la base de datos como sea necesario basándose en los metadatos.  Para obtener más información, vea [Crear y asignar un modelo conceptual](http://go.microsoft.com/fwlink/?LinkID=235382).  
  
 Cuando se trabaja con las Herramientas de Entity Data Model, el modelo conceptual, el modelo de almacenamiento y las asignaciones entre los dos se expresan en esquemas basados en XML y se definen en archivos que tienen extensiones de nombre correspondientes:  
  
-   El lenguaje de definición de esquemas conceptuales \(CSDL\) define el modelo conceptual.  CSDL es la implementación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] del [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  La extensión de archivo es .csdl.  
  
-   El lenguaje de definición de esquemas de almacenamiento \(SSDL\) define el modelo de almacenamiento, que también se denomina modelo lógico.  La extensión de archivo es .ssdl.  
  
-   El lenguaje de especificación de asignaciones \(MSL\) define las asignaciones entre los modelos conceptual y de almacenamiento.  La extensión de archivo es .msl.  
  
 El modelo de almacenamiento y las asignaciones pueden cambiar según sea necesario sin requerir cambios en el modelo conceptual, las clases de datos o el código de la aplicación.  Dado que los modelos de almacenamiento son específicos del proveedor, puede trabajar con un modelo conceptual coherente a través de varios orígenes de datos.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] utiliza estos modelos y archivos de asignación para transformar las operaciones de creación, lectura, actualización y eliminación de las entidades y relaciones del modelo conceptual en las operaciones equivalentes en el origen de datos.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluso permite asignar las entidades del modelo conceptual a los procedimientos almacenados en el origen de datos.  Para obtener más información, consulta [Especificaciones CSDL, SSDL y MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md).  
  
<a name="MappingObjectsToData"></a>   
## Asignar objetos a datos  
 La programación orientada a objetos supone un desafío al interactuar con sistemas de almacenamiento de datos.  Aunque la organización de clases suele reflejar la organización de las tablas de bases de datos relacionales, el ajuste no es perfecto.  Varias tablas normalizadas suelen corresponder a una sola clase y las relaciones entre las clases se representan a menudo de forma diferente a las relaciones entre tablas.  Por ejemplo, para representar el cliente de un pedido de ventas, una clase `Order` podría utilizar una propiedad que contiene una referencia a una instancia de una clase `Customer`, mientras que una fila de la tabla `Order` en una base de datos contiene una columna de clave externa con un valor que corresponde a un valor de clave principal en la tabla `Customer` \(o conjunto de columnas\).  Una clase `Customer` podría tener una propiedad denominada `Orders` que contuviera una colección de instancias de la clase `Order`, mientras que la tabla `Customer` en una base de datos no tiene ninguna columna comparable.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] proporciona a los desarrolladores de software la flexibilidad para representar las relaciones de esta manera, o para modelar más estrechamente las relaciones tal como se representan en la base de datos.  
  
 Las soluciones existentes han intentado cubrir este hueco, que se suele denominar "desigualdad de impedancia", asignando únicamente clases y propiedades orientadas a objetos a las tablas y columnas relacionales.  En lugar de seguir este enfoque tradicional, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] asigna las tablas relacionales, columnas y restricciones FOREIGN KEY de los modelos lógicos a las entidades y relaciones de los modelos conceptuales.  Esto permite una mayor flexibilidad al definir los objetos y optimizar el modelo lógico.  Las herramientas de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] generan clases de datos extensibles según el modelo conceptual.  Se trata de clases parciales que se pueden extender con miembros adicionales que el programador agrega.  De forma predeterminada, las clases que se generan para un modelo conceptual determinado derivan de las clases base que proporcionan servicios para materializar las entidades como objetos y para realizar un seguimiento de los cambios y guardarlos.  Los desarrolladores pueden utilizar estas clases para trabajar con las entidades y relaciones como objetos relacionados mediante asociaciones.  Los desarrolladores también pueden personalizar las clases que se generan para un modelo conceptual. Para obtener más información, vea [Trabajar con objetos](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
<a name="AccessingData"></a>   
## Obtener acceso a los datos de entidad y cambiarlos  
 Como algo más que otra solución de asignación objeto\-relacional, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] trata fundamentalmente de permitir que las aplicaciones obtengan acceso y cambien los datos que están representados como entidades y relaciones en el modelo conceptual. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] usa la información de los archivos del modelo y de asignación para traducir las consultas de objeto con los tipos de entidad que se representan en el modelo conceptual en consultas específicas del origen de datos.  Los resultados de la consulta se materializan en objetos que [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] administra.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] proporciona las maneras siguientes de consultar un modelo conceptual y devolver objetos:  
  
-   [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)]. Proporciona compatibilidad con Language\-Integrated Query \(LINQ\) para consultar los tipos de entidad que se definen en un modelo conceptual.  Para obtener más información, consulta [LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
-   [!INCLUDE[esql](../../../../../includes/esql-md.md)]. Un dialecto de SQL, independiente del almacenamiento, que trabaja directamente con entidades del modelo conceptual y que admite conceptos de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)].  [!INCLUDE[esql](../../../../../includes/esql-md.md)] se utiliza tanto con consultas de objeto como con consultas que se ejecutan utilizando el proveedor EntityClient.  Para obtener más información, consulta [Información general de Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md).  
  
 El [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluye el proveedor de datos de EntityClient.  Este proveedor administra las conexiones, traduce las consultas de entidad en consultas específicas del origen de datos y devuelve un lector de datos que [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] usa para materializar los datos de la entidad en los objetos.  Cuando no se requiere la materialización de los objetos, el proveedor de EntityClient también se puede utilizar como un proveedor de datos [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] estándar habilitando las aplicaciones para ejecutar consultas [!INCLUDE[esql](../../../../../includes/esql-md.md)] y usar el lector de datos de solo lectura devuelto.  Para obtener más información, consulta [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 El diagrama siguiente muestra la arquitectura de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] para el acceso a datos:  
  
 ![Diagrama de arquitectura de Entity Framework](../../../../../docs/framework/data/adonet/ef/media/wd-efarchdiagram.gif "wd\_EFArchDiagram")  
  
 Las herramientas de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] pueden generar una clase derivada de `System.Data.Objects.ObjectContext` o `System.Data.Entity.DbContext` que representa el contenedor de entidades definido en el modelo conceptual.  Este contexto del objeto proporciona los medios para realizar el seguimiento de los cambios y administrar las identidades, la simultaneidad y las relaciones.  Esta clase también expone un método `SaveChanges` que escribe las inserciones, actualizaciones y eliminaciones en el origen de datos.  Al igual que las consultas, estas modificaciones son realizadas bien por los comandos que el sistema genera automáticamente o bien por los procedimientos almacenados que el programador especifica.  
  
<a name="DataProviders"></a>   
## Proveedores de datos  
 El proveedor `EntityClient` extiende el modelo de proveedor de [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] teniendo acceso a los datos en lo que respecta a las entidades conceptuales y relaciones.  Ejecuta consultas que utilizan [!INCLUDE[esql](../../../../../includes/esql-md.md)].  [!INCLUDE[esql](../../../../../includes/esql-md.md)] proporciona el lenguaje de consultas subyacente que permite a `EntityClient` comunicarse con la base de datos.  Para obtener más información, consulta [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluye un proveedor de datos SqlClient actualizado que admite los árboles de comandos canónicos.  Para obtener más información, consulta [SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md).  
  
<a name="Tools"></a>   
## Herramientas de Entity Data Model  
 Junto con el tiempo de ejecución de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] incluye herramientas de asignación y modelado.  Para obtener más información, consulta [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md).  
  
<a name="LearnMore"></a>   
## Obtener más información  
 En los temas siguientes se puede obtener más información sobre [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
 [Introducción](../../../../../docs/framework/data/adonet/ef/getting-started.md)  
 Proporcione información sobre cómo ponerse en marcha y empezar a usar rápidamente [Quickstart](http://msdn.microsoft.com/es-es/0bc534be-789f-4819-b9f6-76e51d961675), que muestra cómo crear una aplicación [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] simple rápidamente.  
  
 [Terminología de Entity Framework](../../../../../docs/framework/data/adonet/ef/terminology.md)  
 Define muchos de los términos incluidos en Entity Data Model y [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] que se usan en la documentación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
 [Recursos de Entity Framework](../../../../../docs/framework/data/adonet/ef/resources.md)  
 Proporciona vínculos a temas conceptuales y vínculos a temas externos y recursos para compilar aplicaciones de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
## Vea también  
 [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)