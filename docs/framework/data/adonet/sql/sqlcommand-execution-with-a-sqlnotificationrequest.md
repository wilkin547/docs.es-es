---
description: 'Más información acerca de: ejecución de SqlCommand con un SqlNotificationRequest'
title: Ejecución de SqlCommand Execution con SqlNotificationRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: d3e82022794aa67d4bd20223cac852097f2be9dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767055"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="12123-103">Ejecución de SqlCommand Execution con SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="12123-103">SqlCommand Execution with a SqlNotificationRequest</span></span>

<span data-ttu-id="12123-104">Se puede configurar un elemento <xref:System.Data.SqlClient.SqlCommand> para generar una notificación cuando los datos cambien después de que se hayan capturado desde el servidor, y el conjunto de resultados sería diferente si la consulta se ejecutara de nuevo.</span><span class="sxs-lookup"><span data-stu-id="12123-104">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="12123-105">Esto resulta útil para los escenarios en los que desea usar colas de notificaciones personalizadas en el servidor o cuando no desea mantener objetos activos.</span><span class="sxs-lookup"><span data-stu-id="12123-105">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>

## <a name="creating-the-notification-request"></a><span data-ttu-id="12123-106">Crear la solicitud de notificación</span><span class="sxs-lookup"><span data-stu-id="12123-106">Creating the Notification Request</span></span>

<span data-ttu-id="12123-107">Puede usar un objeto <xref:System.Data.Sql.SqlNotificationRequest> para crear la solicitud de notificación enlazándolo a un objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="12123-107">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="12123-108">Una vez creada la solicitud, ya no necesita el objeto `SqlNotificationRequest`.</span><span class="sxs-lookup"><span data-stu-id="12123-108">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="12123-109">Puede consultar la cola para obtener las notificaciones y responder de forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="12123-109">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="12123-110">Las notificaciones pueden producirse incluso si la aplicación se cierra y se reinicia posteriormente.</span><span class="sxs-lookup"><span data-stu-id="12123-110">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>

<span data-ttu-id="12123-111">Cuando se ejecuta el comando con la notificación asociada, los cambios en el conjunto de resultados original desencadenan el envío de un mensaje a la cola de SQL Server configurada en la solicitud de notificación.</span><span class="sxs-lookup"><span data-stu-id="12123-111">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>

<span data-ttu-id="12123-112">El modo en el que se sondea la cola de SQL Server y se interpreta el mensaje es específico de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="12123-112">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="12123-113">La aplicación es responsable de sondear la cola y de reaccionar según el contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="12123-113">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>

> [!NOTE]
> <span data-ttu-id="12123-114">Al usar solicitudes de notificación de SQL Server con <xref:System.Data.SqlClient.SqlDependency>, cree su propio nombre de cola en lugar de usar el nombre de servicio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12123-114">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>

<span data-ttu-id="12123-115">No hay nuevos elementos de seguridad del lado cliente para <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="12123-115">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="12123-116">Se trata principalmente de una característica de servidor, y el servidor ha creado privilegios especiales que los usuarios deben tener para solicitar una notificación.</span><span class="sxs-lookup"><span data-stu-id="12123-116">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>

### <a name="example"></a><span data-ttu-id="12123-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="12123-117">Example</span></span>

<span data-ttu-id="12123-118">En el siguiente fragmento de código se muestra cómo crear un valor <xref:System.Data.Sql.SqlNotificationRequest> y asociarlo a <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="12123-118">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>

```vb
' Assume connection is an open SqlConnection.
' Create a new SqlCommand object.
Dim command As New SqlCommand( _
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)

' Create a SqlNotificationRequest object.
Dim notifcationRequest As New SqlNotificationRequest()
notificationRequest.id = "NotificationID"
notificationRequest.Service = "mySSBQueue"

' Associate the notification request with the command.
command.Notification = notificationRequest
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
SqlNotificationRequest notificationRequest=new SqlNotificationRequest();
notificationRequest.id="NotificationID";
notificationRequest.Service="mySSBQueue";

// Associate the notification request with the command.
command.Notification=notificationRequest;
// Execute the command.
command.ExecuteReader();
// Process the DataReader.
// You can use Transact-SQL syntax to periodically poll the
// SQL Server queue to see if you have a new message.
```

## <a name="see-also"></a><span data-ttu-id="12123-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="12123-119">See also</span></span>

- [<span data-ttu-id="12123-120">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="12123-120">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="12123-121">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12123-121">ADO.NET Overview</span></span>](../ado-net-overview.md)
