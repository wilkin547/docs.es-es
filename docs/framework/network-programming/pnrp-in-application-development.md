---
title: PNRP en el desarrollo de aplicaciones
ms.date: 03/30/2017
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b085604d7d20eb9222507b4820be219ffeae4726
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395741"
---
# <a name="pnrp-in-application-development"></a><span data-ttu-id="ea6ce-102">PNRP en el desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ea6ce-102">PNRP in Application Development</span></span>
<span data-ttu-id="ea6ce-103">En Windows Vista, las aplicaciones de red pueden tener acceso a la publicación de nombres y funciones de resolución a través de una interfaz de programación de aplicaciones (API) de PNRP simplificada.</span><span class="sxs-lookup"><span data-stu-id="ea6ce-103">In Windows Vista, networking applications can access name publication and resolution functions through a simplified PNRP application programming interface (API).</span></span>  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a><span data-ttu-id="ea6ce-104">Implementar el Protocolo de resolución de nombres de mismo nivel</span><span class="sxs-lookup"><span data-stu-id="ea6ce-104">Implementing the Peer Name Resolution Protocol</span></span>  
 <span data-ttu-id="ea6ce-105">Con la API de PNRP simplificada, las nubes no se especifican explícitamente para registrar el nombre y las direcciones, ya que el componente PNRP determina automáticamente las nubes adecuadas a las que unirse y las direcciones que se van a publicar en las nubes.</span><span class="sxs-lookup"><span data-stu-id="ea6ce-105">With the simplified PNRP API, clouds are not explicitly specified to register the name and addresses; the PNRP component automatically determines the appropriate clouds to join and the addresses to publish within the clouds.</span></span>  
  
 <span data-ttu-id="ea6ce-106">Para una resolución de nombres de PNRP altamente simplificada en Windows Vista, los nombres PNRP ahora se encuentran integrados en la función getaddrinfo() de Windows Sockets.</span><span class="sxs-lookup"><span data-stu-id="ea6ce-106">For highly simplified PNRP name resolution in Windows Vista, PNRP names are now integrated into the getaddrinfo() Windows Sockets function.</span></span> <span data-ttu-id="ea6ce-107">Para usar PNRP con el fin de resolver un nombre para una dirección de IPv6, las aplicaciones pueden usar la función getaddrinfo() para resolver el nombre de dominio completo (FQDN) name.prnp.net, donde "name" es el nombre de mismo nivel que se resuelve.</span><span class="sxs-lookup"><span data-stu-id="ea6ce-107">To use PNRP to resolve a name to an IPv6 address, applications can use the getaddrinfo() function to resolve the Fully Qualified Domain Name (FQDN) name.prnp.net, in which name is peer name being resolved.</span></span> <span data-ttu-id="ea6ce-108">El dominio pnrp.net es un dominio reservado en Windows Vista para la resolución de nombres de PNRP.</span><span class="sxs-lookup"><span data-stu-id="ea6ce-108">The pnrp.net domain is a reserved domain in Windows Vista for PNRP name resolution.</span></span>  
  
 <span data-ttu-id="ea6ce-109">La transmisión de mensajes entre aplicaciones punto a punto todavía se controla mediante arquitecturas subyacentes, como [datos de gran tamaño y secuencias](http://go.microsoft.com/fwlink/?LinkID=179652) de PeerChannel y WCF.</span><span class="sxs-lookup"><span data-stu-id="ea6ce-109">Message passing between PeerToPeer applications is still handled by underlying architectures such as PeerChannel and WCF [Large Data and Streaming](http://go.microsoft.com/fwlink/?LinkID=179652).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea6ce-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea6ce-110">See Also</span></span>  
 <xref:System.Net.PeerToPeer>
