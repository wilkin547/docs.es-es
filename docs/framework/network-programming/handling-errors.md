---
title: Control de errores
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, WebRequest and WebResponse classes exceptions
- Status property
- WebExceptions class, about WebExceptions class
- Timeout enumeration member
- ConnectFailure enumeration member
- TrustFailure enumeration member
- WebRequest class, exceptions
- requesting data from Internet, error handling
- Success enumeration member
- receiving data, errors
- ProtocolError enumeration member
- downloading Internet resources, error handling
- WebResponse class, exceptions
- SendFailure enumeration member
- errors [.NET Framework], WebRequest and WebResponse classes exceptions
- sending data, errors
- response to Internet request, error handling
- NameResolutionFailure enumeration member
- KeepAliveFailure enumeration member
- network resources, WebRequest and WebResponse classes exceptions
- RequestCanceled enumeration member
- ReceiveFailure enumeration member
- ServerProtocolViolation enumeration member
- ConnectionClosed enumeration member
- SecureChannelFailure enumeration member
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
ms.openlocfilehash: 7084c4579dd5fca0075c7516754195f7cea9e27c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458040"
---
# <a name="handling-errors"></a><span data-ttu-id="49168-102">Control de errores</span><span class="sxs-lookup"><span data-stu-id="49168-102">Handling Errors</span></span>

