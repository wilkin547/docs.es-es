---
title: "Ejecuci&#243;n de SqlCommand con una solicitud SqlNotification | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Ejecuci&#243;n de SqlCommand con una solicitud SqlNotification
Los objetos <xref:System.Data.SqlClient.SqlCommand> se pueden configurar para generar una notificación si, después de capturar datos del servidor, éstos generasen un conjunto de resultados diferente en caso de que se ejecutase de nuevo la consulta.  Esto resulta útil si desea usar colas de notificaciones personalizadas en el servidor o si no desea mantener objetos activos.  
  
## Crear la solicitud de notificación  
 Puede utilizar un objeto <xref:System.Data.Sql.SqlNotificationRequest> para crear la solicitud de notificación mediante su enlace a un objeto `SqlCommand`.  Después de crear la solicitud, ya no necesitará el objeto `SqlNotificationRequest`.  Puede consultar las notificaciones en la cola y responder de forma adecuada.  Las notificaciones se pueden producir incluso si la aplicación se apaga y posteriormente se reinicia.  
  
 Cuando se ejecuta el comando con las notificaciones asociadas, los cambios en el conjunto de resultados original desencadenan el envío de un mensaje a la cola de SQL Server configurada en la solicitud de notificación.  
  
 El modo en que se sondea la cola de SQL Server y se interpreta el mensaje es específico de la aplicación.  La aplicación es responsable de sondear la cola y de reaccionar según el contenido del mensaje.  
  
> [!NOTE]
>  Si utiliza solicitudes de notificación de SQL Server con <xref:System.Data.SqlClient.SqlDependency>, cree su propio nombre de cola en lugar de usar el nombre del servicio predeterminado.  
  
 No existe ningún elemento de seguridad de cliente nuevo para <xref:System.Data.Sql.SqlNotificationRequest>.  Se trata principalmente de una característica de servidor, que ha creado privilegios especiales que deben poseer los usuarios para solicitar una notificación.  
  
### Ejemplo  
 El siguiente fragmento de código demuestra cómo crear un objeto <xref:System.Data.Sql.SqlNotificationRequest> y asociarlo a <xref:System.Data.Sql.SqlCommand>.  
  
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
  
## Vea también  
 [Notificaciones de consulta en SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)