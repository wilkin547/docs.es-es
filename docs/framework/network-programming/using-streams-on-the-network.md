---
title: Usar flujos en la red
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, streams
- Networking
- response to Internet request, streams
- network resources, stream capabilities
- receiving data, stream capabilities
- Network Resources
- sending data, stream capabilities
- downloading Internet resources, streams
- streams, capabilities
- Internet, streams
- streams
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
ms.openlocfilehash: 7d5a2e3eec9b49731a09f6eb41a8d8500a59b45c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180618"
---
# <a name="using-streams-on-the-network"></a><span data-ttu-id="70bfe-102">Usar flujos en la red</span><span class="sxs-lookup"><span data-stu-id="70bfe-102">Using Streams on the Network</span></span>
<span data-ttu-id="70bfe-103">Los recursos de red se representan como secuencias en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70bfe-103">Network resources are represented in the .NET Framework as streams.</span></span> <span data-ttu-id="70bfe-104">Al tratar las secuencias de forma genérica, .NET Framework ofrece lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70bfe-104">By treating streams generically, the .NET Framework offers the following capabilities:</span></span>  
  
- <span data-ttu-id="70bfe-105">Un método común para enviar y recibir datos web.</span><span class="sxs-lookup"><span data-stu-id="70bfe-105">A common way to send and receive Web data.</span></span> <span data-ttu-id="70bfe-106">Independientemente del contenido real del archivo (HTML, XML, etc.), la aplicación usará <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> y <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> para enviar y recibir datos.</span><span class="sxs-lookup"><span data-stu-id="70bfe-106">Whatever the actual contents of the file — HTML, XML, or anything else — your application will use <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> and <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> to send and receive data.</span></span>  
  
- <span data-ttu-id="70bfe-107">Compatibilidad con las secuencias en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70bfe-107">Compatibility with streams across the .NET Framework.</span></span> <span data-ttu-id="70bfe-108">Las secuencias se usan por todo .NET Framework, que posee una amplia infraestructura para gestionarlas.</span><span class="sxs-lookup"><span data-stu-id="70bfe-108">Streams are used throughout the .NET Framework, which has a rich infrastructure for handling them.</span></span> <span data-ttu-id="70bfe-109">Por ejemplo, puede modificar una aplicación que lee datos XML de una <xref:System.IO.FileStream> para que lea los datos de una <xref:System.Net.Sockets.NetworkStream> cambiando únicamente las pocas líneas de código que inicializan la secuencia.</span><span class="sxs-lookup"><span data-stu-id="70bfe-109">For example, you can modify an application that reads XML data from a <xref:System.IO.FileStream> to read data from a <xref:System.Net.Sockets.NetworkStream> instead by changing only the few lines of code that initialize the stream.</span></span> <span data-ttu-id="70bfe-110">Las principales diferencias entre la clase **NetworkStream** y otras secuencias radican en que no se pueden hacer búsquedas en **NetworkStream**, la propiedad <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> siempre devuelve **false** y los métodos <xref:System.Net.Sockets.NetworkStream.Seek%2A> y <xref:System.Net.Sockets.NetworkStream.Position%2A> generan <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="70bfe-110">The major differences between the **NetworkStream** class and other streams are that **NetworkStream** is not seekable, the <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> property always returns **false**, and the <xref:System.Net.Sockets.NetworkStream.Seek%2A> and <xref:System.Net.Sockets.NetworkStream.Position%2A> methods throw a <xref:System.NotSupportedException>.</span></span>  
  
- <span data-ttu-id="70bfe-111">Procesamiento de los datos a medida que llegan.</span><span class="sxs-lookup"><span data-stu-id="70bfe-111">Processing of data as it arrives.</span></span> <span data-ttu-id="70bfe-112">Las secuencias proporcionan acceso a los datos a medida que llegan de la red, en lugar de obligar a la aplicación a esperar mientras se descarga un conjunto completo de datos.</span><span class="sxs-lookup"><span data-stu-id="70bfe-112">Streams provide access to data as it arrives from the network, rather than forcing your application to wait for an entire data set to be downloaded.</span></span>  
  
 <span data-ttu-id="70bfe-113">El espacio de nombres <xref:System.Net.Sockets> contiene una clase **NetworkStream** que implementa la clase <xref:System.IO.Stream> específicamente para su uso con recursos de red.</span><span class="sxs-lookup"><span data-stu-id="70bfe-113">The <xref:System.Net.Sockets> namespace contains a **NetworkStream** class that implements the <xref:System.IO.Stream> class specifically for use with network resources.</span></span> <span data-ttu-id="70bfe-114">Las clases del espacio de nombres <xref:System.Net.Sockets> usan la clase **NetworkStream** para representar las secuencias.</span><span class="sxs-lookup"><span data-stu-id="70bfe-114">Classes in the <xref:System.Net.Sockets> namespace use the **NetworkStream** class to represent streams.</span></span>  
  
 <span data-ttu-id="70bfe-115">Para enviar datos a la red mediante la secuencia devuelta, llame a <xref:System.Net.WebRequest.GetRequestStream%2A> en su <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="70bfe-115">To send data to the network using the returned stream, call <xref:System.Net.WebRequest.GetRequestStream%2A> on your <xref:System.Net.WebRequest>.</span></span> <span data-ttu-id="70bfe-116">**WebRequest** enviará encabezados de solicitud al servidor; después podrá enviar datos al recurso de red mediante una llamada al método <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> o <xref:System.IO.Stream.Write%2A> de la secuencia devuelta.</span><span class="sxs-lookup"><span data-stu-id="70bfe-116">The **WebRequest** will send request headers to the server; then you can send data to the network resource by calling the <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, or <xref:System.IO.Stream.Write%2A> method on the returned stream.</span></span> <span data-ttu-id="70bfe-117">Algunos protocolos, como HTTP, pueden requerir que se establezcan propiedades específicas del protocolo antes de enviar los datos.</span><span class="sxs-lookup"><span data-stu-id="70bfe-117">Some protocols, such as HTTP, may require you to set protocol-specific properties before sending data.</span></span> <span data-ttu-id="70bfe-118">En el siguiente ejemplo de código se muestra cómo se establecen las propiedades específicas de HTTP para enviar datos.</span><span class="sxs-lookup"><span data-stu-id="70bfe-118">The following code example shows how to set HTTP-specific properties for sending data.</span></span> <span data-ttu-id="70bfe-119">Se presupone que la variable `sendData` contiene los datos que se van a enviar y que la variable `sendLength` es el número de bytes de datos que se van a enviar.</span><span class="sxs-lookup"><span data-stu-id="70bfe-119">It assumes that the variable `sendData` contains the data to send and that the variable `sendLength` is the number of bytes of data to send.</span></span>  
  
