---
title: Procedimiento para solicitar datos mediante la clase WebRequest
ms.date: 03/21/2019
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
ms.openlocfilehash: 1b71327d007e66cc217f6d69e11122c481e5118f
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634042"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a>Procedimiento para solicitar datos mediante la clase WebRequest
En el procedimiento siguiente se describen los pasos para solicitar un recurso de un servidor, como una página web o un archivo. El recurso debe ser identificado por un identificador URI.  
  
## <a name="to-request-data-from-a-host-server"></a>Para solicitar datos de un servidor de host  
  
1.  Cree una instancia de <xref:System.Net.WebRequest> mediante una llamada a <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con el URI del recurso. Por ejemplo: 
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/default.html");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/default.html")  
    ```  
  
    > [!NOTE]
    > .NET Framework proporciona clases específicas de protocolo derivadas de las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> para identificadores URI que empiezan por *http:*, *https:*, *ftp:* y *file:*.
    Si necesita establecer o leer propiedades específicas de protocolo, debe convertir el objeto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> a un tipo de objeto específico de protocolo. Para obtener más información, vea [Programar protocolos acoplables](programming-pluggable-protocols.md). 
  
2.  Establezca los valores de propiedad que sean necesarios en el objeto `WebRequest`. Por ejemplo, para habilitar la autenticación, establezca la propiedad <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> en una instancia de la clase <xref:System.Net.NetworkCredential>:  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
3.  Envíe la solicitud al servidor llamando a <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>. Este método devuelve un objeto que contiene la respuesta del servidor. El tipo del objeto <xref:System.Net.WebResponse> devuelto se determina mediante el esquema del URI de la solicitud. Por ejemplo:
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
4.  Puede obtener acceso a las propiedades de su objeto `WebResponse` o convertirlo en una instancia específica de protocolo para leer propiedades específicas de protocolo. 

    Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta el objeto `WebResponse` en una referencia `HttpWebResponse`. En el ejemplo de código siguiente se indica cómo mostrar la propiedad <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> específica de HTTP enviada con una respuesta:
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>. Por ejemplo:  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  Después de leer los datos del objeto de respuesta, ciérrelo con el método <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> o cierre la secuencia de respuesta con el método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Si no cierra el objeto de respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes. Dado que el método `WebResponse.Close` llama a `Stream.Close` cuando cierra la respuesta, no es necesario llamar a `Close` en los objetos de respuesta y de secuencia, aunque hacerlo no causa ningún daño. Por ejemplo:
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Ejemplo  

En el ejemplo de código siguiente se muestra cómo crear una solicitud a un servidor web y cómo leer los datos de la respuesta:  
  
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
            // Open the stream by using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  

            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  

            // Clean up the response.  
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
            ' Open the stream by using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  

            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  

            ' Clean up the response.  
            reader.Close()  
            response.Close() 

        End Sub   

    End Class  
 
End Namespace  
```  
  
## <a name="see-also"></a>Vea también
- [Creación de solicitudes de Internet](creating-internet-requests.md)
- [Uso de secuencias en la red](using-streams-on-the-network.md)
- [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)
- [Solicitud de datos](requesting-data.md)
- [Procedimiento para enviar datos mediante la clase WebRequest](how-to-send-data-using-the-webrequest-class.md)
