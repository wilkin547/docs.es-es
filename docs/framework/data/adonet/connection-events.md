---
title: Eventos de Connection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: fd935306a493bf5a20f5cd6cd61a175c02d8bbba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203766"
---
# <a name="connection-events"></a>Eventos de Connection

Todos los proveedores de datos .NET Framework tienen objetos de **conexión** con dos eventos que se pueden usar para recuperar mensajes informativos de un origen de datos o para determinar si el estado de una **conexión** ha cambiado. En la tabla siguiente se describen los eventos del objeto de **conexión** .  
  
|Evento|Descripción|  
|-----------|-----------------|  
|**InfoMessage**|Se produce cuando se devuelve un mensaje informativo desde un origen de datos. Los mensajes informativos son aquellos procedentes de orígenes de datos que no inician una excepción.|  
|**StateChange**|Se produce cuando cambia el estado de la **conexión** .|  
  
## <a name="working-with-the-infomessage-event"></a>Trabajar con el evento InfoMessage  

 Con el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> del objeto <xref:System.Data.SqlClient.SqlConnection> puede recuperar advertencias o mensajes informativos de un origen de datos de SQL Server. Si se devuelven errores desde el origen de datos con un nivel de seguridad entre 11 y 16, se inicia una excepción. Sin embargo, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> se puede utilizar para obtener mensajes del origen de datos que no estén asociados a un error. En el caso de Microsoft SQL Server, cualquier error que tenga la gravedad 10, como máximo, se considera de tipo informativo y se captura mediante el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>. Para obtener más información, consulte el artículo sobre gravedad de los [errores de motor de base de datos](/sql/relational-databases/errors-events/database-engine-error-severities) .
  
 El <xref:System.Data.SqlClient.SqlConnection.InfoMessage> evento recibe un <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> objeto que contiene, en su propiedad **Errors** , una colección de los mensajes del origen de datos. Puede consultar los objetos de **error** de esta colección para obtener el número de error y el texto del mensaje, así como el origen del error. El proveedor de datos .NET Framework para SQL Server incluye asimismo datos acerca de la base de datos, el procedimiento almacenado y el número de línea donde se originó el mensaje.  
  
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

 Normalmente, el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> solo se activa para mensajes informativos y de advertencia enviados desde el servidor. Sin embargo, cuando se produce un error real, se detiene la ejecución del método **ExecuteNonQuery** o **ExecuteReader** que inició la operación del servidor y se produce una excepción.  
  
 Si desea seguir procesando el resto de las instrucciones de un comando, independientemente de los errores producidos en el servidor, establezca la propiedad <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> de <xref:System.Data.SqlClient.SqlConnection> como `true`. De esta forma, la conexión activa el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage> para errores, en lugar de iniciar una excepción e interrumpir el procesamiento. La aplicación cliente puede controlar el evento y reaccionar ante las situaciones de error.  
  
> [!NOTE]
> Los errores con un nivel de gravedad de 17, como mínimo, que hacen que el servidor interrumpa el procesamiento de comandos, deben controlarse como excepciones. En este caso, se inicia una excepción, independientemente del modo en que se controle el error en el evento <xref:System.Data.SqlClient.SqlConnection.InfoMessage>.  
  
## <a name="working-with-the-statechange-event"></a>Trabajar con el evento StateChange  

 El evento **StateChange** se produce cuando cambia el estado de una **conexión** . El evento **StateChange** recibe <xref:System.Data.StateChangeEventArgs> que le permite determinar el cambio de estado de la **conexión** mediante el uso de las propiedades **OriginalState** y **CurrentState** . La propiedad **OriginalState** es una <xref:System.Data.ConnectionState> enumeración que indica el estado de la **conexión** antes de que se cambiara. **CurrentState** es una <xref:System.Data.ConnectionState> enumeración que indica el estado de la **conexión** después de que se haya cambiado.  
  
 En el ejemplo de código siguiente se usa el evento **StateChange** para escribir un mensaje en la consola cuando cambia el estado de la **conexión** .  
  
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
  
## <a name="see-also"></a>Consulte también

- [Conectarse a un origen de datos](connecting-to-a-data-source.md)
- [Información general de ADO.NET](ado-net-overview.md)
