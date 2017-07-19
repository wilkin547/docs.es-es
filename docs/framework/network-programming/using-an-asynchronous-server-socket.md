---
title: "Usar un socket de servidor asincr&#243;nico | Microsoft Docs"
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
  - "Socket (clase), sockets de servidor asincrónicos"
  - "solicitudes de datos, sockets"
  - "Sockets, sockets de servidor asincrónicos"
  - "solicitar datos de Internet, sockets"
  - "sockets de servidor"
  - "recibir datos, sockets"
  - "sockets de servidor asincrónicos"
  - "protocolos, sockets"
  - "Internet, sockets"
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Usar un socket de servidor asincr&#243;nico
Sockets asincrónicos de servidor utilizan el modelo de programación asincrónica de .NET Framework para procesar solicitudes del servicio de red.  La clase de <xref:System.Net.Sockets.Socket> sigue el modelo de nombres asincrónico de .NET Framework estándar; por ejemplo, el método sincrónico de <xref:System.Net.Sockets.Socket.Accept%2A> corresponde a <xref:System.Net.Sockets.Socket.BeginAccept%2A> y métodos asincrónicos de <xref:System.Net.Sockets.Socket.EndAccept%2A> .  
  
 Un socket asincrónico de servidor requiere un método iniciar aceptar solicitudes de conexión de red, un método de devolución de llamada de controlar las solicitudes de conexión e iniciar recibiendo datos de red, y un método de devolución de llamada para finalizar recibir los datos.  Todos estos métodos se describen más adelante en esta sección.  
  
 En el ejemplo siguiente, iniciar aceptar solicitudes de conexión de red, el método `StartListening` inicializa **Socket** y utilice el método de **BeginAccept** para iniciar aceptar nuevas conexiones.  Se llama al método de devolución de llamada de aceptar cuando una nueva solicitud de conexión se recibe en el socket.  Es responsable de obtener la instancia de **Socket** que administrará la conexión y asignar ese **Socket** desactivado el subproceso que procesará la solicitud.  El método de devolución de llamada de aceptar implementa el delegado de <xref:System.AsyncCallback> ; devuelve un vacío y toma un único parámetro de <xref:System.IAsyncResult>escrito.  El ejemplo siguiente es el shell de un método de devolución de llamada de aceptar.  
  
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
  
 El método de **BeginAccept** toma dos parámetros, el delegado de **AsyncCallback** que señala al método de devolución de llamada de aceptar y un objeto que se utiliza para pasar información de estado al método de devolución de llamada.  En el ejemplo siguiente, **Socket** que escucha se pasa al método de devolución de llamada con el parámetro *de estado* .  Este ejemplo crea un delegado de **AsyncCallback** y comienza aceptar conexiones de red.  
  
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
  
 Los subprocesos asincrónicos de los sockets de sistema subproceso el conjunto para procesar las conexiones entrantes.  Un subproceso es responsable de aceptar conexiones, otro subproceso se utiliza para administrar cada conexión entrante, y otro subproceso es responsable de recibir datos de la conexión.  Éstos podrían ser el mismo subproceso, dependiendo de que el subproceso es asignado por el grupo de subprocesos.  En el ejemplo siguiente, la clase de <xref:System.Threading.ManualResetEvent?displayProperty=fullName> suspende la ejecución del subproceso principal y de paso cuando la ejecución puede continuar.  
  
 El ejemplo siguiente se muestra un método asincrónico que cree un socket asincrónico de TCP\/IP en el equipo local e inicie aceptar conexiones.  Se supone que hay **ManualResetEvent** global denominado `allDone`, que el método es un miembro de una clase denominada `SocketListener`, y un método de devolución de llamada denominado `acceptCallback` está definido.  
  
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
  
 El método de devolución de llamada de aceptación \(`acceptCallback` en el ejemplo anterior\) es responsable de indicar el subproceso principal de la aplicación para continuar procesando, establecer la conexión con el cliente, e iniciar la lectura asincrónica de datos del cliente.  El ejemplo siguiente es la primera parte de una implementación del método de `acceptCallback` .  Esta sección método designa el subproceso de aplicación principal para continuar procesando y establece la conexión al cliente.  Se supone **ManualResetEvent** global denominado `allDone`.  
  
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
  
 Leer datos de un socket de cliente requiere un objeto de estados que pase valores entre las llamadas asincrónicas.  El ejemplo siguiente implementa un objeto de estados para recibir una cadena de cliente remoto.  Contiene los campos del socket de cliente, un búfer de datos para recibir datos, y <xref:System.Text.StringBuilder> para crear la cadena de datos enviada por el cliente.  Agregar estos campos en el objeto de estado permite que sus valores se conservarían a través de varias llamadas para leer datos de socket de cliente.  
  
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
  
 La sección del método de `acceptCallback` inicial recibir los datos de socket de cliente primero inicializa una instancia de la clase de `StateObject` y después llamar al método de <xref:System.Net.Sockets.Socket.BeginReceive%2A> para empezar a leer los datos de socket de cliente de forma asincrónica.  
  
 El ejemplo siguiente se muestra el método completo de `acceptCallback` .  Se supone que hay **ManualResetEvent** global denominado `allDone,` que la clase de `StateObject` está definido, y que el método de `readCallback` está definido en una clase denominada `SocketListener`.  
  
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
  
 El método final que necesita implementarse para el servidor asincrónico de socket es el método de devolución de llamada de lectura que devuelve los datos enviados por el cliente.  Como el método de devolución de llamada de aceptar, el método de devolución de llamada de lectura es un delegado de **AsyncCallback** .  Este método lee uno o más bytes de socket de cliente en el búfer de datos y después llamar al método de **BeginReceive** de nuevo hasta que los datos enviados por el cliente se complete.  Una vez que el mensaje completo se ha leído de cliente, la cadena se muestra en la consola y el socket de servidor que administra la conexión al cliente se cierra.  
  
 El ejemplo siguiente se implementa el método de `readCallback` .  Se supone que la clase de `StateObject` está definida.  
  
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
  
## Vea también  
 [Usar un socket de servidor sincrónico](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [Ejemplo de sockets de servidor asincrónicos](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [Escuchas con sockets](../../../docs/framework/network-programming/listening-with-sockets.md)