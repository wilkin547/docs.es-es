---
title: "C&#243;mo enviar datos mediante la clase WebRequest | Microsoft Docs"
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
  - "clase WebRequest, enviar datos a un host"
  - "Enviar datos a un host, mediante la clase WebRequest"
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# C&#243;mo enviar datos mediante la clase WebRequest
El procedimiento siguiente describe los pasos utilizados para enviar datos a un servidor.  Este procedimiento se utiliza habitualmente enviar datos a una página Web.  
  
### Para enviar datos a un servidor de host  
  
1.  Cree una instancia de <xref:System.Net.WebRequest> llamando a <xref:System.Net.WebRequest.Create%2A> con el URI del recurso que acepta datos, por ejemplo, un script o página ASP.NET.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
  
    ```  
  
    > [!NOTE]
    >  .NET Framework proporciona clases protocolo\- específicas derivadas de **WebRequest** y de **WebResponse** para los URI que comienzan con “http: ”, “https:'' “, FTP: ”, y “archivo: ”.  Para tener acceso a los recursos mediante otros protocolos, debe implementar las clases protocolo\- concretas que derivan de **WebRequest** y de **WebResponse**.  Para obtener más información, vea [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
2.  Establezca los valores de propiedad que necesite en **WebRequest**.  Por ejemplo, para habilitar la autenticación, establezca la propiedad de **Credentials** a una instancia de la clase de <xref:System.Net.NetworkCredential> .  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
  
    ```  
  
     En la mayoría de los casos, la propia instancia de **WebRequest** es suficiente para enviar datos.  Sin embargo, si necesita establecer propiedades protocolo\- específicas, debe convertir **WebRequest** el tipo protocolo\- concreto.  Por ejemplo, para tener acceso a las propiedades Http\- específicas de <xref:System.Net.HttpWebRequest>, convierta **WebRequest** a una referencia de **HttpWebRequest** .  El ejemplo de código siguiente muestra cómo establecer la propiedad Http\-específica de <xref:System.Net.HttpWebRequest.UserAgent%2A> .  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Especifique un método de protocolo que permite que los datos son enviados con una solicitud, como el método de **POST** HTTP.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Establezca la propiedad de **ContentLength** .  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Establezca la propiedad de **ContentType** en un valor apropiado.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Obtiene la secuencia que contiene datos de solicitud llamando al método de <xref:System.Net.WebRequest.GetRequestStream%2A> .  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Escriba los datos al objeto de <xref:System.IO.Stream> devuelto por este método.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Cierre la solicitud transmitir llamando al método de **Stream.Close** .  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Envía la solicitud al servidor llamando <xref:System.Net.WebRequest.GetResponse%2A>.  Este método devuelve un objeto que contiene la respuesta del servidor.  El esquema del URI de solicitud determina el tipo de objeto devuelto de <xref:System.Net.WebResponse> .  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  Cuando haya con un objeto de <xref:System.Net.WebResponse> , debe cerrarlo llamando al método de <xref:System.Net.WebResponse.Close%2A> .  Como alternativa, si se ha obtenido la secuencia de respuesta del objeto de la respuesta, puede cerrar la secuencia llamando al método de <xref:System.IO.Stream.Close%2A?displayProperty=fullName> .  Si no cierra la respuesta o la secuencia, la aplicación puede ejecutarse de conexiones al servidor y volverse no se puede procesar solicitudes adicionales.  
  
10. Puede tener acceso a las propiedades de **WebResponse** o convertir **WebResponse** a una instancia protocolo\- específica para leer propiedades protocolo\- concretas.  Por ejemplo, para tener acceso a las propiedades Http\- específicas de <xref:System.Net.HttpWebResponse>, convierta **WebResponse** a una referencia de **HttpWebResponse** .  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método de <xref:System.Net.WebResponse.GetResponseStream%2A> de **WebResponse**.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. Después de leer los datos de respuesta, debe cerrar la secuencia de respuesta utilizando el método de **Stream.Close** o cerrar la respuesta utilizando el método de **WebResponse.Close** .  No es necesario llamar al método de **Cerrar** en la secuencia de respuesta y **WebResponse**, pero hacerlo no es malintencionado.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
  
    ```  
  
## Ejemplo  
  
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
  
## Vea también  
 [Crear solicitudes de Internet](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [Usar flujos en la red](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)   
 [Cómo solicitar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)