---
title: Usar un socket de cliente asincrónico
description: En este ejemplo se muestra un socket de cliente asincrónico. La programación asincrónica de .NET Framework permite que una aplicación se siga ejecutando mientras se procesa una conexión.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- asynchronous client sockets
- Socket class, asynchronous client sockets
- requesting data from Internet, sockets
- sockets, asynchronous client sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
ms.openlocfilehash: af5379533e51e7488d673359dc24268c6329c082
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265224"
---
# <a name="using-an-asynchronous-client-socket"></a>Usar un socket de cliente asincrónico

Un socket de cliente asincrónico no suspende la aplicación mientras espera a que finalicen las operaciones de red. En lugar de eso, usa el modelo de programación asincrónico estándar de .NET Framework para procesar la conexión de red en un subproceso mientras la aplicación continúa ejecutándose en el subproceso original. Los sockets asincrónicos son adecuados para aplicaciones que hacen un uso intensivo de la red o que no pueden esperar a que finalicen las operaciones de red antes de continuar.  
  
 La clase <xref:System.Net.Sockets.Socket> sigue el patrón de nombres de .NET Framework para los métodos asincrónicos; por ejemplo, el método sincrónico <xref:System.Net.Sockets.Socket.Receive%2A> se corresponde con los métodos asincrónicos <xref:System.Net.Sockets.Socket.BeginReceive%2A> y <xref:System.Net.Sockets.Socket.EndReceive%2A>.  
  
 Las operaciones asincrónicas necesitan un método de devolución de llamada para devolver el resultado de la operación. Si la aplicación no necesita conocer el resultado, no se necesita ningún método de devolución de llamada. El código de ejemplo de esta sección muestra cómo usar un método para iniciar la conexión a un dispositivo de red y un método de devolución de llamada para completar la conexión, un método para empezar a enviar datos y un método de devolución de llamada para completar el envío y un método para iniciar la recepción de datos y un método de devolución de llamada para finalizar la recepción de datos.  
  
 Los sockets asincrónicos usan varios subprocesos del grupo de subprocesos del sistema para procesar las conexiones de red. Un subproceso es responsable de iniciar el envío o la recepción de datos; otros subprocesos completan la conexión al dispositivo de red y envían o reciben los datos. En los ejemplos siguientes se usan instancias de la clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para suspender la ejecución del subproceso principal e indicar cuándo puede continuar la ejecución.  
  
 En el ejemplo siguiente, para conectar un socket asincrónico a un dispositivo de red, el método `Connect` inicializa un **socket** y luego llama al método <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>, pasando un punto de conexión remoto que representa al dispositivo de red, el método de devolución de llamada de conexión y un objeto de estado (el **socket** de cliente), que se usa para pasar información de estado entre llamadas asincrónicas. El ejemplo implementa el método `Connect` para conectar el **socket** especificado al punto de conexión indicado. Presupone que hay un **ManualResetEvent** global denominado `connectDone`.  
  
```vb  
Public Shared Sub Connect(remoteEP As EndPoint, client As Socket)  
    client.BeginConnect(remoteEP, _  
       AddressOf ConnectCallback, client)  
  
    connectDone.WaitOne()  
End Sub 'Connect  
```  
  
```csharp  
public static void Connect(EndPoint remoteEP, Socket client) {  
    client.BeginConnect(remoteEP,
        new AsyncCallback(ConnectCallback), client );  
  
   connectDone.WaitOne();  
}  
```  
  
 El método de devolución de llamada de conexión `ConnectCallback` implementa el delegado <xref:System.AsyncCallback>. Se conecta al dispositivo remoto cuando este está disponible y luego indica al subproceso de aplicación que la conexión está completada estableciendo **ManualResetEvent** en `connectDone`. El código siguiente implementa el método `ConnectCallback`.  
  
```vb  
Private Shared Sub ConnectCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", _  
            client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ConnectCallback  
```  
  
```csharp  
private static void ConnectCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete the connection.  
        client.EndConnect(ar);  
  
        Console.WriteLine("Socket connected to {0}",  
            client.RemoteEndPoint.ToString());  
  
        // Signal that the connection has been made.  
        connectDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 El método de ejemplo `Send` codifica los datos de cadena especificados en formato ASCII y los envía de forma asincrónica al dispositivo de red representado por el socket especificado. El ejemplo siguiente implementa el método `Send`.  
  
```vb  
Private Shared Sub Send(client As Socket, data As [String])  
    ' Convert the string data to byte data using ASCII encoding.  
    Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
    ' Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None, _  
        AddressOf SendCallback, client)  
