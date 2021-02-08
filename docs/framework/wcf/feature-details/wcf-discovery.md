---
description: 'Más información sobre: detección de WCF'
title: Detección de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
ms.openlocfilehash: 67fa5800209676b11e9e49171483bf514b6a190a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779639"
---
# <a name="wcf-discovery"></a><span data-ttu-id="1263e-103">Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="1263e-103">WCF Discovery</span></span>

<span data-ttu-id="1263e-104">Windows Communication Foundation (WCF) proporciona compatibilidad para permitir que los servicios se puedan detectar en tiempo de ejecución de forma interoperable mediante el protocolo de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="1263e-104">Windows Communication Foundation (WCF) provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="1263e-105">Los servicios WCF pueden anunciar su disponibilidad a la red mediante un mensaje de multidifusión o un servidor proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="1263e-105">WCF services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="1263e-106">Las aplicaciones cliente pueden buscar en la red o en un servidor proxy de detección para encontrar servicios que cumplan un conjunto de criterios.</span><span class="sxs-lookup"><span data-stu-id="1263e-106">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="1263e-107">Los temas de esta sección proporcionan información general y describen el modelo de programación para esta característica de forma detallada.</span><span class="sxs-lookup"><span data-stu-id="1263e-107">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1263e-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1263e-108">In This Section</span></span>  

 [<span data-ttu-id="1263e-109">Información general de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="1263e-109">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)  
 <span data-ttu-id="1263e-110">Proporciona información general sobre la compatibilidad de WS-Discovery proporcionada por WCF.</span><span class="sxs-lookup"><span data-stu-id="1263e-110">Provides an overview of WS-Discovery support provided by WCF.</span></span>  
  
 [<span data-ttu-id="1263e-111">Modelo de objetos de Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="1263e-111">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)  
 <span data-ttu-id="1263e-112">Describe las clases de modelo de objetos y extensibilidad del soporte de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="1263e-112">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="1263e-113">Procedimiento para agregar detectabilidad mediante programación a un cliente y un servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="1263e-113">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="1263e-114">Muestra cómo hacer que un servicio de Windows Communication Foundation (WCF) sea reconocible.</span><span class="sxs-lookup"><span data-stu-id="1263e-114">Shows how to make a Windows Communication Foundation (WCF) service discoverable.</span></span>  
  
 [<span data-ttu-id="1263e-115">Implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="1263e-115">Implementing a Discovery Proxy</span></span>](implementing-a-discovery-proxy.md)  
 <span data-ttu-id="1263e-116">Describe los pasos necesarios para implementar un proxy de detección, un servicio reconocible que se registra con el proxy de detección, y un cliente que usa el proxy de detección para encontrar el servicio reconocible.</span><span class="sxs-lookup"><span data-stu-id="1263e-116">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="1263e-117">Versión de la detección</span><span class="sxs-lookup"><span data-stu-id="1263e-117">Discovery Versioning</span></span>](discovery-versioning.md)  
 <span data-ttu-id="1263e-118">Proporciona información general breve sobre una implementación del prototipo de algunas nuevas características de detección.</span><span class="sxs-lookup"><span data-stu-id="1263e-118">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="1263e-119">También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.</span><span class="sxs-lookup"><span data-stu-id="1263e-119">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="1263e-120">Configurar la detección en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="1263e-120">Configuring Discovery in a Configuration File</span></span>](configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="1263e-121">Muestra cómo configurar detección en la configuración.</span><span class="sxs-lookup"><span data-stu-id="1263e-121">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="1263e-122">Usar el canal del cliente de detección</span><span class="sxs-lookup"><span data-stu-id="1263e-122">Using the Discovery Client Channel</span></span>](using-the-discovery-client-channel.md)  
 <span data-ttu-id="1263e-123">Muestra cómo usar un canal de cliente de detección al escribir una aplicación cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="1263e-123">Shows how to use a Discovery Client Channel when writing a WCF client application.</span></span>
