---
title: Usar un socket de cliente asincrónico
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
ms.openlocfilehash: 748745ca6799005dccdbfcbcc37a8c2a38f2a88e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180644"
---
# <a name="using-an-asynchronous-client-socket"></a><span data-ttu-id="6c2a2-102">Usar un socket de cliente asincrónico</span><span class="sxs-lookup"><span data-stu-id="6c2a2-102">Using an Asynchronous Client Socket</span></span>
<span data-ttu-id="6c2a2-103">Un socket de cliente asincrónico no suspende la aplicación mientras espera a que finalicen las operaciones de red.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-103">An asynchronous client socket does not suspend the application while waiting for network operations to complete.</span></span> <span data-ttu-id="6c2a2-104">En lugar de eso, usa el modelo de programación asincrónico estándar de .NET Framework para procesar la conexión de red en un subproceso mientras la aplicación continúa ejecutándose en el subproceso original.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-104">Instead, it uses the standard .NET Framework asynchronous programming model to process the network connection on one thread while the application continues to run on the original thread.</span></span> <span data-ttu-id="6c2a2-105">Los sockets asincrónicos son adecuados para aplicaciones que hacen un uso intensivo de la red o que no pueden esperar a que finalicen las operaciones de red antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-105">Asynchronous sockets are appropriate for applications that make heavy use of the network or that cannot wait for network operations to complete before continuing.</span></span>  
  
 <span data-ttu-id="6c2a2-106">La clase <xref:System.Net.Sockets.Socket> sigue el patrón de nombres de .NET Framework para los métodos asincrónicos; por ejemplo, el método sincrónico <xref:System.Net.Sockets.Socket.Receive%2A> se corresponde con los métodos asincrónicos <xref:System.Net.Sockets.Socket.BeginReceive%2A> y <xref:System.Net.Sockets.Socket.EndReceive%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-106">The <xref:System.Net.Sockets.Socket> class follows the .NET Framework naming pattern for asynchronous methods; for example, the synchronous <xref:System.Net.Sockets.Socket.Receive%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginReceive%2A> and <xref:System.Net.Sockets.Socket.EndReceive%2A> methods.</span></span>  
  
 <span data-ttu-id="6c2a2-107">Las operaciones asincrónicas necesitan un método de devolución de llamada para devolver el resultado de la operación.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-107">Asynchronous operations require a callback method to return the result of the operation.</span></span> <span data-ttu-id="6c2a2-108">Si la aplicación no necesita conocer el resultado, no se necesita ningún método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-108">If your application does not need to know the result, then no callback method is required.</span></span> <span data-ttu-id="6c2a2-109">El código de ejemplo de esta sección muestra cómo usar un método para iniciar la conexión a un dispositivo de red y un método de devolución de llamada para completar la conexión, un método para empezar a enviar datos y un método de devolución de llamada para completar el envío y un método para iniciar la recepción de datos y un método de devolución de llamada para finalizar la recepción de datos.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-109">The example code in this section demonstrates using a method to start connecting to a network device and a callback method to complete the connection, a method to start sending data and a callback method to complete the send, and a method to start receiving data and a callback method to end receiving data.</span></span>  
  
 <span data-ttu-id="6c2a2-110">Los sockets asincrónicos usan varios subprocesos del grupo de subprocesos del sistema para procesar las conexiones de red.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-110">Asynchronous sockets use multiple threads from the system thread pool to process network connections.</span></span> <span data-ttu-id="6c2a2-111">Un subproceso es responsable de iniciar el envío o la recepción de datos; otros subprocesos completan la conexión al dispositivo de red y envían o reciben los datos.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-111">One thread is responsible for initiating the sending or receiving of data; other threads complete the connection to the network device and send or receive the data.</span></span> <span data-ttu-id="6c2a2-112">En los ejemplos siguientes se usan instancias de la clase <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para suspender la ejecución del subproceso principal e indicar cuándo puede continuar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-112">In the following examples, instances of the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class are used to suspend execution of the main thread and signal when execution can continue.</span></span>  
  
 <span data-ttu-id="6c2a2-113">En el ejemplo siguiente, para conectar un socket asincrónico a un dispositivo de red, el método `Connect` inicializa un **socket** y luego llama al método <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>, pasando un punto de conexión remoto que representa al dispositivo de red, el método de devolución de llamada de conexión y un objeto de estado (el **socket** de cliente), que se usa para pasar información de estado entre llamadas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-113">In the following example, to connect an asynchronous socket to a network device, the `Connect` method initializes a **Socket** and then calls the <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType> method, passing a remote endpoint that represents the network device, the connect callback method, and a state object (the client **Socket**), which is used to pass state information between asynchronous calls.</span></span> <span data-ttu-id="6c2a2-114">El ejemplo implementa el método `Connect` para conectar el **socket** especificado al punto de conexión indicado.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-114">The example implements the `Connect` method to connect the specified **Socket** to the specified endpoint.</span></span> <span data-ttu-id="6c2a2-115">Presupone que hay un **ManualResetEvent** global denominado `connectDone`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-115">It assumes a global **ManualResetEvent** named `connectDone`.</span></span>  
  
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
  
 <span data-ttu-id="6c2a2-116">El método de devolución de llamada de conexión `ConnectCallback` implementa el delegado <xref:System.AsyncCallback>.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-116">The connect callback method `ConnectCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="6c2a2-117">Se conecta al dispositivo remoto cuando este está disponible y luego indica al subproceso de aplicación que la conexión está completada estableciendo **ManualResetEvent** en `connectDone`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-117">It connects to the remote device when the remote device is available and then signals the application thread that the connection is complete by setting the **ManualResetEvent** `connectDone`.</span></span> <span data-ttu-id="6c2a2-118">El código siguiente implementa el método `ConnectCallback`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-118">The following code implements the `ConnectCallback` method.</span></span>  
  
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
  
 <span data-ttu-id="6c2a2-119">El método de ejemplo `Send` codifica los datos de cadena especificados en formato ASCII y los envía de forma asincrónica al dispositivo de red representado por el socket especificado.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-119">The example method `Send` encodes the specified string data in ASCII format and sends it asynchronously to the network device represented by the specified socket.</span></span> <span data-ttu-id="6c2a2-120">El ejemplo siguiente implementa el método `Send`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-120">The following example implements the `Send` method.</span></span>  
  
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
  
 <span data-ttu-id="6c2a2-121">El método de devolución de llamada de envío `SendCallback` implementa el delegado <xref:System.AsyncCallback>.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-121">The send callback method `SendCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="6c2a2-122">Envía los datos cuando el dispositivo de red está listo para recibir.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-122">It sends the data when the network device is ready to receive.</span></span> <span data-ttu-id="6c2a2-123">El siguiente ejemplo muestra la implementación del método `SendCallback`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-123">The following example shows the implementation of the `SendCallback` method.</span></span> <span data-ttu-id="6c2a2-124">Asume un elemento global **ManualResetEvent** denominado `sendDone`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-124">It assumes a global **ManualResetEvent** named `sendDone`.</span></span>  
  
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
  
 <span data-ttu-id="6c2a2-125">La lectura de los datos de un socket de cliente requiere un objeto de estado que pase valores entre llamadas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-125">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="6c2a2-126">La clase siguiente es un objeto de estado de ejemplo para recibir datos de un socket de cliente.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-126">The following class is an example state object for receiving data from a client socket.</span></span> <span data-ttu-id="6c2a2-127">Contiene un campo para el socket de cliente, un búfer para los datos recibidos y un <xref:System.Text.StringBuilder> para contener la cadena de datos entrante.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-127">It contains a field for the client socket, a buffer for the received data, and a <xref:System.Text.StringBuilder> to hold the incoming data string.</span></span> <span data-ttu-id="6c2a2-128">La colocación de estos campos en el objeto de estado permite conservar sus valores en varias llamadas para leer datos desde el socket de cliente.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-128">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
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
  
 <span data-ttu-id="6c2a2-129">El método de ejemplo `Receive` configura el objeto de estado y luego llama al método **BeginReceive** para leer los datos desde el socket de cliente de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-129">The example `Receive` method sets up the state object and then calls the **BeginReceive** method to read the data from the client socket asynchronously.</span></span> <span data-ttu-id="6c2a2-130">El ejemplo siguiente implementa el método `Receive`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-130">The following example implements the `Receive` method.</span></span>  
  
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
  
 <span data-ttu-id="6c2a2-131">El método de devolución de llamada de recepción `ReceiveCallback` implementa el delegado **AsyncCallback**.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-131">The receive callback method `ReceiveCallback` implements the **AsyncCallback** delegate.</span></span> <span data-ttu-id="6c2a2-132">Recibe los datos del dispositivo de red y genera una cadena de mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-132">It receives the data from the network device and builds a message string.</span></span> <span data-ttu-id="6c2a2-133">Lee uno o más bytes de datos de la red al búfer de datos y luego llama al método **BeginReceive** de nuevo hasta que los datos enviados por el cliente están completos.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-133">It reads one or more bytes of data from the network into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="6c2a2-134">Una vez que se han leído todos los datos del cliente, `ReceiveCallback` indica al subproceso de aplicación que los datos están completos estableciendo **ManualResetEvent** en `sendDone`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-134">Once all the data is read from the client, `ReceiveCallback` signals the application thread that the data is complete by setting the **ManualResetEvent** `sendDone`.</span></span>  
  
 <span data-ttu-id="6c2a2-135">El código de ejemplo siguiente implementa el método `ReceiveCallback`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-135">The following example code implements the `ReceiveCallback` method.</span></span> <span data-ttu-id="6c2a2-136">Asume una cadena global denominada `response` que contiene la cadena recibida y un elemento global **ManualResetEvent** denominado `receiveDone`.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-136">It assumes a global string named `response` that holds the received string and a global **ManualResetEvent** named `receiveDone`.</span></span> <span data-ttu-id="6c2a2-137">El servidor debe cerrar el socket de cliente correctamente para finalizar la sesión de red.</span><span class="sxs-lookup"><span data-stu-id="6c2a2-137">The server must shut down the client socket gracefully to end the network session.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c2a2-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c2a2-138">See also</span></span>

- [<span data-ttu-id="6c2a2-139">Uso de un socket de cliente sincrónico</span><span class="sxs-lookup"><span data-stu-id="6c2a2-139">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="6c2a2-140">Escuchas con sockets</span><span class="sxs-lookup"><span data-stu-id="6c2a2-140">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="6c2a2-141">Ejemplo de sockets de cliente asincrónicos</span><span class="sxs-lookup"><span data-stu-id="6c2a2-141">Asynchronous Client Socket Example</span></span>](asynchronous-client-socket-example.md)
