---
title: Solicitud de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 1f367caf7656a83597b6262a5746686df15d33b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047315"
---
# <a name="requesting-data"></a><span data-ttu-id="ab7cd-102">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="ab7cd-102">Requesting Data</span></span>
<span data-ttu-id="ab7cd-103">El desarrollo de aplicaciones que se ejecutan en el entorno operativo distribuido de Internet hoy en día requiere un método eficaz y fácil de usar para recuperar datos de recursos de todo tipo.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-103">Developing applications that run in the distributed operating environment of today's Internet requires an efficient, easy-to-use method for retrieving data from resources of all types.</span></span> <span data-ttu-id="ab7cd-104">Los protocolos acoplables permiten desarrollar aplicaciones que usan una sola interfaz para recuperar datos de varios protocolos de Internet.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-104">Pluggable protocols let you develop applications that use a single interface to retrieve data from multiple Internet protocols.</span></span>  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a><span data-ttu-id="ab7cd-105">Cargar y descargar datos desde un servidor de Internet</span><span class="sxs-lookup"><span data-stu-id="ab7cd-105">Uploading and Downloading Data from an Internet Server</span></span>  
 <span data-ttu-id="ab7cd-106">Para transacciones simples de solicitud y respuesta, la clase <xref:System.Net.WebClient> proporciona el método más sencillo para cargar datos en un servidor de Internet o para descargarlos de él.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-106">For simple request and response transactions, the <xref:System.Net.WebClient> class provides the easiest method for uploading data to or downloading data from an Internet server.</span></span> <span data-ttu-id="ab7cd-107">**WebClient** proporciona métodos para cargar y descargar archivos, enviar y recibir secuencias, y enviar un búfer de datos al servidor y recibir una respuesta.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-107">**WebClient** provides methods for uploading and downloading files, sending and receiving streams, and sending a data buffer to the server and receiving a response.</span></span> <span data-ttu-id="ab7cd-108">**WebClient** usa las clases <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse> para establecer las conexiones reales con el recurso de Internet, por lo que cualquier protocolo acoplable registrado está disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-108">**WebClient** uses the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes to make the actual connections to the Internet resource, so any registered pluggable protocol is available for use.</span></span>  
  
 <span data-ttu-id="ab7cd-109">Las aplicaciones cliente que necesitan realizar transacciones más complejas solicitan datos de los servidores mediante la clase **WebRequest** y sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-109">Client applications that need to make more complex transactions request data from servers using the **WebRequest** class and its descendants.</span></span> <span data-ttu-id="ab7cd-110">**WebRequest** encapsula los detalles del proceso de conectar con el servidor, enviar la solicitud y recibir la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-110">**WebRequest** encapsulates the details of connecting to the server, sending the request, and receiving the response.</span></span> <span data-ttu-id="ab7cd-111">**WebRequest** es una clase abstracta que define un conjunto de propiedades y métodos que están disponibles para todas las aplicaciones que usan protocolos acoplables.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-111">**WebRequest** is an abstract class that defines a set of properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="ab7cd-112">Los descendientes de **WebRequest**, como <xref:System.Net.HttpWebRequest>, implementan las propiedades y los métodos definidos por **WebRequest** de una forma coherente con el protocolo subyacente.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-112">Descendants of **WebRequest**, such as <xref:System.Net.HttpWebRequest>, implement the properties and methods defined by **WebRequest** in a way that is consistent with the underlying protocol.</span></span>  
  
 <span data-ttu-id="ab7cd-113">La clase **WebRequest** crea instancias específicas de protocolo de descendientes de **WebRequest** mediante el uso del valor del URI pasado a su método <xref:System.Net.WebRequest.Create%2A> para determinar la instancia específica derivada de la clase que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-113">The **WebRequest** class creates protocol-specific instances of **WebRequest** descendants, using the value of the URI passed to its <xref:System.Net.WebRequest.Create%2A> method to determine the specific derived-class instance to create.</span></span> <span data-ttu-id="ab7cd-114">Las aplicaciones indican qué descendiente de **WebRequest** debe usarse para controlar una solicitud mediante el registro del constructor del descendiente con el método <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-114">Applications indicate which **WebRequest** descendant should be used to handle a request by registering the descendant's constructor with the <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ab7cd-115">Se realiza una solicitud al recurso de Internet mediante una llamada al método <xref:System.Net.WebRequest.GetResponse%2A> en el elemento **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-115">A request is made to the Internet resource by calling the <xref:System.Net.WebRequest.GetResponse%2A> method on the **WebRequest**.</span></span> <span data-ttu-id="ab7cd-116">El método **GetResponse** construye la solicitud específica del protocolo a partir de las propiedades de **WebRequest**, establece la conexión de socket TCP o UDP con el servidor y envía la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-116">The **GetResponse** method constructs the protocol-specific request from the properties of the **WebRequest**, makes the TCP or UDP socket connection to the server, and sends the request.</span></span> <span data-ttu-id="ab7cd-117">Para las solicitudes que envían datos al servidor, como las solicitudes HTTP **Post** o FTP **Put**, el método <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> proporciona una secuencia de red en la que enviar los datos.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-117">For requests that send data to the server, such as HTTP **Post** or FTP **Put** requests, the <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> method provides a network stream in which to send the data.</span></span>  
  
 <span data-ttu-id="ab7cd-118">El método **GetResponse** devuelve un elemento **WebResponse** específico del protocolo que coincide con el elemento **WebRequest.**</span><span class="sxs-lookup"><span data-stu-id="ab7cd-118">The **GetResponse** method returns a protocol-specific **WebResponse** that matches the **WebRequest.**</span></span>  
  
 <span data-ttu-id="ab7cd-119">**WebResponse** es también una clase abstracta que define propiedades y métodos que están disponibles para todas las aplicaciones que usan protocolos acoplables.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-119">The **WebResponse** class is also an abstract class that defines properties and methods that are available to all applications that use pluggable protocols.</span></span> <span data-ttu-id="ab7cd-120">Los descendientes de **WebResponse** implementan estas propiedades y métodos para el protocolo subyacente.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-120">**WebResponse** descendants implement these properties and methods for the underlying protocol.</span></span> <span data-ttu-id="ab7cd-121">La clase <xref:System.Net.HttpWebResponse>, por ejemplo, implementa la clase **WebResponse** para HTTP.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-121">The <xref:System.Net.HttpWebResponse> class, for example, implements the **WebResponse** class for HTTP.</span></span>  
  
 <span data-ttu-id="ab7cd-122">Los datos devueltos por el servidor se presentan a la aplicación en la secuencia devuelta por el método <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-122">The data returned by the server is presented to the application in the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ab7cd-123">Puede usar esta secuencia como cualquier otra, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab7cd-123">You can use this stream like any other, as shown in the following example.</span></span>  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab7cd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab7cd-124">See also</span></span>

- [<span data-ttu-id="ab7cd-125">Programación para redes en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ab7cd-125">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="ab7cd-126">Cómo: solicitar una página web y recuperar los resultados como una secuencia</span><span class="sxs-lookup"><span data-stu-id="ab7cd-126">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [<span data-ttu-id="ab7cd-127">Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest</span><span class="sxs-lookup"><span data-stu-id="ab7cd-127">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
