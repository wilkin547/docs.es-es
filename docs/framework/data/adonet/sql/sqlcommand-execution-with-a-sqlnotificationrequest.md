---
title: Ejecución de SqlCommand Execution con SqlNotificationRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: 90ec7653f7de931bd8127263643b5467998325b5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364474"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a>Ejecución de SqlCommand Execution con SqlNotificationRequest

Los objetos <xref:System.Data.SqlClient.SqlCommand> se pueden configurar para generar una notificación si, después de capturar datos del servidor, éstos generasen un conjunto de resultados diferente en caso de que se ejecutase de nuevo la consulta. Esto resulta útil si desea usar colas de notificaciones personalizadas en el servidor o si no desea mantener objetos activos.

## <a name="creating-the-notification-request"></a>Crear la solicitud de notificación

Puede utilizar un objeto <xref:System.Data.Sql.SqlNotificationRequest> para crear la solicitud de notificación mediante su enlace a un objeto `SqlCommand`. Después de crear la solicitud, ya no necesitará el objeto `SqlNotificationRequest`. Puede consultar las notificaciones en la cola y responder de forma adecuada. Las notificaciones se pueden producir incluso si la aplicación se apaga y posteriormente se reinicia.

Cuando se ejecuta el comando con las notificaciones asociadas, los cambios en el conjunto de resultados original desencadenan el envío de un mensaje a la cola de SQL Server configurada en la solicitud de notificación.

El modo en que se sondea la cola de SQL Server y se interpreta el mensaje es específico de la aplicación. La aplicación es responsable de sondear la cola y de reaccionar según el contenido del mensaje.

> [!NOTE]
> Si utiliza solicitudes de notificación de SQL Server con <xref:System.Data.SqlClient.SqlDependency>, cree su propio nombre de cola en lugar de usar el nombre del servicio predeterminado.

No existe ningún elemento de seguridad de cliente nuevo para <xref:System.Data.Sql.SqlNotificationRequest>. Se trata principalmente de una característica de servidor, que ha creado privilegios especiales que deben poseer los usuarios para solicitar una notificación.

### <a name="example"></a>Ejemplo

El siguiente fragmento de código demuestra cómo crear un objeto <xref:System.Data.Sql.SqlNotificationRequest> y asociarlo a <xref:System.Data.SqlClient.SqlCommand>.

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

- [Notificaciones de consulta en SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
