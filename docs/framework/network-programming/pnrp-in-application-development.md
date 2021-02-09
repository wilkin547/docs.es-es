---
description: 'Más información acerca de: PNRP en el desarrollo de aplicaciones'
title: PNRP en el desarrollo de aplicaciones
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
ms.openlocfilehash: d3e6e9a329f292d3cde7fb906b28452a4e67fb1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794889"
---
# <a name="pnrp-in-application-development"></a>PNRP en el desarrollo de aplicaciones

En Windows Vista, las aplicaciones de red pueden tener acceso a la publicación de nombres y funciones de resolución a través de una interfaz de programación de aplicaciones (API) de PNRP simplificada.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Implementar el Protocolo de resolución de nombres de mismo nivel  

 Con la API de PNRP simplificada, las nubes no se especifican explícitamente para registrar el nombre y las direcciones, ya que el componente PNRP determina automáticamente las nubes adecuadas a las que unirse y las direcciones que se van a publicar en las nubes.  
  
 Para una resolución de nombres de PNRP altamente simplificada en Windows Vista, los nombres PNRP ahora se encuentran integrados en la función getaddrinfo() de Windows Sockets. Para usar PNRP con el fin de resolver un nombre para una dirección de IPv6, las aplicaciones pueden usar la función getaddrinfo() para resolver el nombre de dominio completo (FQDN) name.prnp.net, donde "name" es el nombre de mismo nivel que se resuelve. El dominio pnrp.net es un dominio reservado en Windows Vista para la resolución de nombres de PNRP.  
  
 La transmisión de mensajes entre aplicaciones punto a punto todavía se controla mediante arquitecturas subyacentes, como [datos de gran tamaño y secuencias](../wcf/feature-details/large-data-and-streaming.md) de PeerChannel y WCF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.PeerToPeer>
