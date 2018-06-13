---
title: Protocolo de resolución de nombres del mismo nivel
ms.date: 03/30/2017
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 01e0bd36b35319c90fc46d8f5f97161147852c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397005"
---
# <a name="peer-name-resolution-protocol"></a><span data-ttu-id="fcffe-102">Protocolo de resolución de nombres del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="fcffe-102">Peer Name Resolution Protocol</span></span>
<span data-ttu-id="fcffe-103">En entornos punto a punto, los elementos del mismo nivel usan sistemas de resolución de nombres específicos para resolver sus respectivas ubicaciones de red (direcciones, protocolos y puertos) a partir de nombres u otros tipos de identificadores.</span><span class="sxs-lookup"><span data-stu-id="fcffe-103">In peer-to-peer environments, peers use specific name resolution systems to resolve each other's network locations (addresses, protocols, and ports) from names or other types of identifiers.</span></span> <span data-ttu-id="fcffe-104">Antes, la resolución de nombres del mismo nivel resultaba complicada por la conectividad intrínsecamente transitoria y por otras limitaciones del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="fcffe-104">In the past, peer name resolution has been complicated by the inherently transient connectivity as well as other shortcomings within the Domain Name System (DNS).</span></span>  
  
 <span data-ttu-id="fcffe-105">La plataforma de red punto a punto de Microsoft® Windows® soluciona este problema con el Protocolo de resolución de nombres de mismo nivel (PNRP), que es un registro de nombres seguro, escalable y dinámico. Este protocolo de resolución de nombres se desarrolló inicialmente para Windows XP y posteriormente se actualizó en Windows Vista™.</span><span class="sxs-lookup"><span data-stu-id="fcffe-105">The Microsoft® Windows® Peer-to-Peer Networking platform solves this problem with the Peer Name Resolution Protocol (PNRP), a secure, scalable, and dynamic name registration and name resolution protocol first developed for Windows XP and then upgraded in Windows Vista™.</span></span> <span data-ttu-id="fcffe-106">El funcionamiento de PNRP es muy diferente del de los sistemas de resolución de nombres tradicionales y ofrece nuevas posibilidades muy interesantes para los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="fcffe-106">PNRP works very differently from traditional name resolution systems, opening up exciting new possibilities for application developers.</span></span>  
  
 <span data-ttu-id="fcffe-107">Con PNRP, se pueden aplicar nombres del mismo nivel al equipo, o a las aplicaciones o servicios individuales del equipo.</span><span class="sxs-lookup"><span data-stu-id="fcffe-107">With PNRP, peer names can be applied to the machine, or individual applications or services on the machine.</span></span> <span data-ttu-id="fcffe-108">Una resolución de nombres del mismo nivel incluye una dirección, el puerto y, posiblemente, una carga extendida.</span><span class="sxs-lookup"><span data-stu-id="fcffe-108">A peer name resolution includes an address, port, and possibly an extended payload.</span></span> <span data-ttu-id="fcffe-109">Entre las ventajas de este sistema se incluyen la tolerancia a errores, la ausencia de cuellos de botella y las resoluciones de nombres que nunca devuelven direcciones obsoletas, lo que convierte al protocolo en una solución excelente para la localización de usuarios móviles.</span><span class="sxs-lookup"><span data-stu-id="fcffe-109">Benefits of this system include fault tolerance, no bottlenecks, and name resolutions that will never return stale addresses; making the protocol an excellent solution for locating mobile users.</span></span>  
  
 <span data-ttu-id="fcffe-110">En cuanto a la seguridad, los nombres del mismo nivel pueden publicarse como seguros (protegidos) o no seguros (sin protección).</span><span class="sxs-lookup"><span data-stu-id="fcffe-110">In terms of security, peer names can be published as secured (protected) or unsecured (unprotected).</span></span> <span data-ttu-id="fcffe-111">PNRP usa criptografía de clave pública para proteger los nombres del mismo nivel seguros contra la suplantación de identidad; los nombres de ambos equipos y servicios pueden asignarse con PNRP.</span><span class="sxs-lookup"><span data-stu-id="fcffe-111">PNRP uses public key cryptography to protect secure peer names against spoofing; both computers and services can be named with PNRP.</span></span>  
  
-   <span data-ttu-id="fcffe-112">El Protocolo de resolución de nombres de mismo nivel tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fcffe-112">The Peer Name Resolution Protocol demonstrates the following properties:</span></span>  
  
-   <span data-ttu-id="fcffe-113">Es un protocolo distribuido prácticamente sin servidor.</span><span class="sxs-lookup"><span data-stu-id="fcffe-113">Distributed and almost entirely serverless.</span></span> <span data-ttu-id="fcffe-114">Solo se requieren servidores para el proceso de arranque.</span><span class="sxs-lookup"><span data-stu-id="fcffe-114">Servers are only required for the bootstrapping process.</span></span>  
  
-   <span data-ttu-id="fcffe-115">La publicación de nombres es segura y en ella no intervienen terceros.</span><span class="sxs-lookup"><span data-stu-id="fcffe-115">Secure name publication without the involvement of third parties.</span></span> <span data-ttu-id="fcffe-116">A diferencia de la publicación de nombres DNS, la publicación de nombres PNRP es instantánea y no tiene costo económico.</span><span class="sxs-lookup"><span data-stu-id="fcffe-116">Unlike DNS name publication, PNRP name publication is instantaneous and without financial cost.</span></span>  
  
