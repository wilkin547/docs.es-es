---
title: HTTP
description: Obtenga información sobre la compatibilidad total con HTTP que proporciona .NET Framework mediante el uso de las clases HttpWebRequest y HttpWebResponse.
ms.date: 03/30/2017
helpviewer_keywords:
- protocols, HTTP
- sending data, HTTP
- HttpWebResponse class, sending and receiving data
- HTTP
- receiving data, HTTP
- application protocols, HTTP
- Internet, HTTP
- network resources, HTTP
- HTTP, about HTTP
- HttpWebRequest class, sending and receiving data
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
ms.openlocfilehash: ffb7a5d027ef7691d03caf0ac45d4a3dd9bdb652
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502423"
---
# <a name="http"></a><span data-ttu-id="b4495-103">HTTP</span><span class="sxs-lookup"><span data-stu-id="b4495-103">HTTP</span></span>
<span data-ttu-id="b4495-104">.NET Framework proporciona compatibilidad completa para el protocolo HTTP, que constituye la mayor parte de todo el tráfico de Internet, con las clases <xref:System.Net.HttpWebRequest> y <xref:System.Net.HttpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="b4495-104">The .NET Framework provides comprehensive support for the HTTP protocol, which makes up the majority of all Internet traffic, with the <xref:System.Net.HttpWebRequest> and <xref:System.Net.HttpWebResponse> classes.</span></span> <span data-ttu-id="b4495-105">Estas clases, derivadas de <xref:System.Net.WebRequest> y <xref:System.Net.WebResponse>, se devuelven de manera predeterminada siempre que el método estático <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> detecte un URI que comience por "http" o "https".</span><span class="sxs-lookup"><span data-stu-id="b4495-105">These classes, derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, are returned by default whenever the static method <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> encounters a URI beginning with "http" or "https".</span></span> <span data-ttu-id="b4495-106">En la mayoría de los casos, las clases **WebRequest** y **WebResponse** proporcionan todo lo necesario para realizar la solicitud, pero si necesita tener acceso a las características específicas de HTTP expuestas como propiedades, puede convertir estas clases en **HttpWebRequest** o **HttpWebResponse**.</span><span class="sxs-lookup"><span data-stu-id="b4495-106">In most cases, the **WebRequest** and **WebResponse** classes provide all that is necessary to make the request, but if you need access to the HTTP-specific features exposed as properties, you can typecast these classes to **HttpWebRequest** or **HttpWebResponse**.</span></span>  
  
 <span data-ttu-id="b4495-107">**HttpWebRequest** y **HttpWebResponse** encapsulan una transacción de solicitud y respuesta HTTP estándar y proporcionan acceso a los encabezados HTTP comunes.</span><span class="sxs-lookup"><span data-stu-id="b4495-107">**HttpWebRequest** and **HttpWebResponse** encapsulate a standard HTTP request-and-response transaction and provide access to common HTTP headers.</span></span> <span data-ttu-id="b4495-108">Estas clases también admiten la mayoría de las características de HTTP 1.1, incluidas la canalización, envío y recepción de datos en fragmentos, autenticación, preautenticación, cifrado, compatibilidad de proxy, validación de certificados de servidor y administración de conexiones.</span><span class="sxs-lookup"><span data-stu-id="b4495-108">These classes also support most HTTP 1.1 features, including pipelining, sending and receiving data in chunks, authentication, preauthentication, encryption, proxy support, server certificate validation, and connection management.</span></span> <span data-ttu-id="b4495-109">Los encabezados y los encabezados personalizados que no se proporcionan mediante propiedades pueden almacenarse y se puede acceder a ellos mediante la propiedad **Headers**.</span><span class="sxs-lookup"><span data-stu-id="b4495-109">Custom headers and headers not provided through properties can be stored in and accessed through the **Headers** property.</span></span>  
  
 <span data-ttu-id="b4495-110">**HttpWebRequest** es la clase predeterminada que usa **WebRequest** y no necesita registrarse antes de que pueda pasar un URI al método **WebRequest.Create**.</span><span class="sxs-lookup"><span data-stu-id="b4495-110">**HttpWebRequest** is the default class used by **WebRequest** and does not need to be registered before you can pass a URI to the **WebRequest.Create** method.</span></span>  
  
 <span data-ttu-id="b4495-111">Puede hacer que su aplicación siga las redirecciones de HTTP automáticamente estableciendo la propiedad <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> en **True** (el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b4495-111">You can make your application follow HTTP redirects automatically by setting the <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A> property to **true** (the default).</span></span> <span data-ttu-id="b4495-112">La aplicación redirigirá las solicitudes, y la propiedad <xref:System.Net.HttpWebResponse.ResponseUri%2A> de **HttpWebResponse** contendrá el recurso web actual que ha respondido a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b4495-112">The application will redirect requests, and the <xref:System.Net.HttpWebResponse.ResponseUri%2A> property of **HttpWebResponse** will contain the actual Web resource that responded to the request.</span></span> <span data-ttu-id="b4495-113">Si establece **AllowAutoRedirect** en **False**, su aplicación debe poder controlar las redirecciones como errores de protocolo HTTP.</span><span class="sxs-lookup"><span data-stu-id="b4495-113">If you set **AllowAutoRedirect** to **false**, your application must be able to handle redirects as HTTP protocol errors.</span></span>  
  
 <span data-ttu-id="b4495-114">Las aplicaciones reciben errores de protocolo HTTP capturando <xref:System.Net.WebException> con <xref:System.Net.WebException.Status%2A> establecido en <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="b4495-114">Applications receive HTTP protocol errors by catching a <xref:System.Net.WebException> with the <xref:System.Net.WebException.Status%2A> set to <xref:System.Net.WebExceptionStatus>.</span></span> <span data-ttu-id="b4495-115">La propiedad <xref:System.Net.WebException.Response%2A> contiene la **WebResponse** que ha enviado el servidor e indica el error HTTP actual que se ha detectado.</span><span class="sxs-lookup"><span data-stu-id="b4495-115">The <xref:System.Net.WebException.Response%2A> property contains the **WebResponse** sent by the server and indicates the actual HTTP error encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4495-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4495-116">See also</span></span>

- [<span data-ttu-id="b4495-117">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="b4495-117">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="b4495-118">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b4495-118">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="b4495-119">Cómo: Acceder a propiedades específicas de HTTP</span><span class="sxs-lookup"><span data-stu-id="b4495-119">How to: Access HTTP-Specific Properties</span></span>](how-to-access-http-specific-properties.md)
