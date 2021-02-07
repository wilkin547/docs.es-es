---
description: 'Más información acerca de: consideraciones sobre la migración (Entity Framework)'
title: Consideraciones de migración (Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: 6824d28fecc743e17046c826b887900218c90f3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739253"
---
# <a name="migration-considerations-entity-framework"></a>Consideraciones de migración (Entity Framework)

El Entity Framework ADO.NET proporciona varias ventajas a una aplicación existente. Una de las más importantes es la capacidad de utilizar el modelo conceptual para separar las estructuras de datos que usa la aplicación del esquema en el origen de datos. De esta forma se pueden realizar más adelante y con facilidad cambios en el modelo de almacenamiento o en el propio origen de datos sin realizar los cambios correspondientes en la aplicación. Para obtener más información acerca de las ventajas de usar el Entity Framework, consulte [Entity Framework información general](overview.md) y [Entity Data Model](../entity-data-model.md).  
  
 Para aprovechar las ventajas de los Entity Framework, puede migrar una aplicación existente a la Entity Framework. Algunas tareas son comunes a todas las aplicaciones migradas. Estas tareas comunes incluyen la actualización de la aplicación para usar el .NET Framework a partir de la versión 3,5 Service Pack 1 (SP1), la definición de modelos y la asignación y la configuración del Entity Framework. Al migrar una aplicación al Entity Framework, existen consideraciones adicionales que se aplican. Estas consideraciones dependen del tipo de aplicación que se migra y de la funcionalidad concreta de la aplicación. Este tema proporciona información para ayudarle a elegir el mejor enfoque que utilizar al actualizar una aplicación existente.  
  
## <a name="general-migration-considerations"></a>Consideraciones generales de la migración  

 Las consideraciones siguientes se aplican al migrar cualquier aplicación a la Entity Framework:  
  
- Cualquier aplicación que use el .NET Framework a partir de la versión 3,5 SP1 se puede migrar al Entity Framework, siempre que el proveedor de datos para el origen de datos utilizado por la aplicación admita la Entity Framework.  
  
- Entity Framework puede no admitir toda la funcionalidad de un proveedor de origen de datos, aun cuando ese proveedor sí admita Entity Framework.  
  
- En una aplicación grande o compleja, no es necesario migrar toda la aplicación a Entity Framework a la vez. Sin embargo, cualquier parte de la aplicación que no use Entity Framework aún debe cambiarse cuando el origen de datos cambie.  
  
- La conexión del proveedor de datos utilizada por el Entity Framework se puede compartir con otras partes de la aplicación porque el Entity Framework utiliza proveedores de datos ADO.NET para tener acceso al origen de datos. Por ejemplo, Entity Framework utiliza el proveedor SqlClient para tener acceso a una base de datos de SQL Server. Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Tareas de migración comunes  

 La ruta de acceso para migrar una aplicación existente al Entity Framework depende tanto del tipo de aplicación como de la estrategia de acceso a datos existente. Sin embargo, siempre debe realizar las siguientes tareas al migrar una aplicación existente al Entity Framework.  
  
> [!NOTE]
> Todas estas tareas se realizan automáticamente al usar las herramientas de Entity Data Model a partir de Visual Studio 2008. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
1. Actualice la aplicación.  
  
     Un proyecto creado con una versión anterior de Visual Studio y el .NET Framework debe actualizarse para usar Visual Studio 2008 SP1 y el .NET Framework a partir de la versión 3,5 SP1.  
  
2. Defina los modelos y la asignación.  
  
     Los archivos de modelo y asignación definen las entidades en el modelo conceptual; las estructuras en el origen de datos, por ejemplo las tablas, los procedimientos almacenados y vistas; y la asignación entre las entidades y estructuras del origen de datos. Para obtener más información, vea [Cómo: definir manualmente los archivos de asignación y de modelo](/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).  
  
     Los tipos que se definen en el modelo de almacenamiento deben coincidir con el nombre de los objetos en el origen de datos. Si la aplicación existente expone los datos como objetos, debe asegurarse de que las entidades y las propiedades que se definen en el modelo conceptual coincidan con los nombres de estas clases de datos y propiedades existentes. Para obtener más información, vea [Cómo: personalizar el modelado y la asignación de archivos para trabajar con objetos personalizados](/previous-versions/dotnet/netframework-4.0/bb738625(v=vs.100)).  
  
    > [!NOTE]
    > Entity Data Model Designer se puede utilizar para cambiar el nombre de las entidades en el modelo conceptual de modo que coincidan con los objetos existentes. Para obtener más información, vea [Diseñador de Entity Data Model](/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)).  
  
