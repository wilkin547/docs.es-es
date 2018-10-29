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
ms.openlocfilehash: 8a740d2eecd4d866fd3042985f1f6f3194a12ec5
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50192764"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a><span data-ttu-id="f2446-102">Cómo solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="f2446-102">How to: Request Data Using the WebRequest Class</span></span>
<span data-ttu-id="f2446-103">En el procedimiento siguiente se describen los pasos usados para solicitar un recurso de un servidor, por ejemplo, una página web o un archivo.</span><span class="sxs-lookup"><span data-stu-id="f2446-103">The following procedure describes the steps used to request a resource from a server, for example, a Web page or file.</span></span> <span data-ttu-id="f2446-104">El recurso debe ser identificado por un identificador URI.</span><span class="sxs-lookup"><span data-stu-id="f2446-104">The resource must be identified by a URI.</span></span>  
  
### <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="f2446-105">Para solicitar datos de un servidor de host</span><span class="sxs-lookup"><span data-stu-id="f2446-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="f2446-106">Cree una instancia <xref:System.Net.WebRequest> llamando a <xref:System.Net.WebRequest.Create%2A> con el URI del recurso.</span><span class="sxs-lookup"><span data-stu-id="f2446-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f2446-107">.NET Framework proporciona clases específicas de protocolo derivadas de **WebRequest** y **WebResponse** para identificadores URI que empiezan por "http:", "https:", "ftp:" y "file:".</span><span class="sxs-lookup"><span data-stu-id="f2446-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="f2446-108">Para obtener acceso a recursos con otros protocolos, debe implementar clases específicas de protocolo que se deriven de **WebRequest** y **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="f2446-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="f2446-109">Para obtener más información, vea [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) (Programar protocolos acoplables).</span><span class="sxs-lookup"><span data-stu-id="f2446-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="f2446-110">Establezca los valores de propiedad que sean necesarios en **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="f2446-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="f2446-111">Por ejemplo, para habilitar la autenticación, establezca la propiedad **Credentials** en una instancia de la clase <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="f2446-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="f2446-112">En la mayoría de los casos, la clase **WebRequest** es suficiente para recibir datos.</span><span class="sxs-lookup"><span data-stu-id="f2446-112">In most cases, the **WebRequest** class is sufficient to receive data.</span></span> <span data-ttu-id="f2446-113">En cambio, si necesita establecer propiedades específicas de protocolo, convierta **WebRequest** al tipo específico de protocolo.</span><span class="sxs-lookup"><span data-stu-id="f2446-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="f2446-114">Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebRequest> específicas de HTTP, convierta **WebRequest** en una referencia **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="f2446-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="f2446-115">En el siguiente ejemplo de código se muestra cómo se establece la propiedad <xref:System.Net.HttpWebRequest.UserAgent%2A> específica de HTTP.</span><span class="sxs-lookup"><span data-stu-id="f2446-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="f2446-116">Para enviar la solicitud al servidor, llame a <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2446-116">To send the request to the server, call <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="f2446-117">El esquema de URI solicitado determina el tipo real del objeto devuelto de **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="f2446-117">The actual type of the returned **WebResponse** object is determined by the scheme of the requested URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f2446-118">Cuando haya acabado de usar un objeto <xref:System.Net.WebResponse>, debe cerrarlo llamando al método <xref:System.Net.WebResponse.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2446-118">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="f2446-119">De manera alternativa, si ha obtenido la secuencia de respuesta del objeto de respuesta, puede cerrar la secuencia llamando al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2446-119">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f2446-120">Si no cierra la respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes.</span><span class="sxs-lookup"><span data-stu-id="f2446-120">If you do not close either the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
4.  <span data-ttu-id="f2446-121">Puede obtener acceso a las propiedades de **WebResponse** o convertir **WebResponse** en una instancia específica de protocolo para leer propiedades específicas de protocolo.</span><span class="sxs-lookup"><span data-stu-id="f2446-121">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="f2446-122">Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta **WebResponse** en una referencia **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="f2446-122">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to a **HttpWebResponse** reference.</span></span> <span data-ttu-id="f2446-123">En el ejemplo de código siguiente se muestra cómo mostrar la información de estado enviada con una respuesta.</span><span class="sxs-lookup"><span data-stu-id="f2446-123">The following code example shows how to display the status information sent with a response.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="f2446-124">Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, use el método <xref:System.Net.HttpWebResponse.GetResponseStream%2A> de **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="f2446-124">To get the stream containing response data sent by the server, use the <xref:System.Net.HttpWebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="f2446-125">Después de leer los datos de la respuesta, debe cerrar la secuencia de respuesta usando el método **Stream.Close** o cerrar la respuesta usando el método **WebResponse.Close**.</span><span class="sxs-lookup"><span data-stu-id="f2446-125">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="f2446-126">No es necesario llamar al método **Close** en la secuencia de respuesta ni en **WebResponse**, pero, si lo hace, no se producirán problemas.</span><span class="sxs-lookup"><span data-stu-id="f2446-126">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span> <span data-ttu-id="f2446-127">**WebResponse.Close** llama a **Stream.Close** al cerrar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="f2446-127">**WebResponse.Close** calls **Stream.Close** when closing the response.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="f2446-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2446-128">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f2446-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2446-129">See Also</span></span>  
 [<span data-ttu-id="f2446-130">Creación de solicitudes de Internet</span><span class="sxs-lookup"><span data-stu-id="f2446-130">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="f2446-131">Uso de secuencias en la red</span><span class="sxs-lookup"><span data-stu-id="f2446-131">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="f2446-132">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="f2446-132">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="f2446-133">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="f2446-133">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="f2446-134">Cómo enviar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="f2446-134">How to: Send Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
