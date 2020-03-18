---
title: Crear solicitudes de Internet
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
ms.openlocfilehash: 80e3a6bd199691df9391e88d5a64fab5df2a08a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048621"
---
# <a name="creating-internet-requests"></a><span data-ttu-id="cb6fa-102">Crear solicitudes de Internet</span><span class="sxs-lookup"><span data-stu-id="cb6fa-102">Creating Internet Requests</span></span>
<span data-ttu-id="cb6fa-103">Las aplicaciones crean instancias <xref:System.Net.WebRequest> con el método <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cb6fa-104">Este es un método estático que crea una clase derivada de **WebRequest** según el esquema de URI que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="cb6fa-105">Web, archivos y solicitudes de FTP</span><span class="sxs-lookup"><span data-stu-id="cb6fa-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="cb6fa-106">.NET Framework proporciona la clase <xref:System.Net.HttpWebRequest>, que se deriva de **WebRequest**, para controlar las solicitudes HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="cb6fa-107">En la mayoría de los casos, la clase de **WebRequest** proporciona todas las propiedades que debe realizar una solicitud; en cambio, en caso necesario, puede convertir los objetos **WebRequest** creados por el método **WebRequest.Create** al tipo de **HttpWebRequest** para tener acceso a las propiedades específicas de HTTP de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="cb6fa-108">De igual forma, el objeto **HttpWebResponse** controla las respuestas de las solicitudes HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="cb6fa-109">Para tener acceso a las propiedades específicas de HTTP del objeto **HttpWebResponse**, necesita convertir los objetos **WebResponse** al tipo **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="cb6fa-110">.NET Framework también proporciona las clases <xref:System.Net.FileWebRequest> y <xref:System.Net.FileWebResponse> para controlar las solicitudes de los recursos que usan el esquema de URI "file:".</span><span class="sxs-lookup"><span data-stu-id="cb6fa-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="cb6fa-111">Igualmente, las clases <xref:System.Net.FtpWebRequest> y <xref:System.Net.FtpWebResponse> se proporcionan para controlar las solicitudes de los recursos que usan el esquema "ftp:".</span><span class="sxs-lookup"><span data-stu-id="cb6fa-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="cb6fa-112">Si la solicitud es para un recurso que usa cualquiera de estos esquemas, puede usar el método **WebRequest.Create** para obtener un objeto con el que realizar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="cb6fa-113">Para controlar las solicitudes que usan otros protocolos de nivel de aplicación, debe implementar las clases específicas de protocolo derivadas de **WebRequest** y **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="cb6fa-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="cb6fa-114">Para obtener más información, vea [Programming Pluggable Protocols](programming-pluggable-protocols.md) (Programar protocolos acoplables).</span><span class="sxs-lookup"><span data-stu-id="cb6fa-114">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6fa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb6fa-115">See also</span></span>

- [<span data-ttu-id="cb6fa-116">Cómo solicitar datos mediante la clase WebRequest</span><span class="sxs-lookup"><span data-stu-id="cb6fa-116">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="cb6fa-117">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="cb6fa-117">Requesting Data</span></span>](requesting-data.md)
