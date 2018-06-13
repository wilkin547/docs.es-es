---
title: Cómo solicitar datos mediante la clase WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e02ad4772d3ba84a2735a2e146a9979862d75989
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397720"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a>Cómo solicitar datos mediante la clase WebRequest
En el procedimiento siguiente se describen los pasos usados para solicitar un recurso de un servidor, por ejemplo, una página web o un archivo. El recurso debe ser identificado por un identificador URI.  
  
### <a name="to-request-data-from-a-host-server"></a>Para solicitar datos de un servidor de host  
  
1.  Cree una instancia <xref:System.Net.WebRequest> llamando a <xref:System.Net.WebRequest.Create%2A> con el URI del recurso.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  .NET Framework proporciona clases específicas de protocolo derivadas de **WebRequest** y **WebResponse** para identificadores URI que empiezan por "http:", "https:", "ftp:" y "file:". Para obtener acceso a recursos con otros protocolos, debe implementar clases específicas de protocolo que se deriven de **WebRequest** y **WebResponse**. Para obtener más información, vea [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) (Programar protocolos acoplables).  
  
2.  Establezca los valores de propiedad que sean necesarios en **WebRequest**. Por ejemplo, para habilitar la autenticación, establezca la propiedad **Credentials** en una instancia de la clase <xref:System.Net.NetworkCredential>.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     En la mayoría de los casos, la clase **WebRequest** es suficiente para recibir datos. En cambio, si necesita establecer propiedades específicas de protocolo, convierta **WebRequest** al tipo específico de protocolo. Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebRequest> específicas de HTTP, convierta **WebRequest** en una referencia **HttpWebRequest**. En el siguiente ejemplo de código se muestra cómo se establece la propiedad <xref:System.Net.HttpWebRequest.UserAgent%2A> específica de HTTP.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Para enviar la solicitud al servidor, llame a <xref:System.Net.HttpWebRequest.GetResponse%2A>. El esquema de URI solicitado determina el tipo real del objeto devuelto de **WebResponse**.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  Cuando haya acabado de usar un objeto <xref:System.Net.WebResponse>, debe cerrarlo llamando al método <xref:System.Net.WebResponse.Close%2A>. De manera alternativa, si ha obtenido la secuencia de respuesta del objeto de respuesta, puede cerrar la secuencia llamando al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Si no cierra la respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes.  
  
4.  Puede obtener acceso a las propiedades de **WebResponse** o convertir **WebResponse** en una instancia específica de protocolo para leer propiedades específicas de protocolo. Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta **WebResponse** en una referencia **HttpWebResponse**. En el ejemplo de código siguiente se muestra cómo mostrar la información de estado enviada con una respuesta.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, use el método <xref:System.Net.HttpWebResponse.GetResponseStream%2A> de **WebResponse**.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  Después de leer los datos de la respuesta, debe cerrar la secuencia de respuesta usando el método **Stream.Close** o cerrar la respuesta usando el método **WebResponse.Close**. No es necesario llamar al método **Close** en la secuencia de respuesta ni en **WebResponse**, pero, si lo hace, no se producirán problemas. **WebResponse.Close** llama a **Stream.Close** al cerrar la respuesta.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create(  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestGetExample  
  
        Public Shared Sub Main()  
            ' Create a request for the URL.   
            Dim request As WebRequest = _  
              WebRequest.Create("http://www.contoso.com/default.html")  
            ' If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            Dim dataStream As Stream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams and the response.  
            reader.Close()  
            response.Close()  
        End Sub   
    End Class   
End Namespace  
```  
  
## <a name="see-also"></a>Vea también  
 [Creación de solicitudes de Internet](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [Uso de secuencias en la red](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)  
 [Cómo enviar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
