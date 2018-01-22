---
title: "Consideraciones de migración (Entity Framework)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8e4c1b06e5a3a7717b99379fd9bca2c5a8a14a6a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="migration-considerations-entity-framework"></a>Consideraciones de migración (Entity Framework)
[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework proporciona varias ventajas a una aplicación. Una de las más importantes es la capacidad de utilizar el modelo conceptual para separar las estructuras de datos que usa la aplicación del esquema en el origen de datos. De esta forma se pueden realizar más adelante y con facilidad cambios en el modelo de almacenamiento o en el propio origen de datos sin realizar los cambios correspondientes en la aplicación. Para obtener más información acerca de las ventajas del uso de la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], consulte [Introducción a Entity Framework](../../../../../docs/framework/data/adonet/ef/overview.md) y [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Para aprovechar las ventajas de la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], puede migrar una aplicación existente a la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Algunas tareas son comunes a todas las aplicaciones migradas. Estas tareas comunes incluyen actualizar la aplicación para utilizar el [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] empezando con la versión 3.5 Service Pack 1 (SP1) definir los modelos y asignación y configurar Entity Framework. Al migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], se aplican consideraciones adicionales. Estas consideraciones dependen del tipo de aplicación que se migra y de la funcionalidad concreta de la aplicación. Este tema proporciona información para ayudarle a elegir el mejor enfoque que utilizar al actualizar una aplicación existente.  
  
## <a name="general-migration-considerations"></a>Consideraciones generales de la migración  
 Las consideraciones siguientes se aplican al migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
-   Cualquier aplicación que utilice el [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de la versión 3.5 SP1 puede migrarse a Entity Framework, siempre que el proveedor de datos para el origen de datos que se usa la aplicación admita Entity Framework.  
  
-   Entity Framework puede no admitir toda la funcionalidad de un proveedor de origen de datos, aun cuando ese proveedor sí admita Entity Framework.  
  
-   En una aplicación grande o compleja, no es necesario migrar toda la aplicación a Entity Framework a la vez. Sin embargo, cualquier parte de la aplicación que no use Entity Framework aún debe cambiarse cuando el origen de datos cambie.  
  
-   La conexión del proveedor de datos que Entity Framework usa se puede compartir con otras partes de la aplicación porque el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] utiliza los proveedores de datos de [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] para tener acceso al origen de datos. Por ejemplo, Entity Framework utiliza el proveedor SqlClient para tener acceso a una base de datos de SQL Server. Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Tareas de migración comunes  
 La ruta para migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] depende tanto del tipo de aplicación como de la estrategia de acceso a datos existente. Sin embargo, siempre debe realizar las tareas siguientes al migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Todas estas tareas se realizan automáticamente cuando se usan las herramientas de Entity Data Model a partir de [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)]. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
1.  Actualice la aplicación.  
  
     Un proyecto creado con una versión anterior de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] deben actualizarse para usar [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] SP1 y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de la versión 3.5 SP1.  
  
