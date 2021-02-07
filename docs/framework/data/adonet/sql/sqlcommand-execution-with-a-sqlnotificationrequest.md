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
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a>Ejecución de SqlCommand Execution con SqlNotificationRequest

Se puede configurar un elemento <xref:System.Data.SqlClient.SqlCommand> para generar una notificación cuando los datos cambien después de que se hayan capturado desde el servidor, y el conjunto de resultados sería diferente si la consulta se ejecutara de nuevo. Esto resulta útil para los escenarios en los que desea usar colas de notificaciones personalizadas en el servidor o cuando no desea mantener objetos activos.

## <a name="creating-the-notification-request"></a>Crear la solicitud de notificación

Puede usar un objeto <xref:System.Data.Sql.SqlNotificationRequest> para crear la solicitud de notificación enlazándolo a un objeto `SqlCommand`. Una vez creada la solicitud, ya no necesita el objeto `SqlNotificationRequest`. Puede consultar la cola para obtener las notificaciones y responder de forma adecuada. Las notificaciones pueden producirse incluso si la aplicación se cierra y se reinicia posteriormente.

Cuando se ejecuta el comando con la notificación asociada, los cambios en el conjunto de resultados original desencadenan el envío de un mensaje a la cola de SQL Server configurada en la solicitud de notificación.

El modo en el que se sondea la cola de SQL Server y se interpreta el mensaje es específico de la aplicación. La aplicación es responsable de sondear la cola y de reaccionar según el contenido del mensaje.

> [!NOTE]
> Al usar solicitudes de notificación de SQL Server con <xref:System.Data.SqlClient.SqlDependency>, cree su propio nombre de cola en lugar de usar el nombre de servicio predeterminado.

No hay nuevos elementos de seguridad del lado cliente para <xref:System.Data.Sql.SqlNotificationRequest>. Se trata principalmente de una característica de servidor, y el servidor ha creado privilegios especiales que los usuarios deben tener para solicitar una notificación.

### <a name="example"></a>Ejemplo

En el siguiente fragmento de código se muestra cómo crear un valor <xref:System.Data.Sql.SqlNotificationRequest> y asociarlo a <xref:System.Data.SqlClient.SqlCommand>.

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

## <a name="see-also"></a>Vea también

- [Notificaciones de consulta en SQL Server](query-notifications-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
