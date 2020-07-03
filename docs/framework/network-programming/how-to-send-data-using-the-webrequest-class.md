---
title: Procedimiento para enviar datos mediante la clase WebRequest
description: Obtenga información sobre cómo enviar datos a un servidor mediante la clase WebRequest en .NET Framework. Este procedimiento se suele usar para publicar datos en una página web.
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 4b353250fec778ee8b352f13de6d7faaf15c13ee
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502449"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a><span data-ttu-id="bf279-104">Procedimiento para enviar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="bf279-104">How to: Send data by using the WebRequest class</span></span>

<span data-ttu-id="bf279-105">En el procedimiento siguiente se describen los pasos para enviar datos a un servidor.</span><span class="sxs-lookup"><span data-stu-id="bf279-105">The following procedure describes the steps to send data to a server.</span></span> <span data-ttu-id="bf279-106">Este procedimiento se suele usar para publicar datos en una página web.</span><span class="sxs-lookup"><span data-stu-id="bf279-106">This procedure is commonly used to post data to a Web page.</span></span>

## <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="bf279-107">Para enviar datos a un servidor host</span><span class="sxs-lookup"><span data-stu-id="bf279-107">To send data to a host server</span></span>

1. <span data-ttu-id="bf279-108">Cree una instancia <xref:System.Net.WebRequest> mediante una llamada a <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con el URI de un recurso (como un script o una página ASP.NET) que acepte datos.</span><span class="sxs-lookup"><span data-stu-id="bf279-108">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource, such as a script or ASP.NET page, that accepts data.</span></span> <span data-ttu-id="bf279-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-109">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")
    ```

    > [!NOTE]
    > <span data-ttu-id="bf279-110">.NET Framework proporciona clases específicas de protocolo derivadas de las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> para identificadores URI que empiezan por *http:* , *https:* , *ftp:* y *file:* .</span><span class="sxs-lookup"><span data-stu-id="bf279-110">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="bf279-111">Si necesita establecer o leer propiedades específicas de protocolo, debe convertir el objeto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> a un tipo de objeto específico de protocolo.</span><span class="sxs-lookup"><span data-stu-id="bf279-111">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="bf279-112">Para obtener más información, vea [Programar protocolos acoplables](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="bf279-112">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="bf279-113">Establezca los valores de propiedad que sean necesarios en el objeto `WebRequest`.</span><span class="sxs-lookup"><span data-stu-id="bf279-113">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="bf279-114">Por ejemplo, para habilitar la autenticación, establezca la propiedad <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> en una instancia de la clase <xref:System.Net.NetworkCredential>:</span><span class="sxs-lookup"><span data-stu-id="bf279-114">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="bf279-115">Especifique un método de protocolo que permita que se envíen datos con una solicitud, como el método `POST` de HTTP:</span><span class="sxs-lookup"><span data-stu-id="bf279-115">Specify a protocol method that permits data to be sent with a request, such as the HTTP `POST` method:</span></span>

    ```csharp
    request.Method = "POST";
    ```

    ```vb
    request.Method = "POST"
    ```

4. <span data-ttu-id="bf279-116">Establezca la propiedad <xref:System.Web.HttpRequest.ContentLength> en el número de bytes que incluya con su solicitud.</span><span class="sxs-lookup"><span data-stu-id="bf279-116">Set the <xref:System.Web.HttpRequest.ContentLength> property to the number of bytes you're including with your request.</span></span> <span data-ttu-id="bf279-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-117">For example:</span></span>

    ```csharp
    request.ContentLength = byteArray.Length;
    ```

    ```vb
    request.ContentLength = byteArray.Length
    ```

5. <span data-ttu-id="bf279-118">Establezca la propiedad <xref:System.Web.HttpRequest.ContentType> en un valor apropiado.</span><span class="sxs-lookup"><span data-stu-id="bf279-118">Set the <xref:System.Web.HttpRequest.ContentType> property to an appropriate value.</span></span> <span data-ttu-id="bf279-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-119">For example:</span></span>

    ```csharp
    request.ContentType = "application/x-www-form-urlencoded";
    ```

    ```vb
    request.ContentType = "application/x-www-form-urlencoded"
    ```

6. <span data-ttu-id="bf279-120">Obtenga la secuencia que contiene los datos de la solicitud llamando al método <xref:System.Net.WebRequest.GetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf279-120">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span> <span data-ttu-id="bf279-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-121">For example:</span></span>

    ```csharp
    Stream dataStream = request.GetRequestStream();
    ```

    ```vb
    Dim dataStream As Stream = request.GetRequestStream()
    ```

7. <span data-ttu-id="bf279-122">Escriba los datos en el objeto <xref:System.IO.Stream> que devuelve el método `GetRequestStream`.</span><span class="sxs-lookup"><span data-stu-id="bf279-122">Write the data to the <xref:System.IO.Stream> object returned by the `GetRequestStream` method.</span></span> <span data-ttu-id="bf279-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-123">For example:</span></span>

    ```csharp
    dataStream.Write(byteArray, 0, byteArray.Length);
    ```

    ```vb
    dataStream.Write(byteArray, 0, byteArray.Length)
    ```

8. <span data-ttu-id="bf279-124">Cierre la secuencia de la solicitud mediante una llamada al método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf279-124">Close the request stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bf279-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-125">For example:</span></span>

    ```csharp
    dataStream.Close();
    ```

    ```vb
    dataStream.Close()
    ```

9. <span data-ttu-id="bf279-126">Envíe la solicitud al servidor llamando a <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf279-126">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bf279-127">Este método devuelve un objeto que contiene la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="bf279-127">This method returns an object containing the server's response.</span></span> <span data-ttu-id="bf279-128">El tipo del objeto `WebResponse` devuelto se determina mediante el esquema del URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="bf279-128">The returned `WebResponse` object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="bf279-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-129">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

10. <span data-ttu-id="bf279-130">Puede obtener acceso a las propiedades de su objeto `WebResponse` o convertirlo en una instancia específica de protocolo para leer propiedades específicas de protocolo.</span><span class="sxs-lookup"><span data-stu-id="bf279-130">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="bf279-131">Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta el objeto `WebResponse` en una referencia <xref:System.Net.HttpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="bf279-131">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an <xref:System.Net.HttpWebResponse> reference.</span></span> <span data-ttu-id="bf279-132">En el ejemplo de código siguiente se indica cómo mostrar la propiedad <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> específica de HTTP enviada con una respuesta:</span><span class="sxs-lookup"><span data-stu-id="bf279-132">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)
    ```

