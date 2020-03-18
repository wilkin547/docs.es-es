---
title: Protocolo de Internet versión 6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: 367db4fa4e585d6066009dbd1afacb154829319a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047877"
---
# <a name="internet-protocol-version-6"></a><span data-ttu-id="a4b62-102">Protocolo de Internet versión 6</span><span class="sxs-lookup"><span data-stu-id="a4b62-102">Internet Protocol Version 6</span></span>
<span data-ttu-id="a4b62-103">El protocolo de Internet versión 6 (IPv6) es un nuevo conjunto de protocolos estándar para la capa de red de Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b62-103">The Internet Protocol version 6 (IPv6) is a new suite of standard protocols for the network layer of the Internet.</span></span> <span data-ttu-id="a4b62-104">IPv6 está diseñado para resolver muchos de los problemas que se producen en la versión actual del conjunto de protocolo de Internet (conocido como IPv4) en relación con el agotamiento de direcciones, la seguridad, la configuración automática, la extensibilidad, etc.</span><span class="sxs-lookup"><span data-stu-id="a4b62-104">IPv6 is designed to solve many of the problems of the current version of the Internet Protocol suite (known as IPv4) with regard to address depletion, security, auto-configuration, extensibility, and so on.</span></span> <span data-ttu-id="a4b62-105">IPv6 amplía las funciones de Internet para habilitar nuevos tipos de aplicaciones, incluidas las aplicaciones móviles y de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="a4b62-105">IPv6 expands the capabilities of the Internet to enable new kinds of applications, including peer-to-peer and mobile applications.</span></span> <span data-ttu-id="a4b62-106">A continuación se indican los principales problemas del protocolo IPv4 actual:</span><span class="sxs-lookup"><span data-stu-id="a4b62-106">The following are the main issues of the current IPv4 protocol:</span></span>  
  
- <span data-ttu-id="a4b62-107">Rápido agotamiento del espacio de direcciones.</span><span class="sxs-lookup"><span data-stu-id="a4b62-107">Rapid depletion of the address space.</span></span>  
  
     <span data-ttu-id="a4b62-108">Esto ha llevado al uso de traductores de direcciones de red (NAT) que asignan varias direcciones privadas a una sola dirección IP pública.</span><span class="sxs-lookup"><span data-stu-id="a4b62-108">This has led to the use of Network Address Translators (NATs) that map multiple private addresses to a single public IP address.</span></span> <span data-ttu-id="a4b62-109">Los principales problemas causados por este mecanismo son la sobrecarga de procesamiento y la falta de conectividad de extremo a extremo.</span><span class="sxs-lookup"><span data-stu-id="a4b62-109">The main problems created by this mechanism are processing overhead and lack of end-to-end connectivity.</span></span>  
  
- <span data-ttu-id="a4b62-110">Falta de compatibilidad jerárquica.</span><span class="sxs-lookup"><span data-stu-id="a4b62-110">Lack of hierarchy support.</span></span>  
  
     <span data-ttu-id="a4b62-111">Debido a su organización inherente de clases predefinidas, IPv4 carece de verdadera compatibilidad jerárquica.</span><span class="sxs-lookup"><span data-stu-id="a4b62-111">Because of its inherent predefined class organization, IPv4 lacks true hierarchical support.</span></span> <span data-ttu-id="a4b62-112">Es imposible estructurar las direcciones IP de forma que se asigne realmente la topología de red.</span><span class="sxs-lookup"><span data-stu-id="a4b62-112">It is impossible to structure the IP addresses in a way that truly maps the network topology.</span></span> <span data-ttu-id="a4b62-113">Este error de diseño fundamental crea la necesidad de grandes tablas de enrutamiento para entregar paquetes de IPv4 en cualquier ubicación en Internet.</span><span class="sxs-lookup"><span data-stu-id="a4b62-113">This crucial design flaw creates the need for large routing tables to deliver IPv4 packets to any location on the Internet.</span></span>  
  
- <span data-ttu-id="a4b62-114">Configuración de red compleja.</span><span class="sxs-lookup"><span data-stu-id="a4b62-114">Complex network configuration.</span></span>  
  
     <span data-ttu-id="a4b62-115">Con IPv4, las direcciones deben asignarse de forma estática o mediante un protocolo de configuración como DHCP.</span><span class="sxs-lookup"><span data-stu-id="a4b62-115">With IPv4, addresses must be assigned statically or using a configuration protocol such as DHCP.</span></span> <span data-ttu-id="a4b62-116">En una situación ideal, los hosts no deberían tener que confiar en la administración de una infraestructura DHCP.</span><span class="sxs-lookup"><span data-stu-id="a4b62-116">In an ideal situation, hosts would not have to rely on the administration of a DHCP infrastructure.</span></span> <span data-ttu-id="a4b62-117">En su lugar, deberían poder realizar la configuración por sí mismos en función del segmento de red en el que se encuentran.</span><span class="sxs-lookup"><span data-stu-id="a4b62-117">Instead, they would be able to configure themselves based on the network segment in which they are located.</span></span>  
  
