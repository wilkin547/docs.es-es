---
title: Consideraciones de migración (Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: 8370156d2bd0f3858d7fa0936fa967a658e6e910
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929309"
---
# <a name="migration-considerations-entity-framework"></a>Consideraciones de migración (Entity Framework)
El Entity Framework ADO.NET proporciona varias ventajas a una aplicación existente. Una de las más importantes es la capacidad de utilizar el modelo conceptual para separar las estructuras de datos que usa la aplicación del esquema en el origen de datos. De esta forma se pueden realizar más adelante y con facilidad cambios en el modelo de almacenamiento o en el propio origen de datos sin realizar los cambios correspondientes en la aplicación. Para obtener más información sobre las ventajas del uso [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]de, vea [información general](../../../../../docs/framework/data/adonet/ef/overview.md) y [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md)de Entity Framework.  
  
 Para aprovechar las ventajas [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]de, puede migrar una aplicación existente [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]a. Algunas tareas son comunes a todas las aplicaciones migradas. Estas tareas comunes incluyen la actualización de la aplicación para usar el .NET Framework a partir de la versión 3,5 Service Pack 1 (SP1), la definición de modelos y la asignación y la configuración del Entity Framework. Al migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], se aplican consideraciones adicionales. Estas consideraciones dependen del tipo de aplicación que se migra y de la funcionalidad concreta de la aplicación. Este tema proporciona información para ayudarle a elegir el mejor enfoque que utilizar al actualizar una aplicación existente.  
  
## <a name="general-migration-considerations"></a>Consideraciones generales de la migración  
 Las consideraciones siguientes se aplican al migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]:  
  
- Cualquier aplicación que use el .NET Framework a partir de la versión 3,5 SP1 se puede migrar al Entity Framework, siempre que el proveedor de datos para el origen de datos utilizado por la aplicación admita la Entity Framework.  
  
- Entity Framework puede no admitir toda la funcionalidad de un proveedor de origen de datos, aun cuando ese proveedor sí admita Entity Framework.  
  
- En una aplicación grande o compleja, no es necesario migrar toda la aplicación a Entity Framework a la vez. Sin embargo, cualquier parte de la aplicación que no use Entity Framework aún debe cambiarse cuando el origen de datos cambie.  
  
- La conexión del proveedor de datos utilizada por el Entity Framework se puede compartir con otras partes de la aplicación [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] porque utiliza proveedores de datos ADO.net para tener acceso al origen de datos. Por ejemplo, Entity Framework utiliza el proveedor SqlClient para tener acceso a una base de datos de SQL Server. Para obtener más información, consulte [proveedor de EntityClient para el Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Tareas de migración comunes  
 La ruta para migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] depende tanto del tipo de aplicación como de la estrategia de acceso a datos existente. Sin embargo, siempre debe realizar las tareas siguientes al migrar una aplicación existente a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
> Todas estas tareas se realizan automáticamente al usar las herramientas de Entity Data Model a partir de Visual Studio 2008. Para obtener más información, consulte [Cómo Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
1. Actualice la aplicación.  
  
     Un proyecto creado con una versión anterior de Visual Studio y el .NET Framework debe actualizarse para usar Visual Studio 2008 SP1 y el .NET Framework a partir de la versión 3,5 SP1.  
  
2. Defina los modelos y la asignación.  
  
     Los archivos de modelo y asignación definen las entidades en el modelo conceptual; las estructuras en el origen de datos, por ejemplo las tablas, los procedimientos almacenados y vistas; y la asignación entre las entidades y estructuras del origen de datos. Para obtener más información, consulte [Cómo Definir manualmente los archivos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))de asignación y de modelo.  
  
     Los tipos que se definen en el modelo de almacenamiento deben coincidir con el nombre de los objetos en el origen de datos. Si la aplicación existente expone los datos como objetos, debe asegurarse de que las entidades y las propiedades que se definen en el modelo conceptual coincidan con los nombres de estas clases de datos y propiedades existentes. Para obtener más información, vea [Cómo: Personalizar el modelado y los archivos de asignación para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738625(v=vs.100))trabajar con objetos personalizados.  
  
    > [!NOTE]
    > Entity Data Model Designer se puede utilizar para cambiar el nombre de las entidades en el modelo conceptual de modo que coincidan con los objetos existentes. Para obtener más información, vea [Diseñador de Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)).  
  
3. Defina la cadena de conexión.  
  
     [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] utiliza una cadena de conexión con formato especial al ejecutar las consultas sobre un modelo conceptual. Esta cadena de conexión encapsula la información sobre los archivos de modelo y asignación y la conexión al origen de datos. Para obtener más información, consulte [Cómo Defina la cadena](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)de conexión.  
  
