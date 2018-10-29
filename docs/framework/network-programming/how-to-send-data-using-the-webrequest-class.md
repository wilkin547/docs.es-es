---
title: Cómo enviar datos mediante la clase WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 1f10c5e0c6c266b7b31d658ec561bd8d6d85697b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192660"
---
# <a name="how-to-send-data-using-the-webrequest-class"></a>Cómo enviar datos mediante la clase WebRequest
En el procedimiento siguiente se describen los pasos que se llevan a cabo para enviar datos a un servidor. Este procedimiento se suele usar para publicar datos en una página web.  
  
### <a name="to-send-data-to-a-host-server"></a>Para enviar datos a un servidor host  
  
1.  Cree una instancia <xref:System.Net.WebRequest> llamando a <xref:System.Net.WebRequest.Create%2A> con el URI del recurso que acepte datos, como un script o una página ASP.NET.  
  
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
  
     En la mayoría de los casos, la instancia **WebRequest** es suficiente para enviar datos. En cambio, si necesita establecer propiedades específicas de protocolo, convierta **WebRequest** al tipo específico de protocolo. Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebRequest> específicas de HTTP, convierta **WebRequest** en una referencia **HttpWebRequest**. En el siguiente ejemplo de código se muestra cómo se establece la propiedad <xref:System.Net.HttpWebRequest.UserAgent%2A> específica de HTTP.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Especifique un método de protocolo que permita que se envíen datos con una solicitud, como el método **POST** de HTTP.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Establezca la propiedad **ContentLength**.  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Establezca la propiedad **ContentType** en un valor adecuado.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Obtenga la secuencia que contiene los datos de la solicitud llamando al método <xref:System.Net.WebRequest.GetRequestStream%2A>.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Escriba los datos en el objeto <xref:System.IO.Stream> que devuelve este método.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Cierre la secuencia de la solicitud llamando al método **Stream.Close**.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Envíe la solicitud al servidor llamando a <xref:System.Net.WebRequest.GetResponse%2A>. Este método devuelve un objeto que contiene la respuesta del servidor. El tipo del objeto <xref:System.Net.WebResponse> devuelto se determina mediante el esquema del URI de la solicitud.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  Cuando haya acabado de usar un objeto <xref:System.Net.WebResponse>, debe cerrarlo llamando al método <xref:System.Net.WebResponse.Close%2A>. De manera alternativa, si ha obtenido la secuencia de respuesta del objeto de respuesta, puede cerrar la secuencia llamando al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Si no cierra la respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes.  
  
10. Puede obtener acceso a las propiedades de **WebResponse** o convertir **WebResponse** en una instancia específica de protocolo para leer propiedades específicas de protocolo. Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta **WebResponse** en una referencia **HttpWebResponse**.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método <xref:System.Net.WebResponse.GetResponseStream%2A> de **WebResponse**.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. Después de leer los datos de la respuesta, debe cerrar la secuencia de respuesta usando el método **Stream.Close** o cerrar la respuesta usando el método **WebResponse.Close**. No es necesario llamar al método **Close** en la secuencia de respuesta ni en **WebResponse**, pero, si lo hace, no se producirán problemas.  
  
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
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
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
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
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
 [Cómo solicitar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
