---
title: Crear solicitudes de Internet
description: Obtenga información sobre la manera en que las aplicaciones crean instancias de WebRequest con el método WebRequest.Create. Este método crea una clase derivada basada en el esquema de URI que se le ha pasado.
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325637"
---
# <a name="create-internet-requests"></a><span data-ttu-id="c31c1-103">Creación de solicitudes de Internet</span><span class="sxs-lookup"><span data-stu-id="c31c1-103">Create internet requests</span></span>

<span data-ttu-id="c31c1-104">Las aplicaciones crean instancias <xref:System.Net.WebRequest> con el método <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c31c1-104">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c31c1-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> es un método estático que crea una clase derivada de <xref:System.Net.WebRequest> según el esquema de URI que se le ha pasado.</span><span class="sxs-lookup"><span data-stu-id="c31c1-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> is a static method that creates a class derived from <xref:System.Net.WebRequest> based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="c31c1-106">Solicitudes web, de archivos y FTP</span><span class="sxs-lookup"><span data-stu-id="c31c1-106">Web, file, and FTP requests</span></span>

<span data-ttu-id="c31c1-107">.NET Framework proporciona la clase <xref:System.Net.HttpWebRequest>, que se deriva de `WebRequest`, para controlar las solicitudes HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c31c1-107">.NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from `WebRequest`, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="c31c1-108">En la mayoría de los casos, la clase `WebRequest` proporciona todas las propiedades necesarias para realizar una solicitud; en cambio, si es necesario, puede convertir los objetos `WebRequest` creados por el método `WebRequest.Create` al tipo `HttpWebRequest` para tener acceso a las propiedades específicas de HTTP de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c31c1-108">In most cases, the `WebRequest` class provides all the properties you need to make a request; however, if necessary, you can cast `WebRequest` objects created by the `WebRequest.Create` method to the `HttpWebRequest` type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="c31c1-109">De igual forma, el objeto `HttpWebResponse` controla las respuestas de las solicitudes HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c31c1-109">Similarly, the `HttpWebResponse` object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="c31c1-110">Para tener acceso a las propiedades específicas de HTTP del objeto `HttpWebResponse`, debe convertir objetos `WebResponse` al tipo `HttpWebResponse`.</span><span class="sxs-lookup"><span data-stu-id="c31c1-110">To access the HTTP-specific properties of the `HttpWebResponse` object, you need to cast `WebResponse` objects to the `HttpWebResponse` type.</span></span>  
  
<span data-ttu-id="c31c1-111">.NET Framework también proporciona las clases <xref:System.Net.FileWebRequest> y <xref:System.Net.FileWebResponse> para controlar las solicitudes de recursos que usan el esquema de URI "file:".</span><span class="sxs-lookup"><span data-stu-id="c31c1-111">.NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="c31c1-112">Igualmente, las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse> se proporcionan para controlar las solicitudes de los recursos que usan el esquema "ftp:".</span><span class="sxs-lookup"><span data-stu-id="c31c1-112">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="c31c1-113">Si solicita un recurso que usa cualquiera de estos esquemas, puede usar el método `WebRequest.Create` para obtener un objeto con el que realizar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c31c1-113">If your request is for a resource that uses any of these schemes, you can use the `WebRequest.Create` method to obtain an object with which to make your request.</span></span>  
  
<span data-ttu-id="c31c1-114">Para controlar las solicitudes que usan otros protocolos de nivel de aplicación, implemente las clases específicas de protocolo derivadas de `WebRequest` y `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="c31c1-114">To handle requests that use other application-level protocols, implement protocol-specific classes derived from `WebRequest` and `WebResponse`.</span></span> <span data-ttu-id="c31c1-115">Para obtener más información, vea [Programar protocolos acoplables](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="c31c1-115">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c31c1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c31c1-116">See also</span></span>

- [<span data-ttu-id="c31c1-117">Cómo: Solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="c31c1-117">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="c31c1-118">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="c31c1-118">Requesting Data</span></span>](requesting-data.md)
