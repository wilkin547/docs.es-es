---
title: Procedimiento para solicitar datos mediante la clase WebRequest
description: Obtenga información sobre cómo usar la clase WebRequest en .NET Framework para solicitar un recurso (por ejemplo, una página web o un archivo) de un servidor.
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
ms.openlocfilehash: 5dcc1a7dad226288e3f74969b86e2dd457c0eed0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502475"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="50976-103">Procedimiento para solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="50976-103">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="50976-104">En el procedimiento siguiente se describen los pasos para solicitar un recurso de un servidor, como una página web o un archivo.</span><span class="sxs-lookup"><span data-stu-id="50976-104">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="50976-105">El recurso debe ser identificado por un identificador URI.</span><span class="sxs-lookup"><span data-stu-id="50976-105">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="50976-106">Para solicitar datos de un servidor de host</span><span class="sxs-lookup"><span data-stu-id="50976-106">To request data from a host server</span></span>

1. <span data-ttu-id="50976-107">Cree una instancia de <xref:System.Net.WebRequest> mediante una llamada a <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> con el URI del recurso.</span><span class="sxs-lookup"><span data-stu-id="50976-107">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="50976-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50976-108">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("https://docs.microsoft.com");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("https://docs.microsoft.com")
    ```

    > [!NOTE]
    > <span data-ttu-id="50976-109">.NET Framework proporciona clases específicas de protocolo derivadas de las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> para identificadores URI que empiezan por *http:* , *https:* , *ftp:* y *file:* .</span><span class="sxs-lookup"><span data-stu-id="50976-109">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="50976-110">Si necesita establecer o leer propiedades específicas de protocolo, debe convertir el objeto <xref:System.Net.WebRequest> o <xref:System.Net.WebResponse> a un tipo de objeto específico de protocolo.</span><span class="sxs-lookup"><span data-stu-id="50976-110">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="50976-111">Para obtener más información, vea [Programar protocolos acoplables](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="50976-111">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="50976-112">Establezca los valores de propiedad que sean necesarios en el objeto `WebRequest`.</span><span class="sxs-lookup"><span data-stu-id="50976-112">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="50976-113">Por ejemplo, para habilitar la autenticación, establezca la propiedad <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> en una instancia de la clase <xref:System.Net.NetworkCredential>:</span><span class="sxs-lookup"><span data-stu-id="50976-113">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="50976-114">Envíe la solicitud al servidor llamando a <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50976-114">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="50976-115">Este método devuelve un objeto que contiene la respuesta del servidor.</span><span class="sxs-lookup"><span data-stu-id="50976-115">This method returns an object containing the server's response.</span></span> <span data-ttu-id="50976-116">El tipo del objeto <xref:System.Net.WebResponse> devuelto se determina mediante el esquema del URI de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="50976-116">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="50976-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50976-117">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="50976-118">Puede obtener acceso a las propiedades de su objeto `WebResponse` o convertirlo en una instancia específica de protocolo para leer propiedades específicas de protocolo.</span><span class="sxs-lookup"><span data-stu-id="50976-118">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="50976-119">Por ejemplo, para obtener acceso a las propiedades de <xref:System.Net.HttpWebResponse> específicas de HTTP, convierta el objeto `WebResponse` en una referencia `HttpWebResponse`.</span><span class="sxs-lookup"><span data-stu-id="50976-119">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="50976-120">En el ejemplo de código siguiente se indica cómo mostrar la propiedad <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> específica de HTTP enviada con una respuesta:</span><span class="sxs-lookup"><span data-stu-id="50976-120">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="50976-121">Para obtener la secuencia que contiene los datos de respuesta enviados por el servidor, llame al método <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50976-121">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="50976-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50976-122">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="50976-123">Después de leer los datos del objeto de respuesta, ciérrelo con el método <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> o cierre la secuencia de respuesta con el método <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="50976-123">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="50976-124">Si no cierra el objeto de respuesta o la secuencia, la aplicación se quedará sin conexiones con el servidor y no podrá procesar más solicitudes.</span><span class="sxs-lookup"><span data-stu-id="50976-124">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="50976-125">Dado que el método `WebResponse.Close` llama a `Stream.Close` cuando cierra la respuesta, no es necesario llamar a `Close` en los objetos de respuesta y de secuencia, aunque hacerlo no causa ningún daño.</span><span class="sxs-lookup"><span data-stu-id="50976-125">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="50976-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50976-126">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="50976-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50976-127">Example</span></span>

<span data-ttu-id="50976-128">En el ejemplo de código siguiente se muestra cómo crear una solicitud a un servidor web y cómo leer los datos de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="50976-128">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="50976-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="50976-129">See also</span></span>

- [<span data-ttu-id="50976-130">Creación de solicitudes de Internet</span><span class="sxs-lookup"><span data-stu-id="50976-130">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="50976-131">Uso de secuencias en la red</span><span class="sxs-lookup"><span data-stu-id="50976-131">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="50976-132">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="50976-132">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="50976-133">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="50976-133">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="50976-134">Cómo: para enviar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="50976-134">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
