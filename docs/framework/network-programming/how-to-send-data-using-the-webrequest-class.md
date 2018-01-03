---
title: "Cómo enviar datos mediante la clase WebRequest"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b4cc524b3b3c1dbe42f3fe3926ed44c1e917e871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-send-data-using-the-webrequest-class"></a><span data-ttu-id="08311-102">Cómo enviar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="08311-102">How to: Send Data Using the WebRequest Class</span></span>
<span data-ttu-id="08311-103">En el procedimiento siguiente se describen los pasos que se llevan a cabo para enviar datos a un servidor.</span><span class="sxs-lookup"><span data-stu-id="08311-103">The following procedure describes the steps used to send data to a server.</span></span> <span data-ttu-id="08311-104">Este procedimiento se suele usar para publicar datos en una página web.</span><span class="sxs-lookup"><span data-stu-id="08311-104">This procedure is commonly used to post data to a Web page.</span></span>  
  
### <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="08311-105">Para enviar datos a un servidor host</span><span class="sxs-lookup"><span data-stu-id="08311-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="08311-106">Cree una instancia <xref:System.Net.WebRequest> llamando a <xref:System.Net.WebRequest.Create%2A> con el URI del recurso que acepte datos, como un script o una página ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="08311-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource that accepts data, for example, a script or ASP.NET page.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="08311-107">.NET Framework proporciona clases específicas de protocolo derivadas de **WebRequest** y **WebResponse** para identificadores URI que empiezan por "http:", "https:", "ftp:" y "file:".</span><span class="sxs-lookup"><span data-stu-id="08311-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="08311-108">Para obtener acceso a recursos con otros protocolos, debe implementar clases específicas de protocolo que se deriven de **WebRequest** y **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="08311-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="08311-109">Para obtener más información, vea [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) (Programar protocolos acoplables).</span><span class="sxs-lookup"><span data-stu-id="08311-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="08311-110">Establezca los valores de propiedad que sean necesarios en **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="08311-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="08311-111">Por ejemplo, para habilitar la autenticación, establezca la propiedad **Credentials** en una instancia de la clase <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="08311-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="08311-112">En la mayoría de los casos, la instancia **WebRequest** es suficiente para enviar datos.</span><span class="sxs-lookup"><span data-stu-id="08311-112">In most cases, the **WebRequest** instance itself is sufficient to send data.</span></span> <span data-ttu-id="08311-113">En cambio, si necesita establecer propiedades específicas de protocolo, convierta **WebRequest** al tipo específico de protocolo.</span><span class="sxs-lookup"><span data-stu-id="08311-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="08311-114">Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebRequest> específicas de HTTP, convierta **WebRequest** en una referencia **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="08311-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="08311-115">En el siguiente ejemplo de código se muestra cómo se establece la propiedad <xref:System.Net.HttpWebRequest.UserAgent%2A> específica de HTTP.</span><span class="sxs-lookup"><span data-stu-id="08311-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="08311-116">Especifique un método de protocolo que permita que se envíen datos con una solicitud, como el método **POST** de HTTP.</span><span class="sxs-lookup"><span data-stu-id="08311-116">Specify a protocol method that permits data to be sent with a request, such as the HTTP **POST** method.</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="08311-117">Establezca la propiedad **ContentLength**.</span><span class="sxs-lookup"><span data-stu-id="08311-117">Set the **ContentLength** property.</span></span>  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="08311-118">Establezca la propiedad **ContentType** en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="08311-118">Set the **ContentType** property to an appropriate value.</span></span>  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="08311-119">Obtenga la secuencia que contiene los datos de la solicitud llamando al método <xref:System.Net.WebRequest.GetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="08311-119">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span>  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  <span data-ttu-id="08311-120">Escriba los datos en el objeto <xref:System.IO.Stream> que devuelve este método.</span><span class="sxs-lookup"><span data-stu-id="08311-120">Write the data to the <xref:System.IO.Stream> object returned by this method.</span></span>  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="08311-121">Cierre la secuencia de la solicitud llamando al método **Stream.Close**.</span><span class="sxs-lookup"><span data-stu-id="08311-121">Close the request stream by calling the **Stream.Close** method.</span></span>  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. <span data-ttu-id="08311-122">Envíe la solicitud al servidor llamando a <xref:System.Net.WebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="08311-122">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="08311-123">Este método devuelve un objeto que contiene la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="08311-123">This method returns an object containing the server's response.</span></span> <span data-ttu-id="08311-124">El tipo del objeto <xref:System.Net.WebResponse> devuelto se determina mediante el esquema del URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="08311-124">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="08311-125">Cuando haya acabado de usar un objeto <xref:System.Net.WebResponse>, debe cerrarlo llamando al método <xref:System.Net.WebResponse.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="08311-125">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="08311-126">De manera alternativa, si ha obtenido la secuencia de respuesta del objeto de respuesta, puede cerrar la secuencia llamando al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="08311-126">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="08311-127">Si no cierra la respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes.</span><span class="sxs-lookup"><span data-stu-id="08311-127">If you do not close the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
10. <span data-ttu-id="08311-128">Puede obtener acceso a las propiedades de **WebResponse** o convertir **WebResponse** en una instancia específica de protocolo para leer propiedades específicas de protocolo.</span><span class="sxs-lookup"><span data-stu-id="08311-128">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="08311-129">Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta **WebResponse** en una referencia **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="08311-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to an **HttpWebResponse** reference.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="08311-130">Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método <xref:System.Net.WebResponse.GetResponseStream%2A> de **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="08311-130">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. <span data-ttu-id="08311-131">Después de leer los datos de la respuesta, debe cerrar la secuencia de respuesta usando el método **Stream.Close** o cerrar la respuesta usando el método **WebResponse.Close**.</span><span class="sxs-lookup"><span data-stu-id="08311-131">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="08311-132">No es necesario llamar al método **Close** en la secuencia de respuesta ni en **WebResponse**, pero, si lo hace, no se producirán problemas.</span><span class="sxs-lookup"><span data-stu-id="08311-132">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="08311-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="08311-133">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="08311-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="08311-134">See Also</span></span>  
 [<span data-ttu-id="08311-135">Creación de solicitudes de Internet</span><span class="sxs-lookup"><span data-stu-id="08311-135">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="08311-136">Uso de secuencias en la red</span><span class="sxs-lookup"><span data-stu-id="08311-136">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="08311-137">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="08311-137">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="08311-138">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="08311-138">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="08311-139">Cómo solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="08311-139">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
