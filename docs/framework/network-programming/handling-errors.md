---
title: "Control de errores | Microsoft Docs"
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
  - "Excepciones de las clases Internet, WebRequest y WebResponse"
  - "Propiedad Status"
  - "clase WebExceptions, acerca de la clase WebExceptions"
  - "miembro de enumeración Timeout"
  - "Miembro de enumeración ConnectFailure"
  - "Miembro de enumeración TrustFailure"
  - "clase WebRequest, excepciones"
  - "solicitud de datos de Internet, control de errores"
  - "miembro de enumeración Success"
  - "recepción de datos, errores"
  - "miembro de enumeración ProtocolError"
  - "descarga de recursos de Internet, control de errores"
  - "clase WebResponse, excepciones"
  - "miembro de enumeración SendFailure"
  - "errores [.NET Framework], excepciones de las clases WebRequest y WebResponse"
  - "envío de datos, errores"
  - "respuesta a solicitud de Internet, control de errores"
  - "miembro de enumeración NameResolutionFailure"
  - "miembro de enumeración KeepAliveFailure"
  - "recursos de red, excepciones de las clases WebRequest y WebResponse"
  - "miembro de enumeración RequestCanceled"
  - "miembro de enumeración ReceiveFailure"
  - "miembro de enumeración ServerProtocolViolation"
  - "miembro de enumeración ConnectionClosed"
  - "miembro de enumeración SecureChannelFailure"
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Control de errores
Las clases de <xref:System.Net.WebRequest> y de <xref:System.Net.WebResponse> producen excepciones del sistema \(como <xref:System.ArgumentException>\) y excepciones Web\- específicas \(que son [WebExceptions](frlrfsystemnetwebexceptionclasstopic) producido por el método de <xref:System.Net.WebRequest.GetResponse%2A> \).  
  
 Cada **WebException** incluye una propiedad de <xref:System.Net.WebException.Status%2A> que contiene un valor de enumeración de <xref:System.Net.WebExceptionStatus> .  Puede examinar la propiedad de **Estado** para determinar el error que se produjo y tomar las medidas adecuadas para resolver el error.  
  
 La tabla siguiente describe los valores posibles para la propiedad de **Estado** .  
  
|Estado|Descripción|  
|------------|-----------------|  
|ConnectFailure|El servicio remoto no se puede establecer en el nivel de transporte.|  
|ConnectionClosed|La conexión se ha cerrado prematuramente.|  
|KeepAliveFailure|El servidor se cierra una conexión creada con el conjunto Conservar\- activo del encabezado.|  
|NameResolutionFailure|El servicio de nombre no pudo resolver el nombre de host.|  
|ProtocolError|La respuesta recibida del servidor se completó pero indicó un error en el nivel de protocolo.|  
|ReceiveFailure|No se ha recibido una respuesta completa del servidor remoto.|  
|RequestCanceled|La solicitud se ha cancelado.|  
|SecureChannelFailure|Un error en un vínculo de canal seguro.|  
|SendFailure|No se ha podido enviar una solicitud completa al servidor remoto.|  
|ServerProtocolViolation|La respuesta del servidor no fue una respuesta HTTP válida.|  
|Correcto|No se ha encontrado ningún error.|  
|Tiempo de espera|No se recibió una respuesta en el tiempo de espera establecido para la solicitud.|  
|TrustFailure|No se ha podido validar un certificado del servidor.|  
|MessageLengthLimitExceeded|Se recibió un mensaje que superaba el límite especificado al enviar una solicitud o recibir una respuesta del servidor.|  
|Pendiente|Está pendiente una solicitud asincrónica interna.|  
|PipelineFailure|Este valor es compatible con la infraestructura de.NET Framework y no está diseñado para usarse directamente en el código.|  
|ProxyNameResolutionFailure|El servicio de resolución de nombres no pudo resolver el nombre de host del proxy.|  
|UnknownError|Se ha producido una excepción de tipo desconocido.|  
  
 Cuando la propiedad de **Estado** es **WebExceptionStatus.ProtocolError**, **WebResponse** que contiene la respuesta del servidor está disponible.  Puede examinar esta respuesta para determinar el origen real del error de protocolo.  
  
 El ejemplo siguiente muestra cómo detectar **WebException**.  
  
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
  
 Aplicaciones que utilizan la captura [SocketExceptions](frlrfsystemnetsocketssocketexceptionclasstopic) de la clase de <xref:System.Net.Sockets.Socket> cuando se producen errores en el socket de Windows.  Las clases de [TCPClient](frlrfsystemnetsocketstcpclientclasstopic), de [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic), y de [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) se compilan sobre la clase de **Socket** y producen **SocketExceptions** también.  
  
 Cuando se produce **SocketException** , la clase de **SocketException** establece la propiedad de <xref:System.Net.Sockets.SocketException.ErrorCode%2A> en el último error de socket que se produjo en el sistema operativo.  Para obtener más información sobre los códigos de error de socket, vea la documentación del código de error de API WinSock 2,0 en MSDN.  
  
## Vea también  
 [Fundamentos del control de excepciones](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)