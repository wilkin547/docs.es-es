---
title: Protocolo de resolución de nombres del mismo nivel
description: Obtenga información sobre el Protocolo de resolución de nombres de mismo nivel (PNRP), un protocolo de registro y resolución de nombres seguro, escalable y dinámico.
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
ms.openlocfilehash: 72eb63c2c90f398c515d77cd2b2d693237e533a5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502228"
---
# <a name="peer-name-resolution-protocol"></a><span data-ttu-id="315d2-103">Protocolo de resolución de nombres del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="315d2-103">Peer Name Resolution Protocol</span></span>
<span data-ttu-id="315d2-104">En entornos punto a punto, los elementos del mismo nivel usan sistemas de resolución de nombres específicos para resolver sus respectivas ubicaciones de red (direcciones, protocolos y puertos) a partir de nombres u otros tipos de identificadores.</span><span class="sxs-lookup"><span data-stu-id="315d2-104">In peer-to-peer environments, peers use specific name resolution systems to resolve each other's network locations (addresses, protocols, and ports) from names or other types of identifiers.</span></span> <span data-ttu-id="315d2-105">Antes, la resolución de nombres del mismo nivel resultaba complicada por la conectividad intrínsecamente transitoria y por otras limitaciones del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="315d2-105">In the past, peer name resolution has been complicated by the inherently transient connectivity as well as other shortcomings within the Domain Name System (DNS).</span></span>  
  
 <span data-ttu-id="315d2-106">La plataforma de red punto a punto de Microsoft® Windows® soluciona este problema con el Protocolo de resolución de nombres de mismo nivel (PNRP), que es un registro de nombres seguro, escalable y dinámico. Este protocolo de resolución de nombres se desarrolló inicialmente para Windows XP y posteriormente se actualizó en Windows Vista™.</span><span class="sxs-lookup"><span data-stu-id="315d2-106">The Microsoft® Windows® Peer-to-Peer Networking platform solves this problem with the Peer Name Resolution Protocol (PNRP), a secure, scalable, and dynamic name registration and name resolution protocol first developed for Windows XP and then upgraded in Windows Vista™.</span></span> <span data-ttu-id="315d2-107">El funcionamiento de PNRP es muy diferente del de los sistemas de resolución de nombres tradicionales y ofrece nuevas posibilidades muy interesantes para los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="315d2-107">PNRP works very differently from traditional name resolution systems, opening up exciting new possibilities for application developers.</span></span>  
  
 <span data-ttu-id="315d2-108">Con PNRP, se pueden aplicar nombres del mismo nivel al equipo, o a las aplicaciones o servicios individuales del equipo.</span><span class="sxs-lookup"><span data-stu-id="315d2-108">With PNRP, peer names can be applied to the machine, or individual applications or services on the machine.</span></span> <span data-ttu-id="315d2-109">Una resolución de nombres del mismo nivel incluye una dirección, el puerto y, posiblemente, una carga extendida.</span><span class="sxs-lookup"><span data-stu-id="315d2-109">A peer name resolution includes an address, port, and possibly an extended payload.</span></span> <span data-ttu-id="315d2-110">Entre las ventajas de este sistema se incluyen la tolerancia a errores, la ausencia de cuellos de botella y las resoluciones de nombres que nunca devuelven direcciones obsoletas, lo que convierte al protocolo en una solución excelente para la localización de usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="315d2-110">Benefits of this system include fault tolerance, no bottlenecks, and name resolutions that will never return stale addresses; making the protocol an excellent solution for locating mobile users.</span></span>  
  
 <span data-ttu-id="315d2-111">En cuanto a la seguridad, los nombres del mismo nivel pueden publicarse como seguros (protegidos) o no seguros (sin protección).</span><span class="sxs-lookup"><span data-stu-id="315d2-111">In terms of security, peer names can be published as secured (protected) or unsecured (unprotected).</span></span> <span data-ttu-id="315d2-112">PNRP usa criptografía de clave pública para proteger los nombres del mismo nivel seguros contra la suplantación de identidad; los nombres de ambos equipos y servicios pueden asignarse con PNRP.</span><span class="sxs-lookup"><span data-stu-id="315d2-112">PNRP uses public key cryptography to protect secure peer names against spoofing; both computers and services can be named with PNRP.</span></span>  
  
<span data-ttu-id="315d2-113">El Protocolo de resolución de nombres de mismo nivel tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="315d2-113">The Peer Name Resolution Protocol demonstrates the following properties:</span></span>  
  
- <span data-ttu-id="315d2-114">Es un protocolo distribuido prácticamente sin servidor.</span><span class="sxs-lookup"><span data-stu-id="315d2-114">Distributed and almost entirely serverless.</span></span> <span data-ttu-id="315d2-115">Solo se requieren servidores para el proceso de arranque.</span><span class="sxs-lookup"><span data-stu-id="315d2-115">Servers are only required for the bootstrapping process.</span></span>  
  
