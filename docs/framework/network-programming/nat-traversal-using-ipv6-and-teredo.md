---
title: NAT Traversal mediante IPv6 y Teredo
ms.date: 03/30/2017
ms.assetid: 568cd245-3300-49ef-a995-d81bf845d961
ms.openlocfilehash: f617dc8912091576727b90da1e9efb9ebd5f9bda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642183"
---
# <a name="nat-traversal-using-ipv6-and-teredo"></a>NAT Traversal mediante IPv6 y Teredo
Se han realizado mejoras que proporcionan compatibilidad con la traducción de direcciones de red (NAT) transversal. Estos cambios están diseñados para su uso con IPv6 y Teredo, pero también son aplicables a otras tecnologías de túnel IP. Estas mejoras afectan a las clases del espacio de nombres <xref:System.Net> y de otros espacios de nombres relacionados.  
  
 Estos cambios pueden afectar a las aplicaciones cliente y servidor que tienen previsto usar tecnologías de túnel IP.  
  
 Los cambios para admitir NAT transversal{1}{2}solo están disponibles para las aplicaciones que usan .NET Framework versión 4. Estas características no están disponibles en versiones anteriores de .NET Framework.  
  
## <a name="overview"></a>Información general  
 El protocolo de Internet versión 4 (IPv4) definía una dirección IPv4 con una longitud de 32 bits. Como resultado, IPv4 admite aproximadamente 4 mil millones de direcciones IP únicas (2^32). Con el aumento del número de equipos y dispositivos de red en Internet en la década de 1990, los límites del espacio de direcciones IPv4 se hacían cada vez más evidentes.  
  
 Una de las diversas técnicas usadas para ampliar la vigencia de IPv4 consistía en implementar NAT de modo que permitiese que una sola dirección IP pública representase un gran número de direcciones IP privadas (intranet privada). Las direcciones IP privadas tras el dispositivo NAT comparten la única dirección IPv4 pública. El dispositivo NAT puede ser un dispositivo de hardware dedicado (un económico punto de acceso inalámbrico y enrutador, por ejemplo) o un equipo que ejecuta un servicio para proporcionar NAT. Un dispositivo o servicio para esta dirección IP pública traduce los paquetes de red IP entre la red de Internet pública y la intranet privada.  
  
 Este esquema es apropiado para las aplicaciones cliente que se ejecutan en la intranet privada y que envían solicitudes a otras direcciones IP (normalmente servidores) en Internet. El dispositivo o servidor NAT puede mantener una asignación de las solicitudes de los clientes, de modo que cuando se devuelve una respuesta sabe adónde enviarla. Pero este esquema plantea problemas a las aplicaciones que se ejecutan en la intranet privada tras el dispositivo NAT que va a proporcionar servicios, realizar escuchas de paquetes y responder. Esto sucede sobre todo en las aplicaciones punto a punto.  
  
 El protocolo IPv6 definía una dirección IPv4 con una longitud de 128 bits. Como resultado, IPv6 admite un gran espacio de direcciones IP de 3,2 x 10^38 direcciones únicas (2^128). Con un espacio de direcciones de este tamaño, es posible que todos los dispositivos conectados a Internet obtengan una dirección única. A pesar de ello, existe una serie de problemas. En gran parte del mundo se sigue usando solo IPv4. En concreto, muchos de los enrutadores y puntos de acceso inalámbrico usados por los hogares, las organizaciones y las pequeñas empresas no admiten IPv6. Además, algunos de los proveedores de servicios de Internet que atienden a estos clientes no admiten IPv6 o no han configurado la compatibilidad con IPv6.  
  
 Se han desarrollado varias tecnologías de transición de IPv6 para tunelizar las direcciones IPv6 en un paquete IPv4. Estas tecnologías incluyen 6to4, ISATAP y túneles Teredo, que proporcionan la asignación de direcciones y la tunelización automática de host a host para el tráfico IPv6 de unidifusión cuando los hosts IPv6 deben atravesar redes IP4 para llegar a otras redes IPv6. Los paquetes IPv6 se envían mediante túneles como paquetes IPv4. Se están usando varias técnicas de tunelización que permiten NAT transversal{1}{2}para direcciones IPv6 a través de un dispositivo NAT.  
  
 Teredo es una de las tecnologías de transición IPv6 que ofrece conectividad IPv6 en redes IPv4. Las especificaciones de Teredo están documentadas en RFC 4380, publicado por Internet Engineering Task Force (IETF). Windows XP SP2 y versiones posteriores proporcionan compatibilidad con un adaptador Teredo virtual que puede proporcionar una dirección IPv6 pública en el intervalo 2001:0::/32. Esta dirección IPv6 puede usarse para escuchar las conexiones entrantes procedentes de Internet y puede proporcionarse a los clientes habilitados para IPv6 que quieren conectar con el servicio de escucha. Esto hace que una aplicación no tenga que preocuparse por cómo dirigirse a un equipo tras un dispositivo NAT, dado que la aplicación solo se puede conectar a él mediante su dirección Teredo IPv6.  
  
