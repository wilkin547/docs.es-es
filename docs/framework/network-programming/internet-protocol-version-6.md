---
title: "Protocolo de Internet versi&#243;n 6 | Microsoft Docs"
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
helpviewer_keywords: 
  - "IPv6, mejoras"
  - "IPv4"
  - "IPv6"
  - "Protocolo de Internet versión 6, mejoras"
  - "Protocolo de Internet versión 6"
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Protocolo de Internet versi&#243;n 6
El protocolo de Internet versión 6 \(IPv6\) es un nuevo conjunto de los protocolos estándar del nivel de red de internet.  IPv6 está diseñado para solucionar muchos de los problemas de la versión actual del conjunto de protocolo de Internet \(conocida como IPv4\) con respecto al agotamiento de dirección, seguridad, configuración automática, extensibilidad, etc.  IPv6 amplía las capacidades de internet de habilitar nuevas clases de aplicaciones, incluidos entre iguales y aplicaciones móviles.  Los siguientes son los puntos principales de protocolo actual de IPv4:  
  
-   Agotamiento rápido del espacio de direcciones.  
  
     Esto ha conducido al uso de los traductores de direcciones de red \(NATs\) direcciones privadas varias de ese mapa a una sola dirección IP pública.  Las principales problemas creados por este mecanismo están procesando sobrecarga y falta de conectividad de un extremo a otro.  
  
-   Falta de compatibilidad de la jerarquía.  
  
     Debido a su organización predefinida inherente de la clase, IPv4 carece de compatibilidad jerárquico verdadero.  No se puede estructurar el Direcciones IP de manera que asigna true la topología de red.  Este defecto de diseño crucial crea la necesidad de tablas de enrutamiento grandes de entregar los paquetes IPv4 a cualquier ubicación en internet.  
  
-   Configuración de red compleja.  
  
     Con IPv4, direcciones deben asignarse estáticamente o con un protocolo de configuración como DHCP.  En una situación ideal, los hosts no tendrían que basarse en la administración de una infraestructura de DHCP.  En su lugar, pueden configurarse según el segmento de red en el que se encuentran.  
  
-   Falta de autenticación integrada y de confidencialidad.  
  
     IPv4 no requiere compatibilidad con ningún mecanismo que proporciona la autenticación o el cifrado de datos intercambiados.  Este cambios con IPv6.  Seguridad de protocolo Internet \(IPsec\) es un requisito de soporte de IPv6.  
  
 Un nuevo conjunto de protocolo debe satisfacer los requisitos básicos siguientes:  
  
-   Enrutamiento y direccionamiento de gran tamaño con sobrecarga baja.  
  
-   Configuración automática para las diferentes situaciones de conexión.  
  
-   Autenticación integrada y confidencialidad.  
  
 Para obtener más información, vea [Direccionamiento IPv6](../../../docs/framework/network-programming/ipv6-addressing.md), [Enrutamiento de IPv6](../../../docs/framework/network-programming/ipv6-routing.md), [Configuración automática de IPv6](../../../docs/framework/network-programming/ipv6-auto-configuration.md), [Habilitar y deshabilitar IPv6](../../../docs/framework/network-programming/enabling-and-disabling-ipv6.md) y [Cómo: modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## Referencias  
 Los siguientes son los documentos seleccionados de RFC que puede encontrar en el sitio de Grupo de trabajo de ingeniería de Internet \([http:\/\/www.ietf.org](http://www.ietf.org/)\):  
  
-   RFC 1287, Towards la arquitectura de internet de Future.  
  
-   RFC 1454, comparación de Proposals para la versión siguiente de IP.  
  
-   RFC 2373, la arquitectura de direccionamiento de la versión 6 de IP.  
  
-   RFC 2374, un formato de dirección de unidifusión global agregable de IPv6.  
  
 También puede encontrar información de IPv6\-related en [área de IPv6 en Technet](http://go.microsoft.com/fwlink/?LinkID=179658).  
  
## Vea también  
 [Ejemplo de sockets de IPv6](http://go.microsoft.com/fwlink/?LinkID=179568)   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Sockets](../../../docs/framework/network-programming/sockets.md)