End Sub 'Send  
```  
  
```csharp  
private static void Send(Socket client, String data) {  
    // Convert the string data to byte data using ASCII encoding.  
    byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
    // Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None,  
        new AsyncCallback(SendCallback), client);  
}  
```  
  
 El método de devolución de llamada de envío `SendCallback` implementa el delegado <xref:System.AsyncCallback>. Envía los datos cuando el dispositivo de red está listo para recibir. El siguiente ejemplo muestra la implementación del método `SendCallback`. Asume un elemento global **ManualResetEvent** denominado `sendDone`.  
  
```vb  
Private Shared Sub SendCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'SendCallback  
```  
  
```csharp  
private static void SendCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete sending the data to the remote device.  
        int bytesSent = client.EndSend(ar);  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
        // Signal that all bytes have been sent.  
        sendDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 La lectura de los datos de un socket de cliente requiere un objeto de estado que pase valores entre llamadas asincrónicas. La clase siguiente es un objeto de estado de ejemplo para recibir datos de un socket de cliente. Contiene un campo para el socket de cliente, un búfer para los datos recibidos y un <xref:System.Text.StringBuilder> para contener la cadena de datos entrante. La colocación de estos campos en el objeto de estado permite conservar sus valores en varias llamadas para leer datos desde el socket de cliente.  
  
```vb  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing
    ' Size of receive buffer.  
    Public BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(256) As Byte
    ' Received data string.  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 El método de ejemplo `Receive` configura el objeto de estado y luego llama al método **BeginReceive** para leer los datos desde el socket de cliente de forma asincrónica. El ejemplo siguiente implementa el método `Receive`.  
  
```vb  
Private Shared Sub Receive(client As Socket)  
    Try  
        ' Create the state object.  
        Dim state As New StateObject()  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReceiveCallback, state)  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'Receive  
```  
  
```csharp  
private static void Receive(Socket client) {  
    try {  
        // Create the state object.  
        StateObject state = new StateObject();  
        state.workSocket = client;  
  
        // Begin receiving the data from the remote device.  
        client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReceiveCallback), state);  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 El método de devolución de llamada de recepción `ReceiveCallback` implementa el delegado **AsyncCallback**. Recibe los datos del dispositivo de red y genera una cadena de mensaje. Lee uno o más bytes de datos de la red al búfer de datos y luego llama al método **BeginReceive** de nuevo hasta que los datos enviados por el cliente están completos. Una vez que se han leído todos los datos del cliente, `ReceiveCallback` indica al subproceso de aplicación que los datos están completos estableciendo **ManualResetEvent** en `sendDone`.  
  
 El código de ejemplo siguiente implementa el método `ReceiveCallback`. Asume una cadena global denominada `response` que contiene la cadena recibida y un elemento global **ManualResetEvent** denominado `receiveDone`. El servidor debe cerrar el socket de cliente correctamente para finalizar la sesión de red.  
  
```vb  
Private Shared Sub ReceiveCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the state object and the client socket
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, _  
                bytesRead))  
  
            '  Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
                AddressOf ReceiveCallback, state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ReceiveCallback  
```  
  
```csharp  
private static void ReceiveCallback( IAsyncResult ar ) {  
    try {  
        // Retrieve the state object and the client socket
        // from the asynchronous state object.  
        StateObject state = (StateObject) ar.AsyncState;  
        Socket client = state.workSocket;  
        // Read data from the remote device.  
        int bytesRead = client.EndReceive(ar);  
        if (bytesRead > 0) {  
            // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
                //  Get the rest of the data.  
            client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                new AsyncCallback(ReceiveCallback), state);  
        } else {  
            // All the data has arrived; put it in response.  
            if (state.sb.Length > 1) {  
                response = state.sb.ToString();  
            }  
            // Signal that all bytes have been received.  
            receiveDone.Set();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Uso de un socket de cliente sincrónico](using-a-synchronous-client-socket.md)
- [Escuchas con sockets](listening-with-sockets.md)
- [Ejemplo de sockets de cliente asincrónicos](asynchronous-client-socket-example.md)
