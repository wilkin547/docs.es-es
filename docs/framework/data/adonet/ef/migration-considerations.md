---
title: "Consideraciones de la migraci&#243;n (Entity Framework) | Microsoft Docs"
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
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Consideraciones de la migraci&#243;n (Entity Framework)
[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework proporciona varias ventajas a una aplicación.  Una de las más importantes es la capacidad de utilizar el modelo conceptual para separar las estructuras de datos que usa la aplicación del esquema en el origen de datos.  De esta forma se pueden realizar más adelante y con facilidad cambios en el modelo de almacenamiento o en el propio origen de datos sin realizar los cambios correspondientes en la aplicación.  Para obtener más información acerca de las ventajas de usar [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], consulte [Información general de Entity Framework](../../../../../docs/framework/data/adonet/ef/overview.md) y [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Para aprovecharse de las ventajas de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], puede migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Algunas tareas son comunes a todas las aplicaciones migradas.  Estas tareas comunes incluyen actualizar la aplicación para utilizar [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de la versión 3.5 Service Pack 1, \(SP1\) definir los modelos y la asignación, y configurar Entity Framework.  Al migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], se aplican consideraciones adicionales.  Estas consideraciones dependen del tipo de aplicación que se migra y de la funcionalidad concreta de la aplicación.  Este tema proporciona información para ayudarle a elegir el mejor enfoque que utilizar al actualizar una aplicación existente.  
  
## Consideraciones generales de la migración  
 Las consideraciones siguientes se aplican al migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
-   Cualquier aplicación que utilice [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de la versión 3.5 SP1 se puede migrar a Entity Framework, siempre que el proveedor de datos para el origen de datos que la aplicación use admita Entity Framework.  
  
-   Entity Framework puede no admitir toda la funcionalidad de un proveedor de origen de datos, aun cuando ese proveedor sí admita Entity Framework.  
  
-   En una aplicación grande o compleja, no es necesario migrar toda la aplicación a Entity Framework a la vez.  Sin embargo, cualquier parte de la aplicación que no use Entity Framework aún debe cambiarse cuando el origen de datos cambie.  
  
-   La conexión del proveedor de datos que Entity Framework usa se puede compartir con otras partes de la aplicación porque el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] utiliza los proveedores de datos de [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] para tener acceso al origen de datos.  Por ejemplo, Entity Framework utiliza el proveedor SqlClient para tener acceso a una base de datos de SQL Server.  Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## Tareas de migración comunes  
 La ruta para migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] depende tanto del tipo de aplicación como de la estrategia de acceso a datos existente.  Sin embargo, siempre debe realizar las tareas siguientes al migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Todas estas tareas se realizan automáticamente cuando se usan las herramientas de Entity Data Model a partir de [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)].  Para obtener más información, consulte [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
1.  Actualice la aplicación.  
  
     Un proyecto creado utilizando una versión anterior de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] se debe actualizar para utilizar [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] SP1 y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de la versión 3.5 SP1.  
  