<span data-ttu-id="49168-103">Las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> generan excepciones de sistema (como <xref:System.ArgumentException>) y excepciones específicas de web (que son <xref:System.Net.WebException> generadas mediante el método <xref:System.Net.WebRequest.GetResponse%2A>).</span><span class="sxs-lookup"><span data-stu-id="49168-103">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
<span data-ttu-id="49168-104">Cada **WebException** incluye una propiedad <xref:System.Net.WebException.Status%2A> que contiene un valor de la enumeración <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="49168-104">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="49168-105">Puede examinar la propiedad **Status** para determinar el error que se ha producido y realizar los pasos adecuados para resolverlo.</span><span class="sxs-lookup"><span data-stu-id="49168-105">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
<span data-ttu-id="49168-106">En la tabla siguiente se describen los valores posibles de la propiedad **Status**.</span><span class="sxs-lookup"><span data-stu-id="49168-106">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="49168-107">Situación</span><span class="sxs-lookup"><span data-stu-id="49168-107">Status</span></span>|<span data-ttu-id="49168-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="49168-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="49168-109">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="49168-109">ConnectFailure</span></span>|<span data-ttu-id="49168-110">No se ha podido contactar con el servicio remoto en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="49168-110">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="49168-111">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="49168-111">ConnectionClosed</span></span>|<span data-ttu-id="49168-112">La conexión ha terminado antes de tiempo.</span><span class="sxs-lookup"><span data-stu-id="49168-112">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="49168-113">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="49168-113">KeepAliveFailure</span></span>|<span data-ttu-id="49168-114">El servidor ha terminado una conexión realizada con el conjunto de encabezado de conexión persistente.</span><span class="sxs-lookup"><span data-stu-id="49168-114">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="49168-115">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="49168-115">NameResolutionFailure</span></span>|<span data-ttu-id="49168-116">El servicio de nombres no pudo resolver el nombre de host.</span><span class="sxs-lookup"><span data-stu-id="49168-116">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="49168-117">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="49168-117">ProtocolError</span></span>|<span data-ttu-id="49168-118">La respuesta que se ha recibido del servidor estaba completa pero indicaba un error en el nivel de protocolo.</span><span class="sxs-lookup"><span data-stu-id="49168-118">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="49168-119">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="49168-119">ReceiveFailure</span></span>|<span data-ttu-id="49168-120">No se ha recibido una respuesta completa del servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="49168-120">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="49168-121">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="49168-121">RequestCanceled</span></span>|<span data-ttu-id="49168-122">Se ha cancelado la solicitud.</span><span class="sxs-lookup"><span data-stu-id="49168-122">The request was canceled.</span></span>|  
|<span data-ttu-id="49168-123">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="49168-123">SecureChannelFailure</span></span>|<span data-ttu-id="49168-124">Se ha producido un error en un vínculo de canal seguro.</span><span class="sxs-lookup"><span data-stu-id="49168-124">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="49168-125">SendFailure</span><span class="sxs-lookup"><span data-stu-id="49168-125">SendFailure</span></span>|<span data-ttu-id="49168-126">No se pudo enviar una solicitud completa al servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="49168-126">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="49168-127">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="49168-127">ServerProtocolViolation</span></span>|<span data-ttu-id="49168-128">La respuesta del servidor no era una respuesta HTTP válida.</span><span class="sxs-lookup"><span data-stu-id="49168-128">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="49168-129">Correcto</span><span class="sxs-lookup"><span data-stu-id="49168-129">Success</span></span>|<span data-ttu-id="49168-130">No se ha detectado ningún error.</span><span class="sxs-lookup"><span data-stu-id="49168-130">No error was encountered.</span></span>|  
|<span data-ttu-id="49168-131">Tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="49168-131">Timeout</span></span>|<span data-ttu-id="49168-132">No se ha recibido ninguna respuesta en el tiempo de espera establecido para la solicitud.</span><span class="sxs-lookup"><span data-stu-id="49168-132">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="49168-133">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="49168-133">TrustFailure</span></span>|<span data-ttu-id="49168-134">No se pudo validar un certificado de servidor.</span><span class="sxs-lookup"><span data-stu-id="49168-134">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="49168-135">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="49168-135">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="49168-136">Se ha recibido un mensaje que ha superado el límite especificado al enviar una solicitud o recibir una respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="49168-136">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="49168-137">Pendiente</span><span class="sxs-lookup"><span data-stu-id="49168-137">Pending</span></span>|<span data-ttu-id="49168-138">Una solicitud asincrónica interna está pendiente.</span><span class="sxs-lookup"><span data-stu-id="49168-138">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="49168-139">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="49168-139">PipelineFailure</span></span>|<span data-ttu-id="49168-140">Este valor admite la infraestructura de .NET Framework y no está previsto su uso directo en el código.</span><span class="sxs-lookup"><span data-stu-id="49168-140">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="49168-141">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="49168-141">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="49168-142">El servicio de resolución de nombres no pudo resolver el nombre de host del proxy.</span><span class="sxs-lookup"><span data-stu-id="49168-142">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="49168-143">UnknownError</span><span class="sxs-lookup"><span data-stu-id="49168-143">UnknownError</span></span>|<span data-ttu-id="49168-144">Se ha producido una excepción de un tipo desconocido.</span><span class="sxs-lookup"><span data-stu-id="49168-144">An exception of unknown type has occurred.</span></span>|  
  
<span data-ttu-id="49168-145">Cuando la propiedad **Status** es **WebExceptionStatus.ProtocolError**, está disponible un elemento **WebResponse** que contiene la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="49168-145">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="49168-146">Puede examinar esta respuesta para determinar el origen real del error del protocolo.</span><span class="sxs-lookup"><span data-stu-id="49168-146">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
<span data-ttu-id="49168-147">En el ejemplo siguiente se muestra cómo capturar un elemento **WebException**.</span><span class="sxs-lookup"><span data-stu-id="49168-147">The following example shows how to catch a **WebException**.</span></span>  
  
