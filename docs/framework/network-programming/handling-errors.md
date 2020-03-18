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
ms.openlocfilehash: f5be5d8e14d7aa2d98009fc10c9cce314e745ed1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180864"
---
# <a name="handling-errors"></a>Control de errores

Las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> generan excepciones de sistema (como <xref:System.ArgumentException>) y excepciones específicas de web (que son <xref:System.Net.WebException> generadas mediante el método <xref:System.Net.WebRequest.GetResponse%2A>).  
  
Cada **WebException** incluye una propiedad <xref:System.Net.WebException.Status%2A> que contiene un valor de la enumeración <xref:System.Net.WebExceptionStatus>. Puede examinar la propiedad **Status** para determinar el error que se ha producido y realizar los pasos adecuados para resolverlo.  
  
En la tabla siguiente se describen los valores posibles de la propiedad **Status**.  
  
|Situación|Description|  
|------------|-----------------|  
|ConnectFailure|No se ha podido contactar con el servicio remoto en el nivel de transporte.|  
|ConnectionClosed|La conexión ha terminado antes de tiempo.|  
|KeepAliveFailure|El servidor ha terminado una conexión realizada con el conjunto de encabezado de conexión persistente.|  
|NameResolutionFailure|El servicio de nombres no pudo resolver el nombre de host.|  
|ProtocolError|La respuesta que se ha recibido del servidor estaba completa pero indicaba un error en el nivel de protocolo.|  
|ReceiveFailure|No se ha recibido una respuesta completa del servidor remoto.|  
|RequestCanceled|Se ha cancelado la solicitud.|  
|SecureChannelFailure|Se ha producido un error en un vínculo de canal seguro.|  
|SendFailure|No se pudo enviar una solicitud completa al servidor remoto.|  
|ServerProtocolViolation|La respuesta del servidor no era una respuesta HTTP válida.|  
|Correcto|No se ha detectado ningún error.|  
|Tiempo de espera|No se ha recibido ninguna respuesta en el tiempo de espera establecido para la solicitud.|  
|TrustFailure|No se pudo validar un certificado de servidor.|  
|MessageLengthLimitExceeded|Se ha recibido un mensaje que ha superado el límite especificado al enviar una solicitud o recibir una respuesta del servidor.|  
|Pendiente|Una solicitud asincrónica interna está pendiente.|  
|PipelineFailure|Este valor admite la infraestructura de .NET Framework y no está previsto su uso directo en el código.|  
|ProxyNameResolutionFailure|El servicio de resolución de nombres no pudo resolver el nombre de host del proxy.|  
|UnknownError|Se ha producido una excepción de un tipo desconocido.|  
  
Cuando la propiedad **Status** es **WebExceptionStatus.ProtocolError**, está disponible un elemento **WebResponse** que contiene la respuesta del servidor. Puede examinar esta respuesta para determinar el origen real del error del protocolo.  
  
En el ejemplo siguiente se muestra cómo capturar un elemento **WebException**.  
  
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
  
Las aplicaciones que usan la clase <xref:System.Net.Sockets.Socket> generan <xref:System.Net.Sockets.SocketException> cuando se producen errores en Windows Socket. Las clases <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> y <xref:System.Net.Sockets.UdpClient> se generan en la parte superior de la clase **Socket** y también generan **SocketExceptions**.  
  
Cuando se genera **SocketException**, la clase **SocketException** establece la propiedad <xref:System.Net.Sockets.SocketException.ErrorCode%2A> en el último error de socket que se ha producido en el sistema operativo. Para obtener más información sobre los códigos de error de socket, vea la documentación de códigos de error de la API de Winsock 2.0 en MSDN.  
  
## <a name="see-also"></a>Vea también

- [Controlar y generar excepciones en .NET](../../standard/exceptions/index.md)
- [Solicitud de datos](requesting-data.md)