-   <span data-ttu-id="fcffe-117">PNRP se actualiza en tiempo real, lo que impide la resolución de direcciones obsoletas.</span><span class="sxs-lookup"><span data-stu-id="fcffe-117">PNRP updates in real-time, which prevents the resolution of stale addresses.</span></span>  
  
-   <span data-ttu-id="fcffe-118">La resolución de nombres a través de PNRP va más allá de los equipos, ya que también permite la resolución de nombres para servicios.</span><span class="sxs-lookup"><span data-stu-id="fcffe-118">The resolution of names via PNRP extends beyond computers by also allowing name resolution for services.</span></span>  
  
-  
  
## <a name="the-systemnetpeertopeer-namespace"></a><span data-ttu-id="fcffe-119">El espacio de nombres System.Net.PeerToPeer</span><span class="sxs-lookup"><span data-stu-id="fcffe-119">The System.Net.PeerToPeer Namespace</span></span>  
  
-   <span data-ttu-id="fcffe-120">La funcionalidad PNRP está definida por el espacio de nombres <xref:System.Net.PeerToPeer> en .NET Framework versión 3.5.</span><span class="sxs-lookup"><span data-stu-id="fcffe-120">PNRP functionality is defined by the <xref:System.Net.PeerToPeer> namespace within the .NET Framework version 3.5.</span></span> <span data-ttu-id="fcffe-121">Proporciona un conjunto de tipos que se pueden usar para registrar y resolver nombres del mismo nivel con un servicio PNRP disponible.</span><span class="sxs-lookup"><span data-stu-id="fcffe-121">It provides a set of types that can be used to register and resolve peer names with an available PNRP service.</span></span>  
  
-  
  
-   <span data-ttu-id="fcffe-122">(Se pueden crear resoluciones del mismo nivel personalizadas y PNRP y crear instancias de ellas mediante los tipos proporcionados en el espacio de nombres <xref:System.ServiceModel.PeerResolvers>).</span><span class="sxs-lookup"><span data-stu-id="fcffe-122">(PNRP and custom peer resolvers can be created and instantiated using the types provided in the <xref:System.ServiceModel.PeerResolvers> namespace.)</span></span>  
  
-  
  
-   <span data-ttu-id="fcffe-123">Los tipos básicos que se usan para registrar y resolver los nombres con un servicio PNRP disponible son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="fcffe-123">The basic types used to register and resolve names with an available PNRP service are as follows:</span></span>  
  
-  
  
-   <span data-ttu-id="fcffe-124"><xref:System.Net.PeerToPeer.Cloud>: define la información que describe una nube PNRP disponible, incluido su ámbito.</span><span class="sxs-lookup"><span data-stu-id="fcffe-124"><xref:System.Net.PeerToPeer.Cloud>: Defines the information describing an available PNRP cloud, including its scope.</span></span>  
  
-   <span data-ttu-id="fcffe-125"><xref:System.Net.PeerToPeer.PeerName>: define un nombre del mismo nivel que puede usarse para registrar y resolver posteriormente un elemento del mismo nivel dentro de una nube.</span><span class="sxs-lookup"><span data-stu-id="fcffe-125"><xref:System.Net.PeerToPeer.PeerName>: Defines a peer name that can be used to register and subsequently resolve a peer within a cloud.</span></span>  
  
-   <span data-ttu-id="fcffe-126"><xref:System.Net.PeerToPeer.PeerNameRecord>: define el registro de la nube PNRP que contiene la información de registro de un elemento del mismo nivel, que incluye los puntos de conexión de red en los que se puede establecer contacto con dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="fcffe-126"><xref:System.Net.PeerToPeer.PeerNameRecord>: Defines the record in PNRP cloud that contains the registration information for a peer, which includes the network endpoints at which the peer can be contacted.</span></span>  
  
-   <span data-ttu-id="fcffe-127"><xref:System.Net.PeerToPeer.PeerNameRegistration>: define el proceso de registro para un nombre del mismo nivel, incluidos los métodos para iniciar y detener el registro de nombres del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="fcffe-127"><xref:System.Net.PeerToPeer.PeerNameRegistration>: Defines the registration process for a peer name, including methods to start and stop peer name registration.</span></span>  
  
-   <span data-ttu-id="fcffe-128"><xref:System.Net.PeerToPeer.PeerNameResolver>: define el proceso para resolver un nombre del mismo nivel en sus puntos de conexión de red, incluidos los métodos sincrónicos y asincrónicos para la resolución.</span><span class="sxs-lookup"><span data-stu-id="fcffe-128"><xref:System.Net.PeerToPeer.PeerNameResolver>: Defines the process for resolving a peer name to its network endpoint(s), including both synchronous and asynchronous methods for resolution.</span></span>  
  
-  
  
-  
  
## <a name="see-also"></a><span data-ttu-id="fcffe-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcffe-129">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers>  
 <xref:System.Net.PeerToPeer>  
 [<span data-ttu-id="fcffe-130">Network Programming Samples (Ejemplos de programación de red)</span><span class="sxs-lookup"><span data-stu-id="fcffe-130">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)  
 [<span data-ttu-id="fcffe-131">Ejemplo de tecnología punto a punto</span><span class="sxs-lookup"><span data-stu-id="fcffe-131">PeerToPeer Technology Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=179571)
