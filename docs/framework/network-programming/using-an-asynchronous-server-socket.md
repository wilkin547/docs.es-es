---
title: Usar un socket de servidor asincrónico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- sockets, asynchronous server sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- asynchronous server sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
ms.openlocfilehash: d51553b34f221283429d40a65e08f5ba58faf36a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2018
ms.locfileid: "50198868"
---
# <a name="using-an-asynchronous-server-socket"></a>Usar un socket de servidor asincrónico
Los sockets de servidor asincrónico usan el modelo de programación asincrónico de .NET Framework para procesar las solicitudes de servicio de red. La clase <xref:System.Net.Sockets.Socket> sigue el patrón estándar de nomenclatura asincrónico de .NET Framework; por ejemplo, el método sincrónico <xref:System.Net.Sockets.Socket.Accept%2A> se corresponde con los métodos asincrónicos <xref:System.Net.Sockets.Socket.BeginAccept%2A> y <xref:System.Net.Sockets.Socket.EndAccept%2A>.  
  
 Un socket de servidor asincrónico requiere un método para comenzar a aceptar solicitudes de conexión de la red, un método de devolución de llamada para controlar las solicitudes de conexión y comenzar a recibir datos de la red, así como un método de devolución de llamada para dejar de recibir los datos. Todos estos métodos se describen más adelante en la presente sección.  
  
 En el ejemplo siguiente, para comenzar a aceptar solicitudes de conexión de la red, el método `StartListening` inicializa la clase **Socket** y luego usa el método **BeginAccept** para empezar a aceptar conexiones nuevas. Cuando se recibe una nueva solicitud de conexión en el socket, se llama al método de devolución de llamada de aceptación. Este método es responsable de obtener la instancia **Socket** que controlará la conexión y de rechazar esa clase **Socket** en el subproceso que procesará la solicitud. El método de devolución de llamada de aceptación implementa el delegado <xref:System.AsyncCallback>; no se devuelve ningún valor y toma un único parámetro de tipo <xref:System.IAsyncResult>. El ejemplo siguiente es el shell de un método de devolución de llamada de aceptación.  
  
```vb  
Sub acceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'acceptCallback  
```  
  
```csharp  
void acceptCallback( IAsyncResult ar) {  
    // Add the callback code here.  
}  
```  
  
 El método **BeginAccept** toma dos parámetros, un delegado **AsyncCallback** que señala al método de devolución de llamada de aceptación y un objeto que se usa para pasar información de estado al método de devolución de llamada. En el ejemplo siguiente se pasa la clase **Socket** que escucha al método de devolución de llamada a través del parámetro *state*. En este ejemplo se crea un delegado **AsyncCallback** y se empiezan a aceptar conexiones de la red.  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.acceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(  
    new AsyncCallback(SocketListener.acceptCallback),   
    listener);  
```  
  
 Los sockets asincrónicos usan subprocesos del grupo de subprocesos del sistema para procesar las conexiones entrantes. Un subproceso es responsable de aceptar conexiones, otro subproceso se usa para controlar cada conexión entrante y otro subproceso es responsable de recibir los datos de la conexión. Podría tratarse del mismo subproceso dependiendo del subproceso que esté asignado por el grupo de subprocesos. En el ejemplo siguiente, la clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> suspende la ejecución del subproceso principal e indica cuándo puede continuar la ejecución.  
  
 En el ejemplo siguiente se muestra un método asincrónico que crea un socket de TCP/IP asincrónico en el equipo local y comienza a aceptar conexiones. Presupone que hay un **ManualResetEvent** global denominado `allDone`, que el método es miembro de una clase denominada `SocketListener` y que hay definido un método de devolución de llamada denominado `acceptCallback`.  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine("Local address and port : {0}", localEP.ToString())  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.acceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
```  
  
