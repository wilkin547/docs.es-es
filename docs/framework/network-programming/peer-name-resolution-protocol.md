---
title: Protocolo de resolución de nombres del mismo nivel
description: Obtenga información sobre el Protocolo de resolución de nombres de mismo nivel (PNRP), un protocolo de registro y resolución de nombres seguro, escalable y dinámico.
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: 9ab46566b3c0d6ceff694eca266bdb6e10441374
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98191240"
---
# <a name="peer-name-resolution-protocol"></a>Protocolo de resolución de nombres del mismo nivel

En entornos punto a punto, los elementos del mismo nivel usan sistemas de resolución de nombres específicos para resolver sus respectivas ubicaciones de red (direcciones, protocolos y puertos) a partir de nombres u otros tipos de identificadores. Antes, la resolución de nombres del mismo nivel resultaba complicada por la conectividad intrínsecamente transitoria y por otras limitaciones del Sistema de nombres de dominio (DNS).  
  
 La plataforma de red punto a punto de Microsoft® Windows® soluciona este problema con el Protocolo de resolución de nombres de mismo nivel (PNRP), que es un registro de nombres seguro, escalable y dinámico. Este protocolo de resolución de nombres se desarrolló inicialmente para Windows XP y posteriormente se actualizó en Windows Vista™. El funcionamiento de PNRP es muy diferente del de los sistemas de resolución de nombres tradicionales y ofrece nuevas posibilidades muy interesantes para los desarrolladores de aplicaciones.  
  
 Con PNRP, se pueden aplicar nombres del mismo nivel al equipo, o a las aplicaciones o servicios individuales del equipo. Una resolución de nombres del mismo nivel incluye una dirección, el puerto y, posiblemente, una carga extendida. Entre las ventajas de este sistema se incluyen la tolerancia a errores, la ausencia de cuellos de botella y las resoluciones de nombres que nunca devuelven direcciones obsoletas, lo que convierte al protocolo en una solución excelente para la localización de usuarios móviles.  
  
 En cuanto a la seguridad, los nombres del mismo nivel pueden publicarse como seguros (protegidos) o no seguros (sin protección). PNRP usa criptografía de clave pública para proteger los nombres del mismo nivel seguros contra la suplantación de identidad; los nombres de ambos equipos y servicios pueden asignarse con PNRP.  
  
El Protocolo de resolución de nombres de mismo nivel tiene las propiedades siguientes:  
  
- Es un protocolo distribuido prácticamente sin servidor. Solo se requieren servidores para el proceso de arranque.  
  
- La publicación de nombres es segura y en ella no intervienen terceros. A diferencia de la publicación de nombres DNS, la publicación de nombres PNRP es instantánea y no tiene costo económico.  
  
- PNRP se actualiza en tiempo real, lo que impide la resolución de direcciones obsoletas.  
  
- La resolución de nombres a través de PNRP va más allá de los equipos, ya que también permite la resolución de nombres para servicios.  
  
## <a name="the-systemnetpeertopeer-namespace"></a>El espacio de nombres System.Net.PeerToPeer  
  
- La funcionalidad PNRP está definida por el espacio de nombres <xref:System.Net.PeerToPeer> en .NET Framework versión 3.5. Proporciona un conjunto de tipos que se pueden usar para registrar y resolver nombres del mismo nivel con un servicio PNRP disponible.  
  
- (Se pueden crear resoluciones del mismo nivel personalizadas y PNRP y crear instancias de ellas mediante los tipos proporcionados en el espacio de nombres <xref:System.ServiceModel.PeerResolvers>).  
  
- Los tipos básicos que se usan para registrar y resolver los nombres con un servicio PNRP disponible son los siguientes:  
  
- <xref:System.Net.PeerToPeer.Cloud>: define la información que describe una nube PNRP disponible, incluido su ámbito.  
  
- <xref:System.Net.PeerToPeer.PeerName>: define un nombre del mismo nivel que se puede usar para registrar y resolver posteriormente un elemento del mismo nivel dentro de una nube.  
  
- <xref:System.Net.PeerToPeer.PeerNameRecord>: define el registro de la nube PNRP que contiene la información de registro de un elemento del mismo nivel, que incluye los puntos de conexión de red en los que se puede establecer contacto con dicho elemento.  
  
- <xref:System.Net.PeerToPeer.PeerNameRegistration>: define el proceso de registro para un nombre del mismo nivel, incluidos los métodos para iniciar y detener el registro de nombres del mismo nivel.  
  
- <xref:System.Net.PeerToPeer.PeerNameResolver>: define el proceso para resolver un nombre del mismo nivel en sus puntos de conexión de red, incluidos los métodos sincrónicos y asincrónicos para la resolución.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [Network Programming Samples (Ejemplos de programación de red)](network-programming-samples.md)