3. Defina la cadena de conexión.  
  
     El Entity Framework usa una cadena de conexión con formato especial al ejecutar las consultas en un modelo conceptual. Esta cadena de conexión encapsula la información sobre los archivos de modelo y asignación y la conexión al origen de datos. Para obtener más información, consulte [Cómo: definir la cadena de conexión](how-to-define-the-connection-string.md).  
  
4. Configure el proyecto de Visual Studio.  
  
     Las referencias a los ensamblados de Entity Framework y los archivos de asignación y de modelo se deben agregar al proyecto de Visual Studio. Puede agregar estos archivos de asignación al proyecto para asegurarse de que se implementan con la aplicación en la ubicación que se indica en la cadena de conexión. Para obtener más información, consulte [Cómo: configurar manualmente un proyecto de Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Consideraciones para las aplicaciones con objetos existentes  

 A partir de la .NET Framework 4, el Entity Framework admite objetos CLR "antiguos sin formato" (POCO), también denominados objetos que ignoran la persistencia. En la mayoría de los casos, los objetos existentes pueden trabajar con el Entity Framework realizando cambios menores. Para obtener más información, vea [trabajar con entidades poco](/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100)). También puede migrar una aplicación a la Entity Framework y usar las clases de datos generadas por las herramientas de Entity Framework. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Consideraciones para las aplicaciones que utilizan los proveedores ADO.NET  

 Los proveedores de ADO.NET, como SqlClient, permiten consultar un origen de datos para devolver datos tabulares. Los datos también se pueden cargar en un conjunto de datos de ADO.NET. En la lista siguiente se describen las consideraciones para actualizar una aplicación que usa un proveedor de ADO.NET existente:  
  