```csharp  
try   
{  
    // Create a request instance.  
    WebRequest myRequest =   
    WebRequest.Create("http://www.contoso.com");  
    // Get the response.  
    WebResponse myResponse = myRequest.GetResponse();  
    //Get a readable stream from the server.   
    Stream sr = myResponse.GetResponseStream();  
  
    //Read from the stream and write any data to the console.  
    bytesread = sr.Read( myBuffer, 0, length);  
    while( bytesread > 0 )   
    {  
        for (int i=0; i<bytesread; i++) {  
            Console.Write( "{0}", myBuffer[i]);  
        }  
        Console.WriteLine();  
        bytesread = sr.Read( myBuffer, 0, length);  
    }  
    sr.Close();  
    myResponse.Close();  
}  
catch (WebException webExcp)   
{  
    // If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.");  
    // Write out the WebException message.  
    Console.WriteLine(webExcp.ToString());  
    // Get the WebException status code.  
    WebExceptionStatus status =  webExcp.Status;  
    // If status is WebExceptionStatus.ProtocolError,   
    //   there has been a protocol error and a WebResponse   
    //   should exist. Display the protocol error.  
    if (status == WebExceptionStatus.ProtocolError) {  
        Console.Write("The server returned protocol error ");  
        // Get HttpWebResponse so that you can check the HTTP status code.  
        HttpWebResponse httpResponse = (HttpWebResponse)webExcp.Response;  
        Console.WriteLine((int)httpResponse.StatusCode + " - "  
           + httpResponse.StatusCode);  
    }  
}  
catch (Exception e)   
{  
    // Code to catch other exceptions goes here.  
}  
```  
  
```vb  
Try  
    ' Create a request instance.  
    Dim myRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ' Get the response.  
    Dim myResponse As WebResponse = myRequest.GetResponse()  
    'Get a readable stream from the server.   
    Dim sr As Stream = myResponse.GetResponseStream()  
  
    Dim i As Integer      
    'Read from the stream and write any data to the console.  
    bytesread = sr.Read(myBuffer, 0, length)  
    While bytesread > 0  
        For i = 0 To bytesread - 1  
            Console.Write("{0}", myBuffer(i))  
        Next i  
        Console.WriteLine()  
        bytesread = sr.Read(myBuffer, 0, length)  
    End While  
    sr.Close()  
    myResponse.Close()  
Catch webExcp As WebException  
    ' If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.")  
    ' Write out the WebException message.  
    Console.WriteLine(webExcp.ToString())  
    ' Get the WebException status code.  
    Dim status As WebExceptionStatus = webExcp.Status  
    ' If status is WebExceptionStatus.ProtocolError,   
    '   there has been a protocol error and a WebResponse   
    '   should exist. Display the protocol error.  
    If status = WebExceptionStatus.ProtocolError Then  
        Console.Write("The server returned protocol error ")  
        ' Get HttpWebResponse so that you can check the HTTP status code.  
        Dim httpResponse As HttpWebResponse = _  
           CType(webExcp.Response, HttpWebResponse)  
        Console.WriteLine(CInt(httpResponse.StatusCode).ToString() & _  
           " - " & httpResponse.StatusCode.ToString())  
    End If  
Catch e As Exception  
    ' Code to catch other exceptions goes here.  
End Try  
```  
  
<span data-ttu-id="49168-148">Las aplicaciones que usan la clase <xref:System.Net.Sockets.Socket> generan <xref:System.Net.Sockets.SocketException> cuando se producen errores en Windows Socket.</span><span class="sxs-lookup"><span data-stu-id="49168-148">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="49168-149">Las clases <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> y <xref:System.Net.Sockets.UdpClient> se generan en la parte superior de la clase **Socket** y también generan **SocketExceptions**.</span><span class="sxs-lookup"><span data-stu-id="49168-149">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
<span data-ttu-id="49168-150">Cuando se genera **SocketException**, la clase **SocketException** establece la propiedad <xref:System.Net.Sockets.SocketException.ErrorCode%2A> en el último error de socket que se ha producido en el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="49168-150">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="49168-151">Para obtener más información sobre los códigos de error de socket, vea la documentación de códigos de error de la API de Winsock 2.0 en MSDN.</span><span class="sxs-lookup"><span data-stu-id="49168-151">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49168-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="49168-152">See also</span></span>

- [<span data-ttu-id="49168-153">Controlar y generar excepciones en .NET</span><span class="sxs-lookup"><span data-stu-id="49168-153">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="49168-154">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="49168-154">Requesting Data</span></span>](requesting-data.md)
