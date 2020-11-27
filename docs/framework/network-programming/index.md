---
title: Programación para redes en .NET Framework
description: Use estos recursos para integrar la implementación en capas, extensible y administrada de los servicios de Internet que proporciona .NET Framework en sus aplicaciones.
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 50f23e1a343f969ad2cbb3422038921c710b2b1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241686"
---
# <a name="network-programming-in-the-net-framework"></a>Programación para redes en .NET Framework

Microsoft .NET Framework proporciona una implementación por capas, extensible y administrada de servicios de Internet que se puede integrar rápida y fácilmente en las aplicaciones. Las aplicaciones de red se pueden basar en protocolos conectables para poder usar automáticamente los nuevos protocolos de Internet, o pueden utilizar una implementación administrada de la interfaz de Windows Socket para operar con la red en el nivel de socket.  
  
## <a name="in-this-section"></a>En esta sección  

 [Escribir protocolos acoplables](introducing-pluggable-protocols.md)  
 Describe cómo tener acceso a un recurso de Internet independientemente del protocolo de acceso requerido.  
  
 [Solicitud de datos](requesting-data.md)  
 Explica cómo utilizar protocolos conectables para cargar y descargar datos de recursos de Internet.  
  
 [Programming Pluggable Protocols (Programar protocolos acoplables)](programming-pluggable-protocols.md)  
 Explica cómo derivar clases específicas del protocolo para implementar protocolos conectables.  
  
 [Usar protocolos de aplicaciones](using-application-protocols.md)  
 Describe la programación de aplicaciones que usan protocolos de red como TCP, UDP y HTTP.  
  
 [Protocolo de Internet versión 6](internet-protocol-version-6.md)  
 Describe las ventajas del Protocolo de Internet versión 6 (IPv6) con respecto a la versión actual del conjunto Protocolo de Internet (IPv4), y describe el direccionamiento, enrutamiento y configuración automática de IPv6, y cómo habilitar y deshabilitar IPv6.  
  
 [Configuración de aplicaciones de Internet](configuring-internet-applications.md)  
 Explica cómo utilizar archivos de configuración de .NET Framework para configurar aplicaciones de Internet.  
  
 [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](network-tracing.md)  
 Explica cómo utilizar el seguimiento de la red para obtener información sobre las invocaciones de método y el tráfico de red generado por una aplicación administrada.  
  
 [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)  
 Describe cómo utilizar el almacenamiento en caché para las aplicaciones que usan las clases <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>y <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 [Seguridad en la programación para redes](security-in-network-programming.md)  
 Describe cómo usar las técnicas estándar de seguridad y autenticación de Internet.  
  
 [Procedimientos recomendados para las clases System.Net](best-practices-for-system-net-classes.md)  
 Proporciona sugerencias y trucos para obtener el máximo provecho de las aplicaciones de Internet.  
  
 [Acceso a Internet a través de un proxy](accessing-the-internet-through-a-proxy.md)  
 Describe cómo configurar servidores proxy.  
  
 [NetworkInformation](networkinformation.md)  
 Describe cómo recopilar información sobre eventos, cambios, estadísticas y propiedades de red y, explica también cómo determinar si se puede acceder a un host remoto mediante la clase <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> .  
  
 [Cambios realizados en el espacio de nombres System.Uri de la versión 2.0](changes-to-the-system-uri-namespace-in-version-2-0.md)  
 Describe varios cambios realizados en la clase <xref:System.Uri?displayProperty=nameWithType> en la versión 2.0 para corregir un comportamiento incorrecto y para mejorar la capacidad de uso y la seguridad.  
  
 [Compatibilidad de identificadores de recursos internacionales en System.Uri](international-resource-identifier-support-in-system-uri.md)  
 Describe las mejoras realizadas en la clase <xref:System.Uri?displayProperty=nameWithType> en la versión 3.5, 3.0 SP1 y 2.0 SP1 para la compatibilidad con el identificador de recursos internacionales (IRI) y el nombre de dominio internacionalizado (IDN).  
  
 [Mejoras de rendimiento de socket en la versión 3.5](socket-performance-enhancements-in-version-3-5.md)  
 Describe un conjunto de mejoras realizadas en la clase <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> en la versión 3.5, 3.0 SP1 y 2.0 SP1 que proporcionan un patrón asincrónico alternativo que pueden usar las aplicaciones de socket de alto rendimiento especializadas.  
  
 [Protocolo de resolución de nombres del mismo nivel](peer-name-resolution-protocol.md)  
 Describe la compatibilidad agregada en la versión 3.5 para admitir el Protocolo de resolución de nombres de mismo nivel (PNRP), un protocolo de registro y resolución de nombres dinámico que no requiere servidor. El espacio de nombres <xref:System.Net.PeerToPeer?displayProperty=nameWithType> admite el uso de estas nuevas características.  
  
 [Colaboración de punto a punto](peer-to-peer-collaboration.md)  
 Describe la compatibilidad agregada en la versión 3.5 para admitir la interfaz Peer-to-Peer Collaboration basada en PNRP. El espacio de nombres <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> admite el uso de estas nuevas características.  
  
 [Cambios en la autenticación NTLM para HttpWebRequest en la versión 3.5 SP1](changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 Describe los cambios de seguridad realizados en la versión 3.5 SP1 que afectan al modo en que las clases <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>y clases relacionadas del espacio de nombres System.Net controlan la autenticación de Windows integrada.  
  
 [Autenticación de Windows integrada con protección ampliada](integrated-windows-authentication-with-extended-protection.md)  
 Describe las mejoras para la protección extendida que afectan al modo en que las clases <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>y clases relacionadas del espacio de nombres <xref:System.Net?displayProperty=nameWithType> y espacios de nombres relacionados controlan la autenticación de Windows integrada.  
  
 [NAT Traversal mediante IPv6 y Teredo](nat-traversal-using-ipv6-and-teredo.md)  
 Describe las mejoras agregadas a los espacios de nombres <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>y <xref:System.Net.Sockets?displayProperty=nameWithType> para admitir NAT traversal mediante IPv6 y Teredo.  
  
 [Aislamiento de red para aplicaciones de la Tienda Windows](network-isolation-for-windows-store-apps.md)  
 Describe el impacto del aislamiento de red al usar las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Http>y <xref:System.Net.Http.Headers> en aplicaciones de la Tienda Windows 8.x.  
  
 [Network Programming Samples (Ejemplos de programación de red)](network-programming-samples.md)  
 Vínculos a ejemplos de programación de red descargables que utilizan las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>y <xref:System.Net.Sockets> .  
  
## <a name="reference"></a>Referencia  

 <xref:System.Net?displayProperty=nameWithType>  
 Proporciona una interfaz de programación sencilla para muchos de los protocolos que se utilizan en las redes actuales. Las clases <xref:System.Net.WebRequest?displayProperty=nameWithType> y <xref:System.Net.WebResponse?displayProperty=nameWithType> de este espacio de nombres son la base para los protocolos conectables.  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 Define los tipos y las enumeraciones utilizadas para definir las directivas de caché de los recursos obtenidos mediante las clases <xref:System.Net.WebRequest?displayProperty=nameWithType> y <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 Clases que utilizan las aplicaciones para acceder y actualizar la configuración de los espacios de nombres System.Net mediante programación.  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 Clases que proporcionan una interfaz de programación para aplicaciones HTTP modernas.  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 Proporciona compatibilidad con las colecciones de encabezados HTTP utilizadas por el espacio de nombres <xref:System.Net.Http?displayProperty=nameWithType> .  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 Clases para redactar y enviar correo mediante el protocolo SMTP.  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 Define los tipos que se utilizan para representar los encabezados MIME (Multipurpose Internet Mail Exchange) utilizados por las clases del espacio de nombres <xref:System.Net.Mail?displayProperty=nameWithType> .  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 Clases para recopilar información sobre eventos, cambios, estadísticas y propiedades de red mediante programación.  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 Proporciona una aplicación administrada del Protocolo de resolución de nombres de mismo nivel (PNRP) para desarrolladores.  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 Proporciona una implementación administrada de la interfaz Peer-to-Peer Collaboration para desarrolladores.  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 Clases para proporcionar secuencias de red para comunicaciones seguras entre hosts.  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 Proporciona una implementación administrada de la interfaz de Windows Sockets (Winsock) para desarrolladores que necesitan controlar el acceso a la red.  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 Proporciona una implementación administrada de la interfaz de WebSocket para desarrolladores.  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 Proporciona una representación de objeto de un identificador de recursos uniforme (URI) y un acceso sencillo a las partes del identificador URI.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 Proporciona compatibilidad con la autenticación mediante la protección extendida de las aplicaciones.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 Proporciona compatibilidad con la configuración de la autenticación mediante la protección extendida de las aplicaciones.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos recomendados sobre la seguridad de la capa de transporte (TLS) con .NET Framework](tls.md)
- [Temas de procedimientos de programación de redes](network-programming-how-to-topics.md)
- [Network Programming Samples (Ejemplos de programación de red)](network-programming-samples.md)
- [Ejemplo de HttpClient](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
