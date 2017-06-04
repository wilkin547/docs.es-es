---
title: "NAT Traversal mediante IPv6 y Teredo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# NAT Traversal mediante IPv6 y Teredo
Las mejoras se crearon que proporcionan compatibilidad para la exploración transversal de \(NAT\) de la traducción de direcciones de red.  Estos cambios están diseñados para su uso con IPv6 y Teredo, pero también son aplicables al otro IP de túnel tecnologías.  Estas mejoras afectan a clases de <xref:System.Net> y los espacios de nombres relacionados.  
  
 Estos cambios pueden afectar al cliente y las aplicaciones de servidor que tiene previsto utilizar IP de tunelización tecnologías.  
  
 Los cambios para admitir recorrido NACIONAL sólo están disponibles para las aplicaciones mediante .NET Framework versión 4 Beta 2.  Estas características no están disponibles en versiones anteriores de .NET Framework.  
  
## Información general  
 La versión 4 \(IPv4\) de protocolo de Internet definió una dirección IPv4 como 32 bits.  Como resultado, IPv4 admite aproximadamente 4 millones Direcciones IP únicos \(2^32\).  Como el número de equipos y dispositivos de red en internet expandieron en los años 90, los límites del espacio de direcciones IPv4 llegaron a ser evidentes.  
  
 Una de las técnicas utilizadas para extender la duración de IPv4 ha sido implementar NAT para permitir que una sola dirección IP pública única representa un gran número de Direcciones IP privado \(intranet privada\).  El Direcciones IP privado detrás de la acción del dispositivo NAT una sola dirección IPv4 pública.  El dispositivo NAT puede ser un dispositivo de hardware dedicado \(un punto de acceso inalámbrico y un enrutador baratos, por ejemplo\) o equipo que ejecuta un servicio para proporcionar NAT.  Un dispositivo o servicio para esta dirección IP pública traduce los paquetes de red IP entre internet pública y la intranet privada.  
  
 Este esquema funciona bien para las aplicaciones cliente que se ejecutan en la intranet privada que envían solicitudes a otro Direcciones IP \(normalmente servidores\) en internet.  El dispositivo NAT o el servidor puede mantener una asignación de las solicitudes de cliente cuándo una respuesta se devuelve le sabe dónde enviar la respuesta.  Pero este esquema plantea problemas para las aplicaciones que se ejecutan en la intranet privada detrás del dispositivo NAT que desean proporcionar servicios, escuche los paquetes, y responden.  Esto es particularmente el caso para aplicaciones punto a punto.  
  
 El protocolo IPv6 definió una dirección IPv4 como 128 bits.  Como resultado, IPv6 admite muy un espacio grande de la dirección IP de 3,2 direcciones únicas de x 10^38 \(2^128\).  Con un espacio de direcciones de este tamaño, es posible para cada dispositivo conectado a internet para asignar una dirección única.  Pero hay problemas.  Gran parte del mundo todavía se utiliza sólo IPv4.  En particular, muchos de los enrutadores existentes y los puntos de acceso inalámbrico utilizados por las empresas pequeñas, organizaciones, y los hogares no admiten IPv6.  También algunos proveedores de servicios Internet que sirven a estos clientes no admiten ni han configurado compatibilidad con IPv6.  
  
 Varias tecnologías de transición de IPv6 se han desarrollado para túnel las direcciones de IPv6 en un paquete IPv4.  Estas tecnologías incluyen 6to4, ISATAP, y los túneles de Teredo que proporcionan la asignación y el host\-a\- host de dirección tunelización automático para el tráfico IPv6 de la unidifusión a los hosts de IPv6 deben recorrer las redes IP4 para lograr otras redes de IPv6.  Los paquetes de IPv6 se envían tunelizados como paquetes IPv4.  Se usan varias técnicas de túnel que permiten el recorrido NACIONAL para las direcciones de IPv6 a través de un dispositivo NAT.  
  
 Teredo es una de las tecnologías de transición de IPv6 que aporta conectividad de IPv6 a redes IPv4.  Teredo se documenta en RFC 4380 publicado por el Grupo de trabajo de ingeniería de Internet \(IETF\).  Windows XP SP2 y versiones posteriores proporcionan compatibilidad para un adaptador virtual de Teredo que puede proporcionar una dirección IPv6 pública en el intervalo 2001:0::\/32.  Esta dirección IPv6 se puede utilizar para realizar escuchas para las conexiones entrantes de internet y puede proporcionarse a IPv6 habilitó a los clientes que desean para conectarse al servicio que escucha.  Esto libera una aplicación de preocuparse de cómo tratar un equipo detrás de un dispositivo NAT, porque la aplicación simplemente puede conectarse a ella con su dirección de IPv6 Teredo.  
  
## Mejoras para admitir NAT Traversal y Teredo  
 Las mejoras se agregan a <xref:System.Net>, a <xref:System.Net.NetworkInformation>, y los espacios de nombres de <xref:System.Net.Sockets> para admitir recorrido NACIONAL de IPv6 y Teredo.  
  
 Varios métodos se agregan a la clase de <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=fullName> para obtener la lista de unidifusión Direcciones IP en el host.  Comienza el método de <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> una solicitud asincrónica de recuperar la tabla estable de la dirección IP de la unidifusión en el equipo local.  El método de <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> finaliza una solicitud asincrónica pendiente de recuperar la tabla estable de la dirección IP de la unidifusión en el equipo local.  El método de <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> es una solicitud sincrónica de recuperar la tabla estable de la dirección IP de la unidifusión en el equipo local, espera hasta que la tabla address se estabilizar en caso necesario.  
  
 La propiedad de <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName> se puede utilizar para determinar si <xref:System.Net.IPAddress> es una dirección de IPv6 Teredo.  
  
 Mediante estos nuevos métodos de clase de <xref:System.Net.NetworkInformation.IPGlobalProperties> junto con la propiedad de <xref:System.Net.IPAddress.IsIPv6Teredo%2A> permite una aplicación con facilidad para buscar la dirección de Teredo.  Una aplicación necesita normalmente sólo conocer la dirección local de Teredo si está comunicando esta información a las aplicaciones remotas.  Por ejemplo, una aplicación entre iguales podría enviar a todas sus direcciones de IPv6 en un servidor del servicio de contacto con contrincantes que después puede reenviarlas a otras busca para habilitar la comunicación directa.  
  
 Una aplicación debe establecer habitualmente el servicio que escucha para escuchar en <xref:System.Net.IPAddress.IPv6Any?displayProperty=fullName> en lugar de en la dirección local de Teredo.  Tan si un cliente remoto o un par tiene una ruta directa de IPv6 el host del servicio que escucha, el cliente o el par puede conectar directamente de IPv6 y no tenían que utilizar Teredo para túnel paquetes.  
  
 Para las aplicaciones TCP, la clase de <xref:System.Net.Sockets.TcpListener?displayProperty=fullName> tiene un método de <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> para habilitar recorrido NACIONAL.  Para las aplicaciones de UDP, la clase de <xref:System.Net.Sockets.UdpClient?displayProperty=fullName> tiene un método de <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> para habilitar recorrido NACIONAL.  
  
 Para las aplicaciones que utilizan <xref:System.Net.Sockets.Socket?displayProperty=fullName> y las clases relacionadas, el <xref:System.Net.Sockets.Socket.GetSocketOption%2A> y los métodos de <xref:System.Net.Sockets.Socket.SetSocketOption%2A> se pueden utilizar con la opción de socket de <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName> de ver, habilitar, o deshabilitar recorrido NACIONAL.  
  
## Vea también  
 <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=fullName>   
 <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=fullName>