2.  Defina los modelos y la asignación.  
  
     Los archivos de modelo y asignación definen las entidades en el modelo conceptual; las estructuras en el origen de datos, por ejemplo las tablas, los procedimientos almacenados y vistas; y la asignación entre las entidades y estructuras del origen de datos. Para obtener más información, consulte [Cómo: definir manualmente los archivos de asignación y modelo](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  
  
     Los tipos que se definen en el modelo de almacenamiento deben coincidir con el nombre de los objetos en el origen de datos. Si la aplicación existente expone los datos como objetos, debe asegurarse de que las entidades y las propiedades que se definen en el modelo conceptual coincidan con los nombres de estas clases de datos y propiedades existentes. Para obtener más información, consulte [Cómo: personalizar modelado y asignación de archivos para trabajar con objetos personalizados](http://msdn.microsoft.com/library/bb40c4db-0121-4e45-a167-8fb06707a708).  
  
    > [!NOTE]
    >  Entity Data Model Designer se puede utilizar para cambiar el nombre de las entidades en el modelo conceptual de modo que coincidan con los objetos existentes. Para obtener más información, consulte [Entity Data Model Designer](http://msdn.microsoft.com/library/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf).  
  
3.  Defina la cadena de conexión.  
  
     [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] utiliza una cadena de conexión con formato especial al ejecutar las consultas sobre un modelo conceptual. Esta cadena de conexión encapsula la información sobre los archivos de modelo y asignación y la conexión al origen de datos. Para obtener más información, consulte [Cómo: definir la cadena de conexión](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4.  Configure el proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)].  
  
     Las referencias a los ensamblados de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y a los archivos de modelo y asignación se deben agregar al proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]. Puede agregar estos archivos de asignación al proyecto para asegurarse de que se implementan con la aplicación en la ubicación que se indica en la cadena de conexión. Para obtener más información, consulte [Cómo: configurar manualmente un proyecto de Entity Framework](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Consideraciones para las aplicaciones con objetos existentes  
 A partir de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] admite objetos CLR antiguos (POCO), también llamados objetos que ignoran la persistencia. En la mayoría de los casos, los objetos existentes pueden funcionar con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] realizando pequeños cambios. Para obtener más información, consulte [trabajar con entidades POCO](http://msdn.microsoft.com/library/5e0fb82a-b6d1-41a1-b37b-c12db61629d3). También puede migrar una aplicación a la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y utilizar las clases de datos generadas por las herramientas de Entity Framework. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Consideraciones para las aplicaciones que utilizan los proveedores ADO.NET  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]los proveedores, como SqlClient, permiten consultar un origen de datos para devolver datos tabulares. También se pueden cargar datos en un [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] conjunto de datos. La lista siguiente describe las consideraciones para actualizar una aplicación que utiliza un proveedor de [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] existente:  
  
 Muestre los datos tabulares utilizando un lector de datos.  
 Puede considerar ejecutar una [!INCLUDE[esql](../../../../../includes/esql-md.md)] mediante el proveedor de EntityClient y enumerar archivos en el valor devuelto de la consulta <xref:System.Data.EntityClient.EntityDataReader> objeto. Haga esto únicamente si la aplicación muestra los datos tabulares mediante un lector de datos y no requiere los medios proporcionados por [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] con el fin de materializar los datos en los objetos, realizar el seguimiento de los cambios y efectuar las actualizaciones. Puede continuar utilizando el código de acceso a los datos existente que realiza las actualizaciones en el origen de datos, pero puede utilizar la conexión existente a la que se obtiene acceso desde la propiedad <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> de <xref:System.Data.EntityClient.EntityConnection>. Para obtener más información, consulte [proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 Trabaje con objetos DataSet.  
 El [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] proporciona muchas de las mismas funcionalidades que ofrece un objeto DataSet, incluida la persistencia en memoria, seguimiento de cambios, el enlace de datos y serialización de objetos como datos XML. Para obtener más información, consulte [trabajar con objetos](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Si el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] no proporciona la funcionalidad del conjunto de datos necesario para la aplicación, puede seguir aprovechando las ventajas de las consultas LINQ mediante el uso de [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]. Para más información, vea [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Consideraciones para las aplicaciones que enlazan datos a los controles  
 El [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] permite encapsular los datos en un origen de datos, como un conjunto de datos o un [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] datos de control de código fuente y, a continuación, enlazar elementos de la interfaz de usuario a esos controles de datos. La lista siguiente describe las consideraciones del enlace de los controles a los datos de Entity Framework.  
  
 Enlace los datos a los controles.  
 Al consultar el modelo conceptual, el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] devuelve los datos como objetos que son instancias de tipos de entidad. Estos objetos se pueden enlazar directamente a los controles y este enlace admite actualizaciones. Esto significa que los cambios en los datos en un control, como una fila en un <xref:System.Windows.Forms.DataGridView>, automáticamente se guardan en la base de datos cuando el <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> se llama al método.  
  
 Si una aplicación enumera los resultados de una consulta para mostrar los datos en un control de tipo <xref:System.Windows.Forms.DataGridView> o de otro tipo que admite el enlace de datos, puede modificar la aplicación para enlazar el control al resultado de <xref:System.Data.Objects.ObjectQuery%601>.  
  
 Para obtener más información, consulte [enlazar objetos a controles](http://msdn.microsoft.com/library/2fd34855-929b-4303-a91e-4bb69d958f2b).  
  
 Controles de origen de datos de [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].  
 El [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluye un control de origen de datos diseñado para simplificar el enlace de datos en [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] aplicaciones Web. Para obtener más información, consulte [Control del origen de datos de Entity Framework](http://msdn.microsoft.com/library/1f09af00-9578-4744-a029-765710a3c83f).  
  
## <a name="other-considerations"></a>Otras consideraciones  
 Las siguientes son consideraciones que se pueden aplicar al migrar tipos específicos de aplicaciones a Entity Framework.  
  
 Aplicaciones que exponen los servicios de los datos.  
 Los servicios Web y las aplicaciones que se basan en Windows Communication Foundation (WCF) exponen los datos de un origen de datos subyacente utilizando un formato de mensajería de solicitud/respuesta XML. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] admite la serialización de los objetos entidad utilizando la serialización de contratos de datos WCF, XML o binaria. Las serializaciones WCF y binaria admiten ambas la serialización completa de los gráficos de objetos. Para obtener más información, consulte [creación de aplicaciones con N niveles](http://msdn.microsoft.com/library/9439d2ba-6b5f-44e8-be65-8a442d922cbb).  
  
 Aplicaciones que utilizan datos XML.  
 La serialización de objetos permite crear servicios de datos de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Estos servicios proporcionan datos a las aplicaciones que consumen datos XML, como las aplicaciones de Internet basadas en AJAX. En estos casos, considere el uso de [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]. Estos servicios de datos se basan en el Entity Data Model y proporcionan acceso dinámico a datos de la entidad mediante el uso de acciones de Representational State Transfer (REST) HTTP estándar, como GET, PUT y POST. Para obtener más información, consulte [4.5 de servicios de datos de WCF](../../../../../docs/framework/data/wcf/index.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] no admite un tipo de datos XML nativo. Esto significa que cuando una entidad se asigna a una tabla con una columna XML, la propiedad de entidad equivalente para la columna XML es una cadena. Los objetos se pueden desconectar y serializar como XML. Para obtener más información, consulte [serializar objetos](http://msdn.microsoft.com/library/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99).  
  
 Si una aplicación requiere la capacidad de consultar datos XML, todavía puede aprovecharse de las ventajas de las consultas LINQ utilizando LINQ to XML. Para obtener más información, consulte [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 Aplicaciones que mantienen el estado.  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]Las aplicaciones Web con frecuencia deben mantener el estado de una página Web o de una sesión de usuario. Objetos en un <xref:System.Data.Objects.ObjectContext> instancia puede almacenar en el estado de vista de cliente o en el estado de sesión en el servidor y más adelante recuperar y volver a adjuntar a un nuevo contexto de objeto. Para obtener más información, consulte [adjuntar y separar objetos](http://msdn.microsoft.com/library/41d5c1ef-1b78-4502-aa10-7e1438d62d23).  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de implementación](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)  
 [Terminología de Entity Framework](../../../../../docs/framework/data/adonet/ef/terminology.md)
