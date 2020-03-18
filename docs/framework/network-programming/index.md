---
title: Programación para redes en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 1e7f0123ab07fd4e83eea957b72bf79eeeecef2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74204694"
---
# <a name="network-programming-in-the-net-framework"></a><span data-ttu-id="44228-102">Programación para redes en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="44228-102">Network Programming in the .NET Framework</span></span>
<span data-ttu-id="44228-103">Microsoft .NET Framework proporciona una implementación por capas, extensible y administrada de servicios de Internet que se puede integrar rápida y fácilmente en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="44228-103">The Microsoft .NET Framework provides a layered, extensible, and managed implementation of Internet services that can be quickly and easily integrated into your applications.</span></span> <span data-ttu-id="44228-104">Las aplicaciones de red se pueden basar en protocolos conectables para poder usar automáticamente los nuevos protocolos de Internet, o pueden utilizar una implementación administrada de la interfaz de Windows Socket para operar con la red en el nivel de socket.</span><span class="sxs-lookup"><span data-stu-id="44228-104">Your network applications can build on pluggable protocols to automatically take advantage of new Internet protocols, or they can use a managed implementation of the Windows socket interface to work with the network on the socket level.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44228-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="44228-105">In This Section</span></span>  

 [<span data-ttu-id="44228-106">Escribir protocolos acoplables</span><span class="sxs-lookup"><span data-stu-id="44228-106">Introducing Pluggable Protocols</span></span>](introducing-pluggable-protocols.md)  
 <span data-ttu-id="44228-107">Describe cómo tener acceso a un recurso de Internet independientemente del protocolo de acceso requerido.</span><span class="sxs-lookup"><span data-stu-id="44228-107">Describes how to access an Internet resource without regard to the access protocol that it requires.</span></span>  
  
 [<span data-ttu-id="44228-108">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="44228-108">Requesting Data</span></span>](requesting-data.md)  
 <span data-ttu-id="44228-109">Explica cómo utilizar protocolos conectables para cargar y descargar datos de recursos de Internet.</span><span class="sxs-lookup"><span data-stu-id="44228-109">Explains how to use pluggable protocols to upload and download data from Internet resources.</span></span>  
  
 [<span data-ttu-id="44228-110">Programar protocolos acoplables</span><span class="sxs-lookup"><span data-stu-id="44228-110">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)  
 <span data-ttu-id="44228-111">Explica cómo derivar clases específicas del protocolo para implementar protocolos conectables.</span><span class="sxs-lookup"><span data-stu-id="44228-111">Explains how to derive protocol-specific classes to implement pluggable protocols.</span></span>  
  
 [<span data-ttu-id="44228-112">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="44228-112">Using Application Protocols</span></span>](using-application-protocols.md)  
 <span data-ttu-id="44228-113">Describe la programación de aplicaciones que usan protocolos de red como TCP, UDP y HTTP.</span><span class="sxs-lookup"><span data-stu-id="44228-113">Describes programming applications that take advantage of network protocols such as TCP, UDP, and HTTP.</span></span>  
  
 [<span data-ttu-id="44228-114">Protocolo de Internet versión 6</span><span class="sxs-lookup"><span data-stu-id="44228-114">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)  
 <span data-ttu-id="44228-115">Describe las ventajas del Protocolo de Internet versión 6 (IPv6) con respecto a la versión actual del conjunto Protocolo de Internet (IPv4), y describe el direccionamiento, enrutamiento y configuración automática de IPv6, y cómo habilitar y deshabilitar IPv6.</span><span class="sxs-lookup"><span data-stu-id="44228-115">Describes the advantages of Internet Protocol version 6 (IPv6) over the current version of the Internet Protocol suite (IPv4), describes IPv6 addressing, routing and auto-configuration, and how to enable and disable IPv6.</span></span>  
  
 [<span data-ttu-id="44228-116">Configuración de aplicaciones de Internet</span><span class="sxs-lookup"><span data-stu-id="44228-116">Configuring Internet Applications</span></span>](configuring-internet-applications.md)  
 <span data-ttu-id="44228-117">Explica cómo utilizar archivos de configuración de .NET Framework para configurar aplicaciones de Internet.</span><span class="sxs-lookup"><span data-stu-id="44228-117">Explains how to use the .NET Framework configuration files to configure Internet applications.</span></span>  
  
 [<span data-ttu-id="44228-118">Traza de la red en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="44228-118">Network Tracing in the .NET Framework</span></span>](network-tracing.md)  
 <span data-ttu-id="44228-119">Explica cómo utilizar el seguimiento de la red para obtener información sobre las invocaciones de método y el tráfico de red generado por una aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="44228-119">Explains how to use network tracing to get information about method invocations and network traffic generated by a managed application.</span></span>  
  
 [<span data-ttu-id="44228-120">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="44228-120">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)  
 <span data-ttu-id="44228-121">Describe cómo utilizar el almacenamiento en caché para las aplicaciones que usan las clases <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>y <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="44228-121">Describes how to use caching for applications that use the <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>, and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 [<span data-ttu-id="44228-122">Seguridad en la programación para redes</span><span class="sxs-lookup"><span data-stu-id="44228-122">Security in Network Programming</span></span>](security-in-network-programming.md)  
 <span data-ttu-id="44228-123">Describe cómo usar las técnicas estándar de seguridad y autenticación de Internet.</span><span class="sxs-lookup"><span data-stu-id="44228-123">Describes how to use standard Internet security and authentication techniques.</span></span>  
  
 [<span data-ttu-id="44228-124">Procedimientos recomendados para las clases System.Net</span><span class="sxs-lookup"><span data-stu-id="44228-124">Best Practices for System.Net Classes</span></span>](best-practices-for-system-net-classes.md)  
 <span data-ttu-id="44228-125">Proporciona sugerencias y trucos para obtener el máximo provecho de las aplicaciones de Internet.</span><span class="sxs-lookup"><span data-stu-id="44228-125">Provides tips and tricks for getting the most out of your Internet applications.</span></span>  
  
 [<span data-ttu-id="44228-126">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="44228-126">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)  
 <span data-ttu-id="44228-127">Describe cómo configurar servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="44228-127">Describes how to configure proxies.</span></span>  
  
 [<span data-ttu-id="44228-128">NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="44228-128">NetworkInformation</span></span>](networkinformation.md)  
 <span data-ttu-id="44228-129">Describe cómo recopilar información sobre eventos, cambios, estadísticas y propiedades de red y, explica también cómo determinar si se puede acceder a un host remoto mediante la clase <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="44228-129">Describes how to gather information about network events, changes, statistics, and properties and also explains how to determine whether a remote host is reachable by using the <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> class.</span></span>  
  
 [<span data-ttu-id="44228-130">Cambios realizados en el espacio de nombres System.Uri de la versión 2.0</span><span class="sxs-lookup"><span data-stu-id="44228-130">Changes to the System.Uri namespace in Version 2.0</span></span>](changes-to-the-system-uri-namespace-in-version-2-0.md)  
 <span data-ttu-id="44228-131">Describe varios cambios realizados en la clase <xref:System.Uri?displayProperty=nameWithType> en la versión 2.0 para corregir un comportamiento incorrecto y para mejorar la capacidad de uso y la seguridad.</span><span class="sxs-lookup"><span data-stu-id="44228-131">Describes several changes made to the <xref:System.Uri?displayProperty=nameWithType> class in Version 2.0 to fixed incorrect behavior, enhance usability, and enhance security.</span></span>  
  
 [<span data-ttu-id="44228-132">Compatibilidad de identificadores de recursos internacionales en System.Uri</span><span class="sxs-lookup"><span data-stu-id="44228-132">International Resource Identifier Support in System.Uri</span></span>](international-resource-identifier-support-in-system-uri.md)  
 <span data-ttu-id="44228-133">Describe las mejoras realizadas en la clase <xref:System.Uri?displayProperty=nameWithType> en la versión 3.5, 3.0 SP1 y 2.0 SP1 para la compatibilidad con el identificador de recursos internacionales (IRI) y el nombre de dominio internacionalizado (IDN).</span><span class="sxs-lookup"><span data-stu-id="44228-133">Describes enhancements to the <xref:System.Uri?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 for International Resource Identifier (IRI) and Internationalized Domain Name (IDN) support.</span></span>  
  
 [<span data-ttu-id="44228-134">Mejoras de rendimiento de socket en la versión 3.5</span><span class="sxs-lookup"><span data-stu-id="44228-134">Socket Performance Enhancements in Version 3.5</span></span>](socket-performance-enhancements-in-version-3-5.md)  
 <span data-ttu-id="44228-135">Describe un conjunto de mejoras realizadas en la clase <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> en la versión 3.5, 3.0 SP1 y 2.0 SP1 que proporcionan un patrón asincrónico alternativo que pueden usar las aplicaciones de socket de alto rendimiento especializadas.</span><span class="sxs-lookup"><span data-stu-id="44228-135">Describes a set of enhancements to the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class in Version 3.5, 3.0 SP1, and 2.0 SP1 that provide an alternative asynchronous pattern that can be used by specialized high-performance socket applications.</span></span>  
  
 [<span data-ttu-id="44228-136">Protocolo de resolución de nombres del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="44228-136">Peer Name Resolution Protocol</span></span>](peer-name-resolution-protocol.md)  
 <span data-ttu-id="44228-137">Describe la compatibilidad agregada en la versión 3.5 para admitir el Protocolo de resolución de nombres de mismo nivel (PNRP), un protocolo de registro y resolución de nombres dinámico que no requiere servidor.</span><span class="sxs-lookup"><span data-stu-id="44228-137">Describes support added in Version 3.5 to support the Peer Name Resolution Protocol (PNRP), a serverless and dynamic name registration and name resolution protocol.</span></span> <span data-ttu-id="44228-138">El espacio de nombres <xref:System.Net.PeerToPeer?displayProperty=nameWithType> admite el uso de estas nuevas características.</span><span class="sxs-lookup"><span data-stu-id="44228-138">These new features are supported by the <xref:System.Net.PeerToPeer?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="44228-139">Colaboración de punto a punto</span><span class="sxs-lookup"><span data-stu-id="44228-139">Peer-to-Peer Collaboration</span></span>](peer-to-peer-collaboration.md)  
 <span data-ttu-id="44228-140">Describe la compatibilidad agregada en la versión 3.5 para admitir la interfaz Peer-to-Peer Collaboration basada en PNRP.</span><span class="sxs-lookup"><span data-stu-id="44228-140">Describes support added in Version 3.5 to support the Peer-to-Peer Collaboration that builds on PNRP.</span></span> <span data-ttu-id="44228-141">El espacio de nombres <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> admite el uso de estas nuevas características.</span><span class="sxs-lookup"><span data-stu-id="44228-141">These new features are supported by the <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="44228-142">Cambios en la autenticación NTLM para HttpWebRequest en la versión 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="44228-142">Changes to NTLM authentication for HttpWebRequest in Version 3.5 SP1</span></span>](changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 <span data-ttu-id="44228-143">Describe los cambios de seguridad realizados en la versión 3.5 SP1 que afectan al modo en que las clases <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>y clases relacionadas del espacio de nombres System.Net controlan la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="44228-143">Describes security changes made in Version 3.5 SP1 that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the System.Net namespace.</span></span>  
  
 [<span data-ttu-id="44228-144">Autenticación de Windows integrada con protección ampliada</span><span class="sxs-lookup"><span data-stu-id="44228-144">Integrated Windows Authentication with Extended Protection</span></span>](integrated-windows-authentication-with-extended-protection.md)  
 <span data-ttu-id="44228-145">Describe las mejoras para la protección extendida que afectan al modo en que las clases <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>y clases relacionadas del espacio de nombres <xref:System.Net?displayProperty=nameWithType> y espacios de nombres relacionados controlan la autenticación de Windows integrada.</span><span class="sxs-lookup"><span data-stu-id="44228-145">Describes enhancements for extended protection that affect how integrated Windows authentication is handled by the <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>, and related classes in the <xref:System.Net?displayProperty=nameWithType> and related namespaces.</span></span>  
  
 [<span data-ttu-id="44228-146">NAT Traversal mediante IPv6 y Teredo</span><span class="sxs-lookup"><span data-stu-id="44228-146">NAT Traversal using IPv6 and Teredo</span></span>](nat-traversal-using-ipv6-and-teredo.md)  
 <span data-ttu-id="44228-147">Describe las mejoras agregadas a los espacios de nombres <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>y <xref:System.Net.Sockets?displayProperty=nameWithType> para admitir NAT traversal mediante IPv6 y Teredo.</span><span class="sxs-lookup"><span data-stu-id="44228-147">Describes enhancements added to the <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>, and <xref:System.Net.Sockets?displayProperty=nameWithType> namespaces to support NAT traversal using IPv6 and Teredo.</span></span>  
  
 [<span data-ttu-id="44228-148">Aislamiento de red para aplicaciones de la Tienda Windows</span><span class="sxs-lookup"><span data-stu-id="44228-148">Network Isolation for Windows Store Apps</span></span>](network-isolation-for-windows-store-apps.md)  
 <span data-ttu-id="44228-149">Describe el impacto del aislamiento de red al usar las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Http>y <xref:System.Net.Http.Headers> en aplicaciones de la Tienda Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="44228-149">Describes the impact of network isolation when classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces are used in Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="44228-150">Ejemplos de programación de red</span><span class="sxs-lookup"><span data-stu-id="44228-150">Network Programming Samples</span></span>](network-programming-samples.md)  
 <span data-ttu-id="44228-151">Vínculos a ejemplos de programación de red descargables que utilizan las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>y <xref:System.Net.Sockets> .</span><span class="sxs-lookup"><span data-stu-id="44228-151">Links to downloadable network programming samples that use classes in the <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> namespaces.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="44228-152">Referencia</span><span class="sxs-lookup"><span data-stu-id="44228-152">Reference</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <span data-ttu-id="44228-153">Proporciona una interfaz de programación sencilla para muchos de los protocolos que se utilizan en las redes actuales.</span><span class="sxs-lookup"><span data-stu-id="44228-153">Provides a simple programming interface for many of the protocols used on networks today.</span></span> <span data-ttu-id="44228-154">Las clases <xref:System.Net.WebRequest?displayProperty=nameWithType> y <xref:System.Net.WebResponse?displayProperty=nameWithType> de este espacio de nombres son la base para los protocolos conectables.</span><span class="sxs-lookup"><span data-stu-id="44228-154">The <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.WebResponse?displayProperty=nameWithType> classes in this namespace are the basis for pluggable protocols.</span></span>  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 <span data-ttu-id="44228-155">Define los tipos y las enumeraciones utilizadas para definir las directivas de caché de los recursos obtenidos mediante las clases <xref:System.Net.WebRequest?displayProperty=nameWithType> y <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="44228-155">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest?displayProperty=nameWithType> and <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> classes.</span></span>  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="44228-156">Clases que utilizan las aplicaciones para acceder y actualizar la configuración de los espacios de nombres System.Net mediante programación.</span><span class="sxs-lookup"><span data-stu-id="44228-156">Classes that applications use to programmatically access and update configuration settings for the System.Net namespaces.</span></span>  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 <span data-ttu-id="44228-157">Clases que proporcionan una interfaz de programación para aplicaciones HTTP modernas.</span><span class="sxs-lookup"><span data-stu-id="44228-157">Classes that provides a programming interface for modern HTTP applications.</span></span>  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 <span data-ttu-id="44228-158">Proporciona compatibilidad con las colecciones de encabezados HTTP utilizadas por el espacio de nombres <xref:System.Net.Http?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="44228-158">Provides support for collections of HTTP headers used by the <xref:System.Net.Http?displayProperty=nameWithType> namespace</span></span>  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 <span data-ttu-id="44228-159">Clases para redactar y enviar correo mediante el protocolo SMTP.</span><span class="sxs-lookup"><span data-stu-id="44228-159">Classes to compose and send mail using the SMTP protocol.</span></span>  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 <span data-ttu-id="44228-160">Define los tipos que se utilizan para representar los encabezados MIME (Multipurpose Internet Mail Exchange) utilizados por las clases del espacio de nombres <xref:System.Net.Mail?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="44228-160">Defines types that are used to represent Multipurpose Internet Mail Exchange (MIME) headers used by classes in the <xref:System.Net.Mail?displayProperty=nameWithType> namespace.</span></span>  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 <span data-ttu-id="44228-161">Clases para recopilar información sobre eventos, cambios, estadísticas y propiedades de red mediante programación.</span><span class="sxs-lookup"><span data-stu-id="44228-161">Classes to programmatically gather information about network events, changes, statistics, and properties.</span></span>  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 <span data-ttu-id="44228-162">Proporciona una aplicación administrada del Protocolo de resolución de nombres de mismo nivel (PNRP) para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="44228-162">Provides a managed implementation of the Peer Name Resolution Protocol (PNRP) for developers.</span></span>  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 <span data-ttu-id="44228-163">Proporciona una implementación administrada de la interfaz Peer-to-Peer Collaboration para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="44228-163">Provides a managed implementation of the Peer-to-Peer Collaboration interface for developers.</span></span>  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 <span data-ttu-id="44228-164">Clases para proporcionar secuencias de red para comunicaciones seguras entre hosts.</span><span class="sxs-lookup"><span data-stu-id="44228-164">Classes to provide network streams for secure communications between hosts.</span></span>  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <span data-ttu-id="44228-165">Proporciona una implementación administrada de la interfaz de Windows Sockets (Winsock) para desarrolladores que necesitan controlar el acceso a la red.</span><span class="sxs-lookup"><span data-stu-id="44228-165">Provides a managed implementation of the Windows Sockets (Winsock) interface for developers who need to help control access to the network.</span></span>  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 <span data-ttu-id="44228-166">Proporciona una implementación administrada de la interfaz de WebSocket para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="44228-166">Provides a managed implementation of the WebSocket interface for developers.</span></span>  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 <span data-ttu-id="44228-167">Proporciona una representación de objeto de un identificador de recursos uniforme (URI) y un acceso sencillo a las partes del identificador URI.</span><span class="sxs-lookup"><span data-stu-id="44228-167">Provides an object representation of a uniform resource identifier (URI) and easy access to the parts of the URI.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 <span data-ttu-id="44228-168">Proporciona compatibilidad con la autenticación mediante la protección extendida de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="44228-168">Provides support for authentication using extended protection for applications.</span></span>  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="44228-169">Proporciona compatibilidad con la configuración de la autenticación mediante la protección extendida de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="44228-169">Provides support for configuration of authentication using extended protection for applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44228-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="44228-170">See also</span></span>

- [<span data-ttu-id="44228-171">Procedimientos recomendados sobre la seguridad de la capa de transporte (TLS) con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="44228-171">Transport Layer Security (TLS) best practices with .NET Framework</span></span>](tls.md)
- [<span data-ttu-id="44228-172">Temas de procedimientos de programación de redes</span><span class="sxs-lookup"><span data-stu-id="44228-172">Network Programming How-to Topics</span></span>](network-programming-how-to-topics.md)
- [<span data-ttu-id="44228-173">Ejemplos de programación de red</span><span class="sxs-lookup"><span data-stu-id="44228-173">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="44228-174">Ejemplo de HttpClient</span><span class="sxs-lookup"><span data-stu-id="44228-174">HttpClient Sample</span></span>](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