## <a name="enhancements-to-support-nat-traversal-and-teredo"></a>Mejoras para admitir NAT transversal{1}{2}y Teredo  
 Se han agregado mejoras a los espacios de nombres <xref:System.Net>, <xref:System.Net.NetworkInformation> y <xref:System.Net.Sockets> para admitir NAT transversal{4}{5}mediante IPv6 y Teredo.  
  
 Se han agregado varios métodos a la clase <xref:System.Net.NetworkInformation.IPGlobalProperties?displayProperty=nameWithType> para obtener la lista de direcciones IP de unidifusión en el host. El método <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A> inicia una solicitud asincrónica para recuperar la tabla de direcciones IP de unidifusión estables del equipo local. El método <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A> finaliza una solicitud asincrónica pendiente para recuperar la tabla de direcciones IP de unidifusión estables del equipo local. El método <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A> es una solicitud sincrónica para recuperar la tabla de direcciones IP de unidifusión estables del equipo local, que espera hasta que la tabla de direcciones se estabilice, si es necesario.  
  
 Se puede usar la propiedad <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType> para determinar si una <xref:System.Net.IPAddress> es una dirección Teredo IPv6.  
  
 El uso de estos nuevos métodos de clase <xref:System.Net.NetworkInformation.IPGlobalProperties> en combinación con la propiedad <xref:System.Net.IPAddress.IsIPv6Teredo%2A> permite que una aplicación encuentre fácilmente la dirección Teredo. Normalmente, una aplicación solo necesita conocer la dirección Teredo local si está comunicando esta información a aplicaciones remotas. Por ejemplo, una aplicación punto a punto puede enviar todas sus direcciones IPv6 a un servidor de contactos que, posteriormente, puede reenviarlas a otros servidores para habilitar la comunicación directa.  
  
 Por lo general, una aplicación debe establecer su servicio de escucha para que escuche en <xref:System.Net.IPAddress.IPv6Any?displayProperty=nameWithType>, en lugar de en la dirección Teredo local. Así pues, si un elemento del mismo nivel o cliente remoto tiene una ruta IPv6 directa al host del servicio de escucha, puede conectarse directamente mediante IPv6 sin tener que usar Teredo para tunelizar paquetes.  
  
 Para las aplicaciones TCP, la clase <xref:System.Net.Sockets.TcpListener?displayProperty=nameWithType> tiene un método <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A> para permitir NAT transversal. Para las aplicaciones UDP, la clase <xref:System.Net.Sockets.UdpClient?displayProperty=nameWithType> tiene un método <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A> para permitir NAT transversal.  
  
 Para las aplicaciones que usan <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> y clases relacionadas, se pueden usar los métodos <xref:System.Net.Sockets.Socket.GetSocketOption%2A> y <xref:System.Net.Sockets.Socket.SetSocketOption%2A> con la opción de socket <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType> para consultar, habilitar o deshabilitar NAT transversal.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.IPAddress.IsIPv6Teredo%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.BeginGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.EndGetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.NetworkInformation.IPGlobalProperties.GetUnicastAddresses%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.SetIPProtectionLevel%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.TcpListener.AllowNatTraversal%2A?displayProperty=nameWithType>
- <xref:System.Net.Sockets.UdpClient.AllowNatTraversal%2A?displayProperty=nameWithType>