```csharp  
HttpWebRequest request =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 <span data-ttu-id="70bfe-120">Para recibir datos de la red, llame a <xref:System.Net.WebResponse.GetResponseStream%2A> en su <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="70bfe-120">To receive data from the network, call <xref:System.Net.WebResponse.GetResponseStream%2A> on your <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="70bfe-121">Después podrá leer los datos del recurso de red mediante una llamada al método <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> o <xref:System.IO.Stream.Read%2A> de la secuencia devuelta.</span><span class="sxs-lookup"><span data-stu-id="70bfe-121">You can then read data from the network resource by calling the <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, or <xref:System.IO.Stream.Read%2A> method on the returned stream.</span></span>  
  
 <span data-ttu-id="70bfe-122">Si usa secuencias de recursos de red, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70bfe-122">When using streams from network resources, keep in mind the following points:</span></span>  
  
- <span data-ttu-id="70bfe-123">La propiedad **CanSeek** siempre devuelve **false**, ya que la clase **NetworkStream** no puede cambiar la posición en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="70bfe-123">The **CanSeek** property always returns **false** since the **NetworkStream** class cannot change position in the stream.</span></span> <span data-ttu-id="70bfe-124">Los métodos **Seek** y **Position** generan **NotSupportedException**.</span><span class="sxs-lookup"><span data-stu-id="70bfe-124">The **Seek** and **Position** methods throw a **NotSupportedException**.</span></span>  
  
- <span data-ttu-id="70bfe-125">Si usa **WebRequest** y **WebResponse**, las instancias de secuencia creadas mediante la llamada a **GetResponseStream** son de solo lectura, mientras que las instancias de secuencia creadas mediante la llamada a **GetRequestStream** son de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="70bfe-125">When you use **WebRequest** and **WebResponse**, stream instances created by calling **GetResponseStream** are read-only and stream instances created by calling **GetRequestStream** are write-only.</span></span>  
  
- <span data-ttu-id="70bfe-126">Use la clase <xref:System.IO.StreamReader> para facilitar la codificación.</span><span class="sxs-lookup"><span data-stu-id="70bfe-126">Use the <xref:System.IO.StreamReader> class to make encoding easier.</span></span> <span data-ttu-id="70bfe-127">En el siguiente ejemplo de código se usa un **StreamReader** para leer una secuencia con codificación ASCII de una **WebResponse** (en el ejemplo no se muestra la creación de la solicitud).</span><span class="sxs-lookup"><span data-stu-id="70bfe-127">The following code example uses a **StreamReader** to read an ASCII-encoded stream from a **WebResponse** (the example does not show creating the request).</span></span>  
  
- <span data-ttu-id="70bfe-128">La llamada a **GetResponse** puede bloquearse si los recursos de red no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="70bfe-128">The call to **GetResponse** can block if network resources are not available.</span></span> <span data-ttu-id="70bfe-129">Debe considerar el uso de una solicitud asincrónica con los métodos <xref:System.Net.WebRequest.BeginGetResponse%2A> y <xref:System.Net.WebRequest.EndGetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="70bfe-129">You should consider using an asynchronous request with the <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods.</span></span>  
  
- <span data-ttu-id="70bfe-130">La llamada a **GetRequestStream** puede bloquearse mientras se establece la conexión con el servidor.</span><span class="sxs-lookup"><span data-stu-id="70bfe-130">The call to **GetRequestStream** can block while the connection to the server is created.</span></span> <span data-ttu-id="70bfe-131">Debe considerar el uso de una solicitud asincrónica para la secuencia con los métodos <xref:System.Net.WebRequest.BeginGetRequestStream%2A> y <xref:System.Net.WebRequest.EndGetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="70bfe-131">You should consider using an asynchronous request for the stream with the <xref:System.Net.WebRequest.BeginGetRequestStream%2A> and <xref:System.Net.WebRequest.EndGetRequestStream%2A> methods.</span></span>  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="70bfe-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="70bfe-132">See also</span></span>

- [<span data-ttu-id="70bfe-133">Cómo solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="70bfe-133">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="70bfe-134">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="70bfe-134">Requesting Data</span></span>](requesting-data.md)
