---
description: 'Más información acerca de: SqlDependency en una aplicación ASP.NET'
title: SqlDependency en una aplicación ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 686586af834884f97ff8e62fdc792b3cdc23f507
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767029"
---
# <a name="sqldependency-in-an-aspnet-application"></a>SqlDependency en una aplicación ASP.NET

En el ejemplo de esta sección se muestra cómo usar <xref:System.Data.SqlClient.SqlDependency> indirectamente aprovechando el objeto <xref:System.Web.Caching.SqlCacheDependency> de ASP.NET. El objeto <xref:System.Web.Caching.SqlCacheDependency> usa <xref:System.Data.SqlClient.SqlDependency> para escuchar notificaciones y actualizar correctamente la memoria caché.  
  
> [!NOTE]
> En el código de ejemplo se supone que ha habilitado las notificaciones de consulta ejecutando los scripts en [habilitando las notificaciones de consulta](enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>Acerca de la aplicación de ejemplo  

 La aplicación de ejemplo usa una única página web de ASP.NET para mostrar información de producto de la base de datos **AdventureWorks** de SQL Server en un control <xref:System.Web.UI.WebControls.GridView>. Cuando se carga la página, el código escribe la hora actual en un control de <xref:System.Web.UI.WebControls.Label>. A continuación, define un objeto de <xref:System.Web.Caching.SqlCacheDependency> y establece propiedades en el objeto <xref:System.Web.Caching.Cache> para almacenar los datos de la memoria caché durante un máximo de tres minutos. Después, el código se conecta a la base de datos y recupera los datos. Cuando se carga la página y la aplicación se ejecuta, ASP.NET recuperará los datos de la memoria caché, lo cual se puede comprobar observando que la hora de la página no cambia. Si los datos que se supervisan cambian, ASP.NET invalida la memoria caché y vuelve a rellenar el control `GridView` con datos nuevos, actualizando la hora que se muestra en el control `Label`.  
  
## <a name="creating-the-sample-application"></a>Crear la aplicación de ejemplo  

 Siga estos pasos para crear y ejecutar la aplicación de ejemplo:  
  
1. Cree un nuevo sitio web de ASP.NET.  
  
2. Agregue un control <xref:System.Web.UI.WebControls.Label> y <xref:System.Web.UI.WebControls.GridView> a la página Default.aspx.  
  
3. Abra el módulo de clase de la página y agregue las siguientes directivas:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. Agregue el siguiente código en el evento `Page_Load` de la página:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. Agregue dos métodos del asistente, `GetConnectionString` y `GetSQL`. La cadena de conexión definida usa seguridad integrada. Debe comprobar que la cuenta que usa dispone de los permisos de base de datos necesarios y que la base de datos de ejemplo, **AdventureWorks**, tiene habilitadas las notificaciones.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Probar la aplicación  

 La aplicación almacena en caché los datos que se muestran en el formulario web y los actualiza cada tres minutos si no hay ninguna actividad. Si se produce un cambio en la base de datos, la caché se actualiza inmediatamente. Ejecute la aplicación desde Visual Studio, que carga la página en el explorador. La hora de actualización de la caché que se muestra indica cuándo se actualizó la memoria caché por última vez. Espere tres minutos y, a continuación, actualice la página, lo que hará que se produzca un evento de postback. Observe que la hora que se muestra en la página ha cambiado. Si actualiza la página en menos de tres minutos, la hora que se muestra en la página seguirá siendo la misma.  
  
 Ahora, actualice los datos de la base de datos mediante un comando UPDATE de Transact-SQL y actualice la página. La hora que se muestra ahora indica que la memoria caché se ha actualizado con los nuevos datos de la base de datos. Tenga en cuenta que aunque la memoria caché se actualiza, la hora que se muestra en la página no cambia hasta que se produce un evento de postback.  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a>Sincronización de caché distribuida mediante la dependencia de SQL

Algunas de las memorias caché distribuidas de terceros, como [NCache](https://www.alachisoft.com/ncache) , proporcionan compatibilidad para sincronizar la base de datos SQL y la memoria caché mediante la [dependencia de SQL](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html). Para obtener más información y un ejemplo de implementación de código fuente, vea [ejemplo de dependencia SQL de caché distribuida](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).

## <a name="see-also"></a>Vea también

- [Notificaciones de consulta en SQL Server](query-notifications-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