```csharp  
public void StartListening() {  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0],11000);  
  
    Console.WriteLine("Local address and port : {0}",localEP.ToString());  
  
    Socket listener = new Socket( localEP.Address.AddressFamily,  
        SocketType.Stream, ProtocolType.Tcp );  
  
    try {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true) {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(  
                new AsyncCallback(SocketListener.acceptCallback),   
                listener );  
  
            allDone.WaitOne();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine( "Closing the listener...");  
}  
```  
  
 El método de devolución de llamada de aceptación (`acceptCallback` en el ejemplo anterior) es responsable de indicar el subproceso de aplicación principal para continuar el procesamiento, de establecer la conexión con el cliente y de iniciar la lectura asincrónica de datos desde el cliente. El siguiente ejemplo es la primera parte de una implementación del método `acceptCallback`. Esta sección del método indica al subproceso de aplicación principal que continúe el procesamiento y establezca la conexión con el cliente. Presupone que hay un **ManualResetEvent** global denominado `allDone`.  
  
```vb  
Public Sub acceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'acceptCallback  
```  
  
```csharp  
public void acceptCallback(IAsyncResult ar) {  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.    
}  
```  
  
 La lectura de los datos de un socket de cliente requiere un objeto de estado que pase valores entre llamadas asincrónicas. En el ejemplo siguiente se implementa un objeto de estado para recibir una cadena del cliente remoto. Contiene campos para el socket de cliente, un búfer de datos para recibir los datos y un <xref:System.Text.StringBuilder> para crear la cadena de datos enviada por el cliente. La colocación de estos campos en el objeto de estado permite conservar sus valores en varias llamadas para leer datos desde el socket de cliente.  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 La sección del método `acceptCallback` que comienza a recibir los datos del socket de cliente primero inicializa una instancia de la clase `StateObject` y luego llama al método <xref:System.Net.Sockets.Socket.BeginReceive%2A> para empezar a leer los datos del socket de cliente de forma asincrónica.  
  
 En el siguiente ejemplo se muestra el método `acceptCallback` completo. Se presupone que hay un **ManualResetEvent** global denominado `allDone,`, que se ha definido la clase `StateObject` y que se ha definido el método `readCallback` en una clase denominada `SocketListener`.  
  
```vb  
Public Shared Sub acceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.readCallback, state)  
End Sub 'acceptCallback  
```  
  
```csharp  
public static void acceptCallback(IAsyncResult ar) {  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.readCallback), state);  
}  
```  
  
 El método final que debe implementarse para el servidor de socket asincrónico es el método de devolución de llamada de lectura que devuelve los datos enviados por el cliente. Al igual que el método de devolución de llamada de aceptación, el método de devolución de llamada de lectura es un delegado **AsyncCallback**. Este método lee uno o más bytes del socket de cliente en el búfer de datos y luego vuelve a llamar al método **BeginReceive** hasta que los datos enviados por el cliente están completos. Una vez que se ha leído todo el mensaje desde el cliente, la cadena se muestra en la consola y se cierra el socket de servidor que controla la conexión con el cliente.  
  
 El ejemplo siguiente implementa el método `readCallback`. Se presupone que se ha definido la clase `StateObject`.  
  
```vb  
Public Shared Sub readCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.   
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf readCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine("Read {0} bytes from socket." + _  
                ControlChars.Cr + " Data : {1}", content.Length, content)  
        End If  
    End If  
End Sub 'readCallback  
```  
  
```csharp  
public static void readCallback(IAsyncResult ar) {  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0) {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer,0,StateObject.BufferSize, 0,  
            new AsyncCallback(readCallback), state);  
    } else {  
        if (state.sb.Length > 1) {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine("Read {0} bytes from socket.\n Data : {1}",  
               content.Length, content);  
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Uso de un socket de servidor sincrónico](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)  
 [Ejemplo de sockets de servidor asincrónicos](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Escuchas con sockets](../../../docs/framework/network-programming/listening-with-sockets.md)