- <span data-ttu-id="a4b62-118">Falta de autenticación y confidencialidad integradas.</span><span class="sxs-lookup"><span data-stu-id="a4b62-118">Lack of built-in authentication and confidentiality.</span></span>  
  
     <span data-ttu-id="a4b62-119">IPv4 no requiere compatibilidad con ningún mecanismo que proporcione la autenticación o el cifrado de los datos intercambiados.</span><span class="sxs-lookup"><span data-stu-id="a4b62-119">IPv4 does not require the support for any mechanism that provides authentication or encryption of the exchanged data.</span></span> <span data-ttu-id="a4b62-120">Esto cambia con IPv6.</span><span class="sxs-lookup"><span data-stu-id="a4b62-120">This changes with IPv6.</span></span> <span data-ttu-id="a4b62-121">El protocolo de seguridad de Internet (IPSec) es un requisito de compatibilidad con IPv6.</span><span class="sxs-lookup"><span data-stu-id="a4b62-121">Internet Protocol security (IPSec) is an IPv6 support requirement.</span></span>  
  
 <span data-ttu-id="a4b62-122">Un nuevo conjunto de protocolos debe cumplir los siguientes requisitos básicos:</span><span class="sxs-lookup"><span data-stu-id="a4b62-122">A new protocol suite must satisfy the following basic requirements:</span></span>  
  
- <span data-ttu-id="a4b62-123">Enrutamiento a gran escala y direccionamiento con poca sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="a4b62-123">Large-scale routing and addressing with low overhead.</span></span>  
  
- <span data-ttu-id="a4b62-124">Configuración automática para varias situaciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="a4b62-124">Auto-configuration for various connecting situations.</span></span>  
  
- <span data-ttu-id="a4b62-125">Autenticación y confidencialidad integradas.</span><span class="sxs-lookup"><span data-stu-id="a4b62-125">Built-in authentication and confidentiality.</span></span>  
  
 <span data-ttu-id="a4b62-126">Para obtener más información, vea [IPv6 Addressing](ipv6-addressing.md) (Direccionamiento IPv6), [IPv6 Routing](ipv6-routing.md) (Enrutamiento de IPv6), [IPv6 Auto-Configuration](ipv6-auto-configuration.md) (Configuración automática de IPv6), [Enabling and Disabling IPv6](enabling-and-disabling-ipv6.md) (Habilitar y deshabilitar IPv6) y [How to: Modify the Computer Configuration File to Enable IPv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md) (Cómo: Modificar el archivo de configuración de equipo para habilitar la compatibilidad con IPv6).</span><span class="sxs-lookup"><span data-stu-id="a4b62-126">For more information, see [IPv6 Addressing](ipv6-addressing.md), [IPv6 Routing](ipv6-routing.md), [IPv6 Auto-Configuration](ipv6-auto-configuration.md), [Enabling and Disabling IPv6](enabling-and-disabling-ipv6.md), and [How to: Modify the Computer Configuration File to Enable IPv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="a4b62-127">Referencias</span><span class="sxs-lookup"><span data-stu-id="a4b62-127">References</span></span>  
 <span data-ttu-id="a4b62-128">Aquí hay una selección de documentos RFC que se pueden encontrar en el sitio web de [Internet Engineering Task Force (IETF)](https://www.ietf.org/):</span><span class="sxs-lookup"><span data-stu-id="a4b62-128">The following are selected RFC documents that you can find at the [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website:</span></span>  
  
- <span data-ttu-id="a4b62-129">RFC 1287, Towards the Future Internet Architecture (Hacia la arquitectura de Internet del futuro).</span><span class="sxs-lookup"><span data-stu-id="a4b62-129">RFC 1287, Towards the Future Internet Architecture.</span></span>  
  
- <span data-ttu-id="a4b62-130">RFC 1454, Comparison of Proposals for Next Version of IP (Comparación de propuestas para una próxima versión de IP).</span><span class="sxs-lookup"><span data-stu-id="a4b62-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span></span>  
  
- <span data-ttu-id="a4b62-131">RFC 2373, IP Version 6 Addressing Architecture (Arquitectura de direccionamiento de IP versión 6).</span><span class="sxs-lookup"><span data-stu-id="a4b62-131">RFC 2373, IP Version 6 Addressing Architecture.</span></span>  
  
- <span data-ttu-id="a4b62-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format (Formato de dirección de unidifusión global agregable de IPv6).</span><span class="sxs-lookup"><span data-stu-id="a4b62-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span></span>  
  
 <span data-ttu-id="a4b62-133">También encontrará información relacionada con IPv6 en [IP versión 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).</span><span class="sxs-lookup"><span data-stu-id="a4b62-133">You can also find IPv6-related information on the [IP Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b62-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4b62-134">See also</span></span>

- [<span data-ttu-id="a4b62-135">Ejemplo de sockets IPv6</span><span class="sxs-lookup"><span data-stu-id="a4b62-135">IPv6 Sockets Sample</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms180981%28v=vs.85%29)
- [<span data-ttu-id="a4b62-136">Ejemplos de programación de red</span><span class="sxs-lookup"><span data-stu-id="a4b62-136">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="a4b62-137">Sockets</span><span class="sxs-lookup"><span data-stu-id="a4b62-137">Sockets</span></span>](sockets.md)
