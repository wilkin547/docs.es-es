---
description: 'Más información acerca de: eventos de conexión'
title: Eventos de Connection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: fcf131e41ce90db11e84fd241744e348f4ca739e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663812"
---
# <a name="connection-events"></a>Eventos de Connection

Todos los proveedores de datos .NET Framework tienen objetos de **conexión** con dos eventos que se pueden usar para recuperar mensajes informativos de un origen de datos o para determinar si el estado de una **conexión** ha cambiado. En la tabla siguiente se enumeran los eventos del objeto **Connection**.  
  
|Evento|Descripción|  
|-----------|-----------------|  
|**InfoMessage**|Se produce cuando se devuelve un mensaje informativo desde un origen de datos. Los mensajes informativos son aquellos procedentes de orígenes de datos que no inician una excepción.|  
|**StateChange**|Se produce cuando cambia el estado del objeto **Connection**.|  
  
## <a name="working-with-the-infomessage-event"></a>Trabajar con el evento InfoMessage  

 Con el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> del objeto <xref:System.Data.SqlClient.SqlConnection> puede recuperar advertencias o mensajes informativos de un origen de datos de SQL Server. Si se devuelven errores desde el origen de datos con un nivel de seguridad entre 11 y 16, se inicia una excepción. Sin embargo, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> se puede utilizar para obtener mensajes del origen de datos que no estén asociados a un error. En el caso de Microsoft SQL Server, cualquier error que tenga la gravedad 10, como máximo, se considera de tipo informativo y se captura mediante el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>. Para obtener más información, consulte el artículo [Niveles de gravedad de error del motor de base de datos](/sql/relational-databases/errors-events/database-engine-error-severities).
  
 El evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> recibe un objeto <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> que contiene en su propiedad **Errors** una colección de los mensajes del origen de datos. Puede consultar los objetos **Error** de esa colección para conocer el número de error y el texto del mensaje, así como el origen del error. El proveedor de datos .NET Framework para SQL Server incluye asimismo datos acerca de la base de datos, el procedimiento almacenado y el número de línea donde se originó el mensaje.  
  
### <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se muestra cómo se puede agregar un controlador de eventos para el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a>Controlar errores como InfoMessages  

 Normalmente, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> solo se activa para mensajes informativos y de advertencia enviados desde el servidor. Sin embargo, cuando se produce un error real, se detiene la ejecución de los métodos **ExecuteNonQuery** o **ExecuteReader** que iniciaron la operación del servidor y se inicia una excepción.  
  
 Si desea seguir procesando el resto de las instrucciones de un comando, independientemente de los errores producidos en el servidor, establezca la propiedad <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> de <xref:System.Data.SqlClient.SqlConnection> como `true`. De esta forma, la conexión activa el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> para errores, en lugar de iniciar una excepción e interrumpir el procesamiento. La aplicación cliente puede controlar el evento y reaccionar ante las situaciones de error.  
  
> [!NOTE]
> Los errores con un nivel de gravedad de 17, como mínimo, que hacen que el servidor interrumpa el procesamiento de comandos, deben controlarse como excepciones. En este caso, se inicia una excepción, independientemente del modo en que se controle el error en el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
## <a name="working-with-the-statechange-event"></a>Trabajar con el evento StateChange  

 El evento **StateChange** se produce cuando cambia el estado de un objeto **Connection**. El evento **StateChange** recibe la clase <xref:System.Data.StateChangeEventArgs>, que permite determinar el cambio de estado de **Connection** por medio de las propiedades **OriginalState** y **CurrentState**. La propiedad **OriginalState** es una enumeración <xref:System.Data.ConnectionState> que indica el estado del objeto **Connection** antes del cambio. **CurrentState** es una enumeración <xref:System.Data.ConnectionState> que indica el estado del objeto **Connection** después del cambio.  
  
 En el ejemplo de código siguiente se utiliza el evento **StateChange** para escribir un mensaje en la consola cuando cambia el estado del objeto **Connection**.  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Conectarse a un origen de datos](connecting-to-a-data-source.md)
- [Información general de ADO.NET](ado-net-overview.md)