11. <span data-ttu-id="bf279-133">Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> del objeto `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="bf279-133">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method of your `WebResponse` object.</span></span> <span data-ttu-id="bf279-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-134">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

12. <span data-ttu-id="bf279-135">Después de leer los datos del objeto de respuesta, ciérrelo con el método <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> o cierre la secuencia de respuesta con el método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf279-135">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bf279-136">Si no cierra la respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes.</span><span class="sxs-lookup"><span data-stu-id="bf279-136">If you don't close either the response or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="bf279-137">Dado que el método `WebResponse.Close` llama a `Stream.Close` cuando cierra la respuesta, no es necesario llamar a `Close` en los objetos de respuesta y de secuencia, aunque hacerlo no causa ningún daño.</span><span class="sxs-lookup"><span data-stu-id="bf279-137">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="bf279-138">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf279-138">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="bf279-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf279-139">Example</span></span>

<span data-ttu-id="bf279-140">En el ejemplo siguiente se muestra cómo enviar datos a un servidor web y cómo leer los datos de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="bf279-140">The following example shows how to send data to a web server and read the data in its response:</span></span>

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a><span data-ttu-id="bf279-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf279-141">See also</span></span>

- [<span data-ttu-id="bf279-142">Creación de solicitudes de Internet</span><span class="sxs-lookup"><span data-stu-id="bf279-142">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="bf279-143">Uso de secuencias en la red</span><span class="sxs-lookup"><span data-stu-id="bf279-143">Using streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="bf279-144">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="bf279-144">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="bf279-145">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="bf279-145">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="bf279-146">Cómo: para solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="bf279-146">How to: Request data by using the WebRequest class</span></span>](how-to-request-data-using-the-webrequest-class.md)
