---
title: "Ejecución de SqlCommand Execution con SqlNotificationRequest"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fee008d0b1f278a48eacd8eae70d75bbbfd93691
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="c7e87-102">Ejecución de SqlCommand Execution con SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="c7e87-102">SqlCommand Execution with a SqlNotificationRequest</span></span>
<span data-ttu-id="c7e87-103">Los objetos <xref:System.Data.SqlClient.SqlCommand> se pueden configurar para generar una notificación si, después de capturar datos del servidor, éstos generasen un conjunto de resultados diferente en caso de que se ejecutase de nuevo la consulta.</span><span class="sxs-lookup"><span data-stu-id="c7e87-103">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="c7e87-104">Esto resulta útil si desea usar colas de notificaciones personalizadas en el servidor o si no desea mantener objetos activos.</span><span class="sxs-lookup"><span data-stu-id="c7e87-104">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>  
  
## <a name="creating-the-notification-request"></a><span data-ttu-id="c7e87-105">Crear la solicitud de notificación</span><span class="sxs-lookup"><span data-stu-id="c7e87-105">Creating the Notification Request</span></span>  
 <span data-ttu-id="c7e87-106">Puede utilizar un objeto <xref:System.Data.Sql.SqlNotificationRequest> para crear la solicitud de notificación mediante su enlace a un objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="c7e87-106">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="c7e87-107">Después de crear la solicitud, ya no necesitará el objeto `SqlNotificationRequest`.</span><span class="sxs-lookup"><span data-stu-id="c7e87-107">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="c7e87-108">Puede consultar las notificaciones en la cola y responder de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="c7e87-108">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="c7e87-109">Las notificaciones se pueden producir incluso si la aplicación se apaga y posteriormente se reinicia.</span><span class="sxs-lookup"><span data-stu-id="c7e87-109">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>  
  
 <span data-ttu-id="c7e87-110">Cuando se ejecuta el comando con las notificaciones asociadas, los cambios en el conjunto de resultados original desencadenan el envío de un mensaje a la cola de SQL Server configurada en la solicitud de notificación.</span><span class="sxs-lookup"><span data-stu-id="c7e87-110">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>  
  
 <span data-ttu-id="c7e87-111">El modo en que se sondea la cola de SQL Server y se interpreta el mensaje es específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c7e87-111">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="c7e87-112">La aplicación es responsable de sondear la cola y de reaccionar según el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c7e87-112">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7e87-113">Si utiliza solicitudes de notificación de SQL Server con <xref:System.Data.SqlClient.SqlDependency>, cree su propio nombre de cola en lugar de usar el nombre del servicio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c7e87-113">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>  
  
 <span data-ttu-id="c7e87-114">No existe ningún elemento de seguridad de cliente nuevo para <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="c7e87-114">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="c7e87-115">Se trata principalmente de una característica de servidor, que ha creado privilegios especiales que deben poseer los usuarios para solicitar una notificación.</span><span class="sxs-lookup"><span data-stu-id="c7e87-115">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c7e87-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7e87-116">Example</span></span>  
 <span data-ttu-id="c7e87-117">El siguiente fragmento de código demuestra cómo crear un objeto <xref:System.Data.Sql.SqlNotificationRequest> y asociarlo a <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="c7e87-117">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>  
  
```vb  
' Assume connection is an open SqlConnection.  
' Create a new SqlCommand object.  
Dim command As New SqlCommand( _  
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)  
  
' Create a SqlNotificationRequest object.  
Dim notficationRequest As New SqlNotificationRequest()  
notficationRequest.id = "NotificationID"  
notficationRequest.Service = "mySSBQueue"  
  
' Associate the notification request with the command.  
command.Notification = notficationRequest  
' Execute the command.  
command.ExecuteReader()  
' Process the DataReader.  
' You can use Transact-SQL syntax to periodically poll the   
' SQL Server queue to see if you have a new message.  
```  
  
```csharp  
// Assume connection is an open SqlConnection.  
// Create a new SqlCommand object.  
SqlCommand command=new SqlCommand(  
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);  
  
// Create a SqlNotificationRequest object.  
SqlNotificationRequest notficationRequest=new SqlNotificationRequest();  
notficationRequest.id="NotificationID";  
notficationRequest.Service="mySSBQueue";  
  
// Associate the notification request with the command.  
command.Notification=notficationRequest;  
// Execute the command.  
command.ExecuteReader();  
// Process the DataReader.  
// You can use Transact-SQL syntax to periodically poll the   
// SQL Server queue to see if you have a new message.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7e87-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7e87-118">See Also</span></span>  
 [<span data-ttu-id="c7e87-119">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="c7e87-119">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="c7e87-120">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="c7e87-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
