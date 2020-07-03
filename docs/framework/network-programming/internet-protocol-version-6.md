---
title: Protocolo de Internet versión 6
description: Obtenga información sobre el protocolo IPv6 y sus diferencias con IPv4. Las aplicaciones .NET Framework admiten IPv6, pero es posible que haya que configurarlas.
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: dd8b0b26e449fba7479d2678aff25ed49e721a90
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502397"
---
# <a name="internet-protocol-version-6"></a>Protocolo de Internet versión 6
El protocolo de Internet versión 6 (IPv6) es un nuevo conjunto de protocolos estándar para la capa de red de Internet. IPv6 está diseñado para resolver muchos de los problemas que se producen en la versión actual del conjunto de protocolo de Internet (conocido como IPv4) en relación con el agotamiento de direcciones, la seguridad, la configuración automática, la extensibilidad, etc. IPv6 amplía las funciones de Internet para habilitar nuevos tipos de aplicaciones, incluidas las aplicaciones móviles y de punto a punto. A continuación se indican los principales problemas del protocolo IPv4 actual:  
  
- Rápido agotamiento del espacio de direcciones.  
  
     Esto ha llevado al uso de traductores de direcciones de red (NAT) que asignan varias direcciones privadas a una sola dirección IP pública. Los principales problemas causados por este mecanismo son la sobrecarga de procesamiento y la falta de conectividad de extremo a extremo.  
  
- Falta de compatibilidad jerárquica.  
  
     Debido a su organización inherente de clases predefinidas, IPv4 carece de verdadera compatibilidad jerárquica. Es imposible estructurar las direcciones IP de forma que se asigne realmente la topología de red. Este error de diseño fundamental crea la necesidad de grandes tablas de enrutamiento para entregar paquetes de IPv4 en cualquier ubicación en Internet.  
  
- Configuración de red compleja.  
  
     Con IPv4, las direcciones deben asignarse de forma estática o mediante un protocolo de configuración como DHCP. En una situación ideal, los hosts no deberían tener que confiar en la administración de una infraestructura DHCP. En su lugar, deberían poder realizar la configuración por sí mismos en función del segmento de red en el que se encuentran.  
  
- Falta de autenticación y confidencialidad integradas.  
  
     IPv4 no requiere compatibilidad con ningún mecanismo que proporcione la autenticación o el cifrado de los datos intercambiados. Esto cambia con IPv6. El protocolo de seguridad de Internet (IPSec) es un requisito de compatibilidad con IPv6.  
  
 Un nuevo conjunto de protocolos debe cumplir los siguientes requisitos básicos:  
  
- Enrutamiento a gran escala y direccionamiento con poca sobrecarga.  
  
- Configuración automática para varias situaciones de conexión.  
  
- Autenticación y confidencialidad integradas.  
  
 Para más información, vea [Direccionamiento IPv6](ipv6-addressing.md), [Enrutamiento de IPv6](ipv6-routing.md), [Configuración automática de IPv6](ipv6-auto-configuration.md), [Habilitar y deshabilitar IPv6](enabling-and-disabling-ipv6.md) y [Cómo: Modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).  
  
## <a name="references"></a>Referencias  
 Aquí hay una selección de documentos RFC que se pueden encontrar en el sitio web de [Internet Engineering Task Force (IETF)](https://www.ietf.org/):  
  
- RFC 1287, Towards the Future Internet Architecture (Hacia la arquitectura de Internet del futuro).  
  
- RFC 1454, Comparison of Proposals for Next Version of IP (Comparación de propuestas para una próxima versión de IP).  
  
- RFC 2373, IP Version 6 Addressing Architecture (Arquitectura de direccionamiento de IP versión 6).  
  
- RFC 2374, An IPv6 Aggregatable Global Unicast Address Format (Formato de dirección de unidifusión global agregable de IPv6).  
  
 También encontrará información relacionada con IPv6 en [IP versión 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de sockets IPv6](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms180981%28v=vs.85%29)
- [Network Programming Samples (Ejemplos de programación de red)](network-programming-samples.md)
- [Sockets](sockets.md)