4. Configure el proyecto de Visual Studio.  
  
     Las referencias [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] a los ensamblados y los archivos de asignación y de modelo se deben agregar al proyecto de Visual Studio. Puede agregar estos archivos de asignación al proyecto para asegurarse de que se implementan con la aplicación en la ubicación que se indica en la cadena de conexión. Para obtener más información, consulte [Cómo Configurar manualmente un proyecto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))de Entity Framework.  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Consideraciones para las aplicaciones con objetos existentes  
 A partir de la .NET Framework 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] admite objetos CLR "antiguos sin formato" (poco), también denominados objetos que ignoran la persistencia. En la mayoría de los casos, los objetos existentes pueden funcionar con [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] realizando pequeños cambios. Para obtener más información, vea [trabajar con entidades poco](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100)). También puede migrar una aplicación a [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y utilizar las clases de datos generadas por las herramientas de Entity Framework. Para obtener más información, consulte [Cómo Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Consideraciones para las aplicaciones que utilizan los proveedores ADO.NET  
 Los proveedores de ADO.NET, como SqlClient, permiten consultar un origen de datos para devolver datos tabulares. Los datos también se pueden cargar en un conjunto de datos de ADO.NET. En la lista siguiente se describen las consideraciones para actualizar una aplicación que usa un proveedor de ADO.NET existente:  
  
- Muestre los datos tabulares utilizando un lector de datos.  

  Puede considerar la posibilidad de ejecutar [!INCLUDE[esql](../../../../../includes/esql-md.md)] una consulta con el proveedor de EntityClient y enumerarla a <xref:System.Data.EntityClient.EntityDataReader> través del objeto devuelto. Haga esto únicamente si la aplicación muestra los datos tabulares mediante un lector de datos y no requiere los medios proporcionados por [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] con el fin de materializar los datos en los objetos, realizar el seguimiento de los cambios y efectuar las actualizaciones. Puede continuar utilizando el código de acceso a los datos existente que realiza las actualizaciones en el origen de datos, pero puede utilizar la conexión existente a la que se obtiene acceso desde la propiedad <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> de <xref:System.Data.EntityClient.EntityConnection>. Para obtener más información, consulte [proveedor de EntityClient para el Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
- Trabaje con objetos DataSet.  

  Proporciona [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] muchas de las mismas funcionalidades proporcionadas por el conjunto de datos, incluida la persistencia en memoria, el seguimiento de los cambios, el enlace de datos y la serialización de objetos como datos XML. Para obtener más información, vea [trabajar con objetos](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Si no proporciona la funcionalidad del conjunto de cambios que la aplicación necesita, puede aprovechar las ventajas de las consultas LINQ mediante el uso de LINQ to DataSet. Para más información, vea [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Consideraciones para las aplicaciones que enlazan datos a los controles  
 El .NET Framework permite encapsular los datos en un origen de datos, como un conjunto de datos o un control de origen de datos ASP.NET y, a continuación, enlazar los elementos de la interfaz de usuario a esos controles de datos. La lista siguiente describe las consideraciones del enlace de los controles a los datos de Entity Framework.  
  
- Enlace los datos a los controles.  

  Al consultar el modelo conceptual, el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] objeto devuelve los datos como objetos que son instancias de tipos de entidad. Estos objetos se pueden enlazar directamente a los controles y este enlace admite actualizaciones. Esto significa que los cambios en los datos de un control, como una fila de <xref:System.Windows.Forms.DataGridView>, se guardan automáticamente en la base de <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> datos cuando se llama al método.  
  
  Si una aplicación enumera los resultados de una consulta para mostrar los datos en un control de tipo <xref:System.Windows.Forms.DataGridView> o de otro tipo que admite el enlace de datos, puede modificar la aplicación para enlazar el control al resultado de <xref:System.Data.Objects.ObjectQuery%601>.  
  
  Para obtener más información, vea [enlazar objetos a controles](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738469(v=vs.100)).  
  
- Controles de origen de datos ASP.NET.  

  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Incluye un control de origen de datos diseñado para simplificar el enlace de datos en las aplicaciones Web de ASP.net. Para obtener más información, vea [información general sobre el control de servidor Web EntityDataSource](https://docs.microsoft.com/previous-versions/aspnet/cc488502(v=vs.100)).  
  
## <a name="other-considerations"></a>Otras consideraciones  
 Las siguientes son consideraciones que se pueden aplicar al migrar tipos específicos de aplicaciones a Entity Framework.  
  
- Aplicaciones que exponen los servicios de los datos.  

  Los servicios Web y las aplicaciones que se basan en Windows Communication Foundation (WCF) exponen los datos de un origen de datos subyacente utilizando un formato de mensajería de solicitud/respuesta XML. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] admite la serialización de los objetos entidad utilizando la serialización de contratos de datos WCF, XML o binaria. Las serializaciones WCF y binaria admiten ambas la serialización completa de los gráficos de objetos. Para obtener más información, vea compilar [aplicaciones de N niveles](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896304(v=vs.100)).  
  
- Aplicaciones que utilizan datos XML.  

  La serialización de objetos permite crear servicios de datos de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Estos servicios proporcionan datos a las aplicaciones que consumen datos XML, como las aplicaciones de Internet basadas en AJAX. En estos casos, considere el uso de [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]. Estos servicios de datos se basan en el Entity Data Model y proporcionan acceso dinámico a los datos de la entidad mediante acciones HTTP de transferencia de estado de representación (REST) estándar, como GET, PUT y POST. Para obtener más información, vea [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md).  
  
  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] no admite un tipo de datos XML nativo. Esto significa que cuando una entidad se asigna a una tabla con una columna XML, la propiedad de entidad equivalente para la columna XML es una cadena. Los objetos se pueden desconectar y serializar como XML. Para obtener más información, vea [serializar objetos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
  Si una aplicación requiere la capacidad de consultar datos XML, todavía puede aprovecharse de las ventajas de las consultas LINQ utilizando LINQ to XML. Para obtener más información, vea [LINQ to XMLC#()](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) o [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
- Aplicaciones que mantienen el estado.  

  Las aplicaciones Web de ASP.NET deben mantener con frecuencia el estado de una página web o de una sesión de usuario. Los objetos de <xref:System.Data.Objects.ObjectContext> una instancia de pueden almacenarse en el estado de vista de cliente o en el estado de sesión en el servidor y, posteriormente, recuperarse y volver a adjuntarse a un nuevo contexto de objeto. Para obtener más información, vea adjuntar [y separar objetos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896271(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- [Consideraciones de implementación](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)
- [Terminología de Entity Framework](../../../../../docs/framework/data/adonet/ef/terminology.md)
