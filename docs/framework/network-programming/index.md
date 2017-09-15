---
title: "Programación para redes en .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
caps.latest.revision: 24
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4b63aeadb795e5457266bd75d1f2bf0e695eac7f
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2017

---
# <a name="network-programming-in-the-net-framework"></a>Programación para redes en .NET Framework
Microsoft .NET Framework proporciona una implementación por capas, extensible y administrada de servicios de Internet que se puede integrar rápida y fácilmente en las aplicaciones. Las aplicaciones de red se pueden basar en protocolos conectables para poder usar automáticamente los nuevos protocolos de Internet, o pueden utilizar una implementación administrada de la interfaz de Windows Socket para operar con la red en el nivel de socket.  
  
## <a name="in-this-section"></a>En esta sección  
 [Escribir protocolos acoplables](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 Describe cómo tener acceso a un recurso de Internet independientemente del protocolo de acceso requerido.  
  
 [Solicitud de datos](../../../docs/framework/network-programming/requesting-data.md)  
 Explica cómo utilizar protocolos conectables para cargar y descargar datos de recursos de Internet.  
  
 [Programar protocolos acoplables](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 Explica cómo derivar clases específicas del protocolo para implementar protocolos conectables.  
  
 [Usar protocolos de aplicaciones](../../../docs/framework/network-programming/using-application-protocols.md)  
 Describe la programación de aplicaciones que usan protocolos de red como TCP, UDP y HTTP.  
  
 [Protocolo de Internet versión 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 Describe las ventajas del Protocolo de Internet versión 6 (IPv6) con respecto a la versión actual del conjunto Protocolo de Internet (IPv4), y describe el direccionamiento, enrutamiento y configuración automática de IPv6, y cómo habilitar y deshabilitar IPv6.  
  
 [Configuración de aplicaciones de Internet](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 Explica cómo utilizar archivos de configuración de .NET Framework para configurar aplicaciones de Internet.  
  
 [Traza de la red en .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 Explica cómo utilizar el seguimiento de la red para obtener información sobre las invocaciones de método y el tráfico de red generado por una aplicación administrada.  
  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 Describe cómo utilizar el almacenamiento en caché para las aplicaciones que usan las clases <xref:System.Net.WebClient?displayProperty=fullName>, <xref:System.Net.WebRequest?displayProperty=fullName>y <xref:System.Net.HttpWebRequest?displayProperty=fullName> .  
  
 [Seguridad en la programación para redes](../../../docs/framework/network-programming/security-in-network-programming.md)  
 Describe cómo usar las técnicas estándar de seguridad y autenticación de Internet.  
  
 [Procedimientos recomendados para las clases System.Net](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 Proporciona sugerencias y trucos para obtener el máximo provecho de las aplicaciones de Internet.  
  
 [Acceso a Internet a través de un proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 Describe cómo configurar servidores proxy.  
  
 [NetworkInformation](../../../docs/framework/network-programming/networkinformation.md)  
 Describe cómo recopilar información sobre eventos, cambios, estadísticas y propiedades de red y, explica también cómo determinar si se puede acceder a un host remoto mediante la clase <xref:System.Net.NetworkInformation.Ping?displayProperty=fullName> .  
  
 [Cambios realizados en el espacio de nombres System.Uri de la versión 2.0](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 Describe varios cambios realizados en la clase <xref:System.Uri?displayProperty=fullName> en la versión 2.0 para corregir un comportamiento incorrecto y para mejorar la capacidad de uso y la seguridad.  
  
 [Compatibilidad de identificadores de recursos internacionales en System.Uri](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 Describe las mejoras realizadas en la clase <xref:System.Uri?displayProperty=fullName> en la versión 3.5, 3.0 SP1 y 2.0 SP1 para la compatibilidad con el identificador de recursos internacionales (IRI) y el nombre de dominio internacionalizado (IDN).  
  
 [Mejoras de rendimiento de socket en la versión 3.5](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 Describe un conjunto de mejoras realizadas en la clase <xref:System.Net.Sockets.Socket?displayProperty=fullName> en la versión 3.5, 3.0 SP1 y 2.0 SP1 que proporcionan un patrón asincrónico alternativo que pueden usar las aplicaciones de socket de alto rendimiento especializadas.  
  
 [Protocolo de resolución de nombres del mismo nivel](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 Describe la compatibilidad agregada en la versión 3.5 para admitir el Protocolo de resolución de nombres de mismo nivel (PNRP), un protocolo de registro y resolución de nombres dinámico que no requiere servidor. El espacio de nombres <xref:System.Net.PeerToPeer?displayProperty=fullName> admite el uso de estas nuevas características.  
  
 [Colaboración de punto a punto](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 Describe la compatibilidad agregada en la versión 3.5 para admitir la interfaz Peer-to-Peer Collaboration basada en PNRP. El espacio de nombres <xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName> admite el uso de estas nuevas características.  
  
 [Cambios en la autenticación NTLM para HttpWebRequest en la versión 3.5 SP1](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 Describe los cambios de seguridad realizados en la versión 3.5 SP1 que afectan al modo en que las clases <xref:System.Net.HttpWebRequest?displayProperty=fullName>, <xref:System.Net.HttpListener?displayProperty=fullName>, <xref:System.Net.Security.NegotiateStream?displayProperty=fullName>y clases relacionadas del espacio de nombres System.Net controlan la autenticación de Windows integrada.  
  
 [Autenticación de Windows integrada con protección ampliada](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 Describe las mejoras para la protección extendida que afectan al modo en que las clases <xref:System.Net.HttpWebRequest?displayProperty=fullName>, <xref:System.Net.HttpListener?displayProperty=fullName>, <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>, <xref:System.Net.Security.SslStream?displayProperty=fullName>, <xref:System.Net.Security.NegotiateStream?displayProperty=fullName>y clases relacionadas del espacio de nombres <xref:System.Net?displayProperty=fullName> y espacios de nombres relacionados controlan la autenticación de Windows integrada.  
  
 [NAT Traversal mediante IPv6 y Teredo](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 Describe las mejoras agregadas a los espacios de nombres <xref:System.Net?displayProperty=fullName>, <xref:System.Net.NetworkInformation?displayProperty=fullName>y <xref:System.Net.Sockets?displayProperty=fullName> para admitir NAT traversal mediante IPv6 y Teredo.  
  
 [Aislamiento de red para aplicaciones de la Tienda Windows](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 Describe el impacto de aislamiento de red cuando se usan las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Http>y <xref:System.Net.Http.Headers> en aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .  
  
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)  
 Vínculos a ejemplos de programación de red descargables que utilizan las clases de los espacios de nombres <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>y <xref:System.Net.Sockets> .  
  
## <a name="reference"></a>Referencia  
 <xref:System.Net?displayProperty=fullName>  
 Proporciona una interfaz de programación sencilla para muchos de los protocolos que se utilizan en las redes actuales. Las clases <xref:System.Net.WebRequest?displayProperty=fullName> y <xref:System.Net.WebResponse?displayProperty=fullName> de este espacio de nombres son la base para los protocolos conectables.  
  
 <xref:System.Net.Cache?displayProperty=fullName>  
 Define los tipos y las enumeraciones utilizadas para definir las directivas de caché de los recursos obtenidos mediante las clases <xref:System.Net.WebRequest?displayProperty=fullName> y <xref:System.Net.HttpWebRequest?displayProperty=fullName> .  
  
 <xref:System.Net.Configuration?displayProperty=fullName>  
 Clases que utilizan las aplicaciones para acceder y actualizar la configuración de los espacios de nombres System.Net mediante programación.  
  
 <xref:System.Net.Http?displayProperty=fullName>  
 Clases que proporcionan una interfaz de programación para aplicaciones HTTP modernas.  
  
 <xref:System.Net.Http.Headers?displayProperty=fullName>  
 Proporciona compatibilidad con las colecciones de encabezados HTTP utilizadas por el espacio de nombres <xref:System.Net.Http?displayProperty=fullName> .  
  
 <xref:System.Net.Mail?displayProperty=fullName>  
 Clases para redactar y enviar correo mediante el protocolo SMTP.  
  
 <xref:System.Net.Mime?displayProperty=fullName>  
 Define los tipos que se utilizan para representar los encabezados MIME (Multipurpose Internet Mail Exchange) utilizados por las clases del espacio de nombres <xref:System.Net.Mail?displayProperty=fullName> .  
  
 <xref:System.Net.NetworkInformation?displayProperty=fullName>  
 Clases para recopilar información sobre eventos, cambios, estadísticas y propiedades de red mediante programación.  
  
 <xref:System.Net.PeerToPeer?displayProperty=fullName>  
 Proporciona una aplicación administrada del Protocolo de resolución de nombres de mismo nivel (PNRP) para desarrolladores.  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=fullName>  
 Proporciona una implementación administrada de la interfaz Peer-to-Peer Collaboration para desarrolladores.  
  
 <xref:System.Net.Security?displayProperty=fullName>  
 Clases para proporcionar secuencias de red para comunicaciones seguras entre hosts.  
  
 <xref:System.Net.Sockets?displayProperty=fullName>  
 Proporciona una implementación administrada de la interfaz de Windows Sockets (Winsock) para desarrolladores que necesitan controlar el acceso a la red.  
  
 <xref:System.Net.WebSockets?displayProperty=fullName>  
 Proporciona una implementación administrada de la interfaz de WebSocket para desarrolladores.  
  
 <xref:System.Uri?displayProperty=fullName>  
 Proporciona una representación de objeto de un identificador de recursos uniforme (URI) y un acceso sencillo a las partes del identificador URI.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=fullName>  
 Proporciona compatibilidad con la autenticación mediante la protección extendida de las aplicaciones.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=fullName>  
 Proporciona compatibilidad con la configuración de la autenticación mediante la protección extendida de las aplicaciones.  
  
## <a name="see-also"></a>Vea también  
 [Temas de procedimientos de programación de red](../../../docs/framework/network-programming/network-programming-how-to-topics.md)   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Ejemplos de red para .NET en la galería de código de MSDN](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)   
 [Ejemplo de HttpClient](http://go.microsoft.com/fwlink/?LinkId=242550)

