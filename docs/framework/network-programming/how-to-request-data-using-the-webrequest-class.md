---
title: "C&#243;mo solicitar datos mediante la clase WebRequest | Microsoft Docs"
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
  - "descargar recursos de Internet, pasos"
  - "solicitar datos de Internet, pasos"
  - "clase WebRequest, recibir datos"
  - "recibir datos, mediante la clase WebRequest"
  - "Internet, solicitar datos"
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# C&#243;mo solicitar datos mediante la clase WebRequest
El procedimiento siguiente describe los pasos utilizados para solicitar un recurso de un servidor, por ejemplo, una página Web o un archivo.  El recurso debe ser identificado por un identificador URI.  
  
### Para solicitar datos de un servidor de host  
  
1.  Cree una instancia de <xref:System.Net.WebRequest> llamando a <xref:System.Net.WebRequest.Create%2A> con el URI del recurso.  
  
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
  
     En la mayoría de los casos, la clase de **WebRequest** es suficiente para recibir datos.  Sin embargo, si necesita establecer propiedades protocolo\- específicas, debe convertir **WebRequest** el tipo protocolo\- concreto.  Por ejemplo, para tener acceso a las propiedades Http\- específicas de <xref:System.Net.HttpWebRequest>, convierta **WebRequest** a una referencia de **HttpWebRequest** .  El ejemplo de código siguiente muestra cómo establecer la propiedad Http\-específica de <xref:System.Net.HttpWebRequest.UserAgent%2A> .  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
  
    ```  
  
3.  Para enviar la solicitud al servidor, llame a <xref:System.Net.HttpWebRequest.GetResponse%2A>.  El esquema de URI solicitado determina el tipo real del objeto devuelto de **WebResponse** .  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  Cuando haya con un objeto de <xref:System.Net.WebResponse> , debe cerrarlo llamando al método de <xref:System.Net.WebResponse.Close%2A> .  Como alternativa, si se ha obtenido la secuencia de respuesta del objeto de la respuesta, puede cerrar la secuencia llamando al método de <xref:System.IO.Stream.Close%2A?displayProperty=fullName> .  Si no cierra la respuesta o la secuencia, la aplicación puede ejecutarse de conexiones al servidor y volverse no se puede procesar solicitudes adicionales.  
  
4.  Puede tener acceso a las propiedades de **WebResponse** o convertir **WebResponse** a una instancia protocolo\- específica para leer propiedades protocolo\- concretas.  Por ejemplo, para tener acceso a las propiedades Http\- específicas de <xref:System.Net.HttpWebResponse>, convierta **WebResponse** a una referencia de **HttpWebResponse** .  El ejemplo de código siguiente muestra cómo mostrar la información de estado enviada con una respuesta.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, utilice el método de <xref:System.Net.HttpWebResponse.GetResponseStream%2A> de **WebResponse**.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream ();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
  
    ```  
  
6.  Después de leer los datos de respuesta, debe cerrar la secuencia de respuesta utilizando el método de **Stream.Close** o cerrar la respuesta utilizando el método de **WebResponse.Close** .  No es necesario llamar al método de **Cerrar** en la secuencia de respuesta y **WebResponse**, pero hacerlo no es malintencionado.  Llamadas **Stream.Close** de**WebResponse.Close** al cerrar la respuesta.  
  
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
    public class WebRequestGetExample  
    {  
        public static void Main ()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create (  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close ();  
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
  
## Vea también  
 [Crear solicitudes de Internet](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [Usar flujos en la red](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)   
 [Cómo enviar datos mediante la clase WebRequest](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)