2.  Defina los modelos y la asignación.  
  
     Los archivos de modelo y asignación definen las entidades en el modelo conceptual; las estructuras en el origen de datos, por ejemplo las tablas, los procedimientos almacenados y vistas; y la asignación entre las entidades y estructuras del origen de datos.  Para obtener más información, consulte [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/es-es/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  
  
     Los tipos que se definen en el modelo de almacenamiento deben coincidir con el nombre de los objetos en el origen de datos.  Si la aplicación existente expone los datos como objetos, debe asegurarse de que las entidades y las propiedades que se definen en el modelo conceptual coincidan con los nombres de estas clases de datos y propiedades existentes.  Para obtener más información, consulte [How to: Customize Modeling and Mapping Files to Work with Custom Objects](http://msdn.microsoft.com/es-es/bb40c4db-0121-4e45-a167-8fb06707a708).  
  
    > [!NOTE]
    >  Entity Data Model Designer se puede utilizar para cambiar el nombre de las entidades en el modelo conceptual de modo que coincidan con los objetos existentes.  Para obtener más información, consulte [Entity Data Model Designer](http://msdn.microsoft.com/es-es/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf).  
  
3.  Defina la cadena de conexión.  
  
     [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] utiliza una cadena de conexión con formato especial al ejecutar las consultas sobre un modelo conceptual.  Esta cadena de conexión encapsula la información sobre los archivos de modelo y asignación y la conexión al origen de datos.  Para obtener más información, consulte [Definir la cadena de conexión](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4.  Configure el proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)].  
  
     Las referencias a los ensamblados de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y a los archivos de modelo y asignación se deben agregar al proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)].  Puede agregar estos archivos de asignación al proyecto para asegurarse de que se implementan con la aplicación en la ubicación que se indica en la cadena de conexión.  Para obtener más información, consulte [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/es-es/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
## Consideraciones para las aplicaciones con objetos existentes  
 A partir de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] admite objetos CLR antiguos \(POCO\), también llamados objetos que ignoran la persistencia.  En la mayoría de los casos, los objetos existentes pueden funcionar con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] realizando pequeños cambios.  Para obtener más información, consulte [Working with POCO Entities](http://msdn.microsoft.com/es-es/5e0fb82a-b6d1-41a1-b37b-c12db61629d3). Puede migrar también una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y utilizar las clases de datos generadas por las herramientas de Entity Framework.  Para obtener más información, consulte [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/es-es/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
## Consideraciones para las aplicaciones que utilizan los proveedores ADO.NET  
 Los proveedores [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)], como SqlClient, permiten consultar un origen de datos para devolver datos tabulares.  Los datos también se pueden cargar en un conjunto de datos de [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)].  La lista siguiente describe las consideraciones para actualizar una aplicación que utiliza un proveedor de [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] existente:  
  
 Muestre los datos tabulares utilizando un lector de datos.  
 Puede considerar ejecutar una consulta de [!INCLUDE[esql](../../../../../includes/esql-md.md)] utilizando el proveedor de EntityClient y enumerando el objeto <xref:System.Data.EntityClient.EntityDataReader> devuelto.  Haga esto únicamente si la aplicación muestra los datos tabulares mediante un lector de datos y no requiere los medios proporcionados por [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] con el fin de materializar los datos en los objetos, realizar el seguimiento de los cambios y efectuar las actualizaciones. Puede continuar utilizando el código de acceso a los datos existente que realiza las actualizaciones en el origen de datos, pero puede utilizar la conexión existente a la que se obtiene acceso desde la propiedad <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> de <xref:System.Data.EntityClient.EntityConnection>.  Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
  
 Trabaje con objetos DataSet.  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] proporcionan muchas de las mismas funcionalidades que ofrece un objeto DataSet, incluida la persistencia en memoria, el seguimiento de cambios, el enlace de datos y la serialización de objetos como datos XML.  Para obtener más información, consulte [Trabajar con objetos](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Si [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] no proporciona la funcionalidad de DataSet que necesita la aplicación, aún se pueden aprovechar las ventajas de las consultas de LINQ mediante [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)].  Para obtener más información, consulte [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## Consideraciones para las aplicaciones que enlazan datos a los controles  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] permite encapsular los datos en un origen de datos, por ejemplo un DataSet o un control de origen de datos de [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)], y a continuación enlazar los elementos de la interfaz de usuario a esos controles de datos.  La lista siguiente describe las consideraciones del enlace de los controles a los datos de Entity Framework.  
  
 Enlace los datos a los controles.  
 Al consultar el modelo conceptual, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] devuelve los datos como objetos que son instancias de tipos de entidad.  Estos objetos se pueden enlazar directamente a los controles. Este enlace admite actualizaciones. Esto significa que los cambios en los datos de un control, por ejemplo en una fila de <xref:System.Windows.Forms.DataGridView>, se guardan automáticamente en la base de datos al llamar al método <xref:System.Data.Objects.ObjectContext.SaveChanges%2A>.  
  
 Si una aplicación enumera los resultados de una consulta para mostrar los datos en un control de tipo <xref:System.Windows.Forms.DataGridView> o de otro tipo que admite el enlace de datos, puede modificar la aplicación para enlazar el control al resultado de <xref:System.Data.Objects.ObjectQuery%601>.  
  
 Para obtener más información, consulte [Binding Objects to Controls](http://msdn.microsoft.com/es-es/2fd34855-929b-4303-a91e-4bb69d958f2b).  
  
 Controles de origen de datos de [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluye un control de origen de datos diseñado para simplificar el enlace de datos en aplicaciones web de [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  Para obtener más información, vea [Control del origen de datos de Entity Framework](../Topic/EntityDataSource%20Web%20Server%20Control%20Overview.md).  
  
## Otras consideraciones  
 Las siguientes son consideraciones que se pueden aplicar al migrar tipos específicos de aplicaciones a Entity Framework.  
  
 Aplicaciones que exponen los servicios de los datos.  
 Los servicios Web y las aplicaciones que se basan en Windows Communication Foundation \(WCF\) exponen los datos de un origen de datos subyacente utilizando un formato de mensajería de solicitud\/respuesta XML.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] admite la serialización de los objetos entidad utilizando la serialización de contratos de datos WCF, XML o binaria.  Las serializaciones WCF y binaria admiten ambas la serialización completa de los gráficos de objetos.  Para obtener más información, consulte [Building N\-Tier Applications](http://msdn.microsoft.com/es-es/9439d2ba-6b5f-44e8-be65-8a442d922cbb).  
  
 Aplicaciones que utilizan datos XML.  
 La serialización de objetos permite crear servicios de datos de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Estos servicios proporcionan datos a las aplicaciones que consumen datos XML, como las aplicaciones de Internet basadas en AJAX.  En estos casos, considere el uso de [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)].  Estos servicios de datos se basan en Entity Data Model y proporcionan acceso dinámico a los datos de entidad a través de acciones HTTP de Transferencia de datos de representación \(REST\) estándar, como GET, PUT y POST.  Para obtener más información, consulte [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md)  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] no admite un tipo de datos XML nativo.  Esto significa que cuando una entidad se asigna a una tabla con una columna XML, la propiedad de entidad equivalente para la columna XML es una cadena.  Los objetos se pueden desconectar y serializar como XML.  Para obtener más información, consulte [Serializing Objects](http://msdn.microsoft.com/es-es/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99).  
  
 Si una aplicación requiere la capacidad de consultar datos XML, todavía puede aprovecharse de las ventajas de las consultas LINQ utilizando LINQ to XML.  Para obtener más información, consulte [LINQ to XML](../../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 Aplicaciones que mantienen el estado.  
 Las aplicaciones web de [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] deben mantener con frecuencia el estado de una página web o de una sesión de usuario.  Los objetos de una instancia de <xref:System.Data.Objects.ObjectContext> pueden almacenarse en el estado de vista del cliente o en el estado de sesión en el servidor, y después recuperarse y se volverse a adjuntar a un nuevo contexto del objeto.  Para obtener más información, consulte [Attaching and Detaching Objects](http://msdn.microsoft.com/es-es/41d5c1ef-1b78-4502-aa10-7e1438d62d23).  
  
## Vea también  
 [Consideraciones de implementación](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)   
 [Terminología de Entity Framework](../../../../../docs/framework/data/adonet/ef/terminology.md)