- Muestre los datos tabulares utilizando un lector de datos.  

  Puede considerar la posibilidad de ejecutar una [!INCLUDE[esql](../../../../../includes/esql-md.md)] consulta con el proveedor de EntityClient y enumerarla a través del objeto devuelto <xref:System.Data.EntityClient.EntityDataReader> . Haga esto solo si la aplicación muestra datos tabulares mediante un lector de datos y no requiere los medios proporcionados por el Entity Framework para materializar los datos en los objetos, realizar el seguimiento de los cambios y realizar actualizaciones. Puede continuar utilizando el código de acceso a los datos existente que realiza las actualizaciones en el origen de datos, pero puede utilizar la conexión existente a la que se obtiene acceso desde la propiedad <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A> de <xref:System.Data.EntityClient.EntityConnection>. Para obtener más información, consulte [Proveedor de EntityClient para Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
- Trabaje con objetos DataSet.  

  El Entity Framework proporciona muchas de las mismas funcionalidades proporcionadas por el conjunto de datos, incluida la persistencia en memoria, el seguimiento de los cambios, el enlace de datos y la serialización de objetos como datos XML. Para obtener más información, vea [trabajar con objetos](working-with-objects.md).  
  
  Si el Entity Framework no proporciona la funcionalidad del conjunto de cambios que la aplicación necesita, puede aprovechar las ventajas de las consultas LINQ mediante LINQ to DataSet. Para más información, vea [LINQ to DataSet](../linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Consideraciones para las aplicaciones que enlazan datos a los controles  

 El .NET Framework permite encapsular los datos en un origen de datos, como un conjunto de datos o un control de origen de datos ASP.NET y, a continuación, enlazar los elementos de la interfaz de usuario a esos controles de datos. La lista siguiente describe las consideraciones del enlace de los controles a los datos de Entity Framework.  
  
- Enlace los datos a los controles.  

  Al consultar el modelo conceptual, el Entity Framework devuelve los datos como objetos que son instancias de tipos de entidad. Estos objetos se pueden enlazar directamente a los controles. Este enlace admite actualizaciones. Esto significa que los cambios en los datos de un control, como una fila de <xref:System.Windows.Forms.DataGridView> , se guardan automáticamente en la base de datos cuando <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> se llama al método.  
  
  Si una aplicación enumera los resultados de una consulta para mostrar los datos en un control de tipo <xref:System.Windows.Forms.DataGridView> o de otro tipo que admite el enlace de datos, puede modificar la aplicación para enlazar el control al resultado de <xref:System.Data.Objects.ObjectQuery%601>.  
  
  Para obtener más información, vea [enlazar objetos a controles](/previous-versions/dotnet/netframework-4.0/bb738469(v=vs.100)).  
  
- Controles de origen de datos ASP.NET.  

  El Entity Framework incluye un control de origen de datos diseñado para simplificar el enlace de datos en las aplicaciones Web de ASP.NET. Para obtener más información, vea [información general sobre el control de servidor Web EntityDataSource](/previous-versions/aspnet/cc488502(v=vs.100)).  
  
## <a name="other-considerations"></a>Otras consideraciones  

 Las siguientes son consideraciones que se pueden aplicar al migrar tipos específicos de aplicaciones a Entity Framework.  
  
- Aplicaciones que exponen los servicios de los datos.  

  Los servicios Web y las aplicaciones que se basan en Windows Communication Foundation (WCF) exponen los datos de un origen de datos subyacente utilizando un formato de mensajería de solicitud/respuesta XML. El Entity Framework admite la serialización de objetos entidad mediante la serialización binaria, XML o de contrato de datos de WCF. Las serializaciones WCF y binaria admiten ambas la serialización completa de los gráficos de objetos. Para obtener más información, vea [compilar aplicaciones de N niveles](/previous-versions/dotnet/netframework-4.0/bb896304(v=vs.100)).  
  
- Aplicaciones que utilizan datos XML.  

  La serialización de objetos permite crear Entity Framework Data Services. Estos servicios proporcionan datos a las aplicaciones que consumen datos XML, como las aplicaciones de Internet basadas en AJAX. En estos casos, considere la posibilidad de usar Servicios de datos de WCF. Estos servicios de datos se basan en Entity Data Model y proporcionan acceso dinámico a los datos de entidad a través de acciones HTTP de Transferencia de datos de representación (REST) estándar, como GET, PUT y POST. Para obtener más información, vea [WCF Data Services 4.5](../../wcf/index.md).  
  
  El Entity Framework no admite un tipo de datos XML nativo. Esto significa que cuando una entidad se asigna a una tabla con una columna XML, la propiedad de entidad equivalente para la columna XML es una cadena. Los objetos se pueden desconectar y serializar como XML. Para obtener más información, vea [serializar objetos](/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
  Si una aplicación requiere la capacidad de consultar datos XML, todavía puede aprovecharse de las ventajas de las consultas LINQ utilizando LINQ to XML. Para obtener más información, vea [LINQ to XML (C#)](../../../../standard/linq/linq-xml-overview.md) o [LINQ to XML (Visual Basic)](../../../../standard/linq/linq-xml-overview.md).  
  
- Aplicaciones que mantienen el estado.  

  Las aplicaciones Web de ASP.NET deben mantener con frecuencia el estado de una página web o de una sesión de usuario. Los objetos de una <xref:System.Data.Objects.ObjectContext> instancia de pueden almacenarse en el estado de vista de cliente o en el estado de sesión en el servidor y, posteriormente, recuperarse y volver a adjuntarse a un nuevo contexto de objeto. Para obtener más información, vea [adjuntar y separar objetos](/previous-versions/dotnet/netframework-4.0/bb896271(v=vs.100)).  
  
## <a name="see-also"></a>Vea también

- [Consideraciones de implementación](deployment-considerations.md)
- [Terminología de Entity Framework](terminology.md)