- <span data-ttu-id="315d2-116">La publicación de nombres es segura y en ella no intervienen terceros.</span><span class="sxs-lookup"><span data-stu-id="315d2-116">Secure name publication without the involvement of third parties.</span></span> <span data-ttu-id="315d2-117">A diferencia de la publicación de nombres DNS, la publicación de nombres PNRP es instantánea y no tiene costo económico.</span><span class="sxs-lookup"><span data-stu-id="315d2-117">Unlike DNS name publication, PNRP name publication is instantaneous and without financial cost.</span></span>  
  
- <span data-ttu-id="315d2-118">PNRP se actualiza en tiempo real, lo que impide la resolución de direcciones obsoletas.</span><span class="sxs-lookup"><span data-stu-id="315d2-118">PNRP updates in real-time, which prevents the resolution of stale addresses.</span></span>  
  
- <span data-ttu-id="315d2-119">La resolución de nombres a través de PNRP va más allá de los equipos, ya que también permite la resolución de nombres para servicios.</span><span class="sxs-lookup"><span data-stu-id="315d2-119">The resolution of names via PNRP extends beyond computers by also allowing name resolution for services.</span></span>  
  
## <a name="the-systemnetpeertopeer-namespace"></a><span data-ttu-id="315d2-120">El espacio de nombres System.Net.PeerToPeer</span><span class="sxs-lookup"><span data-stu-id="315d2-120">The System.Net.PeerToPeer namespace</span></span>  
  
- <span data-ttu-id="315d2-121">La funcionalidad PNRP está definida por el espacio de nombres <xref:System.Net.PeerToPeer> en .NET Framework versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="315d2-121">PNRP functionality is defined by the <xref:System.Net.PeerToPeer> namespace within the .NET Framework version 3.5.</span></span> <span data-ttu-id="315d2-122">Proporciona un conjunto de tipos que se pueden usar para registrar y resolver nombres del mismo nivel con un servicio PNRP disponible.</span><span class="sxs-lookup"><span data-stu-id="315d2-122">It provides a set of types that can be used to register and resolve peer names with an available PNRP service.</span></span>  
  
- <span data-ttu-id="315d2-123">(Se pueden crear resoluciones del mismo nivel personalizadas y PNRP y crear instancias de ellas mediante los tipos proporcionados en el espacio de nombres <xref:System.ServiceModel.PeerResolvers>).</span><span class="sxs-lookup"><span data-stu-id="315d2-123">(PNRP and custom peer resolvers can be created and instantiated using the types provided in the <xref:System.ServiceModel.PeerResolvers> namespace.)</span></span>  
  
- <span data-ttu-id="315d2-124">Los tipos básicos que se usan para registrar y resolver los nombres con un servicio PNRP disponible son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="315d2-124">The basic types used to register and resolve names with an available PNRP service are as follows:</span></span>  
  
- <span data-ttu-id="315d2-125"><xref:System.Net.PeerToPeer.Cloud>: define la información que describe una nube PNRP disponible, incluido su ámbito.</span><span class="sxs-lookup"><span data-stu-id="315d2-125"><xref:System.Net.PeerToPeer.Cloud>: Defines the information describing an available PNRP cloud, including its scope.</span></span>  
  
- <span data-ttu-id="315d2-126"><xref:System.Net.PeerToPeer.PeerName>: define un nombre del mismo nivel que se puede usar para registrar y resolver posteriormente un elemento del mismo nivel dentro de una nube.</span><span class="sxs-lookup"><span data-stu-id="315d2-126"><xref:System.Net.PeerToPeer.PeerName>: Defines a peer name that can be used to register and subsequently resolve a peer within a cloud.</span></span>  
  
- <span data-ttu-id="315d2-127"><xref:System.Net.PeerToPeer.PeerNameRecord>: define el registro de la nube PNRP que contiene la información de registro de un elemento del mismo nivel, que incluye los puntos de conexión de red en los que se puede establecer contacto con dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="315d2-127"><xref:System.Net.PeerToPeer.PeerNameRecord>: Defines the record in PNRP cloud that contains the registration information for a peer, which includes the network endpoints at which the peer can be contacted.</span></span>  
  
- <span data-ttu-id="315d2-128"><xref:System.Net.PeerToPeer.PeerNameRegistration>: define el proceso de registro para un nombre del mismo nivel, incluidos los métodos para iniciar y detener el registro de nombres del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="315d2-128"><xref:System.Net.PeerToPeer.PeerNameRegistration>: Defines the registration process for a peer name, including methods to start and stop peer name registration.</span></span>  
  
- <span data-ttu-id="315d2-129"><xref:System.Net.PeerToPeer.PeerNameResolver>: define el proceso para resolver un nombre del mismo nivel en sus puntos de conexión de red, incluidos los métodos sincrónicos y asincrónicos para la resolución.</span><span class="sxs-lookup"><span data-stu-id="315d2-129"><xref:System.Net.PeerToPeer.PeerNameResolver>: Defines the process for resolving a peer name to its network endpoint(s), including both synchronous and asynchronous methods for resolution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315d2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="315d2-130">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers>
- <xref:System.Net.PeerToPeer>
- [<span data-ttu-id="315d2-131">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="315d2-131">Network Programming Samples</span></span>](network-programming-samples.md)

<!-- to-do: review sample links
- [PeerToPeer Technology Sample](https://go.microsoft.com/fwlink/?LinkID=179571)
-->
