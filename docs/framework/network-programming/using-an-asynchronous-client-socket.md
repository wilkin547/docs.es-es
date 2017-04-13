---
title: "Usar un socket de cliente asincr&#243;nico | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "protocolos de aplicaciones, sockets"
  - "enviar datos, sockets"
  - "solicitudes de datos, sockets"
  - "sockets de cliente asincrónicos"
  - "Socket (clase), sockets de cliente asincrónicos"
  - "solicitar datos de Internet, sockets"
  - "sockets, sockets de cliente asincrónicos"
  - "recibir datos, sockets"
  - "protocolos, sockets"
  - "Internet, sockets"
  - "sockets de cliente"
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Usar un socket de cliente asincr&#243;nico
Un socket de cliente asíncrono no suspende la aplicación mientras espera operaciones de red para completar.  En su lugar, utiliza el modelo de programación asincrónica de .NET Framework estándar para procesar la conexión de red en un subproceso mientras la aplicación continúa ejecutándose en el subproceso original.  Sockets asincrónicos son adecuados para las aplicaciones que utilizan intensivo de red o que no pueden esperar operaciones de red para completar antes de continuar.  
  
 La clase de <xref:System.Net.Sockets.Socket> sigue .NET Framework que llama al modelo para los métodos asincrónicos; por ejemplo, el método sincrónico de <xref:System.Net.Sockets.Socket.Receive%2A> corresponde a <xref:System.Net.Sockets.Socket.BeginReceive%2A> y métodos asincrónicos de <xref:System.Net.Sockets.Socket.EndReceive%2A> .  
  
 Las operaciones asincrónicas requieren un método de devolución de llamada devolver el resultado de la operación.  Si su aplicación no necesita conocer el resultado, no se requiere ningún método de devolución de llamada.  El código de ejemplo de esta sección muestra cómo utilizar un método para iniciar la conexión con un dispositivo de red y un método de devolución de llamada para completar la conexión, un método para iniciar el envío de datos y un método de devolución de llamada para completar el envío, y un método empiece a recibe datos y un método de devolución de llamada al final que recibe datos.  
  
 Varios subprocesos de uso asincrónico de sockets de sistema subproceso el conjunto para procesar las conexiones de red.  Un subproceso es responsable de iniciar el enviar o recibir de datos; otros subprocesos completan la conexión al dispositivo de red y envían o reciben los datos.  En los ejemplos siguientes, las instancias de la clase de <xref:System.Threading.ManualResetEvent?displayProperty=fullName> se utilizan para suspender la ejecución del subproceso principal y señalado cuando la ejecución puede continuar.  
  
 En el ejemplo siguiente, conectar un socket asincrónico en un dispositivo de red, el método de `Connect`inicializa **Socket** y después llamar al método de [BeginConnect](frlrfsystemnetsocketssocketclassconnecttopic) , pasando un extremo remoto que representa el dispositivo de red, el método de devolución de llamada conectarse, y un objeto de estado \(el cliente **Socket**\), que se utiliza para pasar información de estado entre las llamadas asincrónicas.  El ejemplo implementa el método de `Connect` para conectarse **Socket** especificado al extremo especificada.  Se supone **ManualResetEvent** global denominado `connectDone`.  
  
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
  
 El método de devolución de llamada conectarse `ConnectCallback` implementa el delegado de <xref:System.AsyncCallback> .  Conecta con el dispositivo remoto cuando el dispositivo remoto está disponible y a continuación designa el subproceso de la aplicación que la conexión se ha finalizado estableciendo **ManualResetEvent**`connectDone`.  El código siguiente implementa el método de `ConnectCallback` .  
  
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
  
 El método `Send` de ejemplo codifica los datos de la cadena especificada en formato ASCII y los envía de forma asincrónica al dispositivo de red representado por el socket especificado.  El ejemplo siguiente se implementa el método de `Send` .  
  
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
  
 El método de devolución de llamada `SendCallback` send implementa el delegado de <xref:System.AsyncCallback> .  Envía los datos cuando el dispositivo de red está listo para recibir.  El ejemplo siguiente se muestra la implementación del método de `SendCallback` .  Se supone **ManualResetEvent** global denominado `sendDone`.  
  
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
  
 Leer datos de un socket de cliente requiere un objeto de estados que pase valores entre las llamadas asincrónicas.  La clase siguiente es un objeto de estados de ejemplo para recibir datos de un socket de cliente.  Contiene un campo para que el socket de cliente, un búfer para los datos recibidos, y <xref:System.Text.StringBuilder> lleven presionada la cadena de los datos entrantes.  Agregar estos campos en el objeto de estado permite que sus valores se conservarían a través de varias llamadas para leer datos de socket de cliente.  
  
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
  
 El método de `Receive` de ejemplo prepara el objeto de estado y después llamar al método de **BeginReceive** para leer los datos de socket de cliente de forma asincrónica.  El ejemplo siguiente se implementa el método de `Receive` .  
  
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
  
 El método de devolución de llamada `ReceiveCallback` receive implementa el delegado de **AsyncCallback** .  Recibe los datos del dispositivo de red y compila una cadena de mensaje.  Lee uno o más bytes de datos de red en el búfer de datos y después llamar al método de **BeginReceive** de nuevo hasta que los datos enviados por el cliente se complete.  Una vez que todos los datos se lee del cliente, `ReceiveCallback` designa el subproceso de la aplicación que los datos son completado estableciendo **ManualResetEvent** `sendDone`.  
  
 El ejemplo de código siguiente se implementa el método de `ReceiveCallback`.  Supone una cadena global denominada `response` que contendrá la cadena recibida y **ManualResetEvent** global denominados `receiveDone`.  El servidor debe cerrar el socket de cliente correctamente para finalizar la sesión de la red.  
  
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
  
## Vea también  
 [Usar un Socket de cliente sincrónico](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [Escuchas con sockets](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [Ejemplo de sockets de cliente asincrónicos](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)