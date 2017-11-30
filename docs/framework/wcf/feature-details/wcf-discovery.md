---
title: "Detección de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], discovery
- Windows Communication Foundation [WCF], discovery
- discovery [WCF]
ms.assetid: 462c4913-f388-45a9-9042-28ae96a4e735
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fda50f14d9003b81f93840571b8b27f874f7730b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-discovery"></a><span data-ttu-id="d2cc7-102">Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="d2cc7-102">WCF Discovery</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d2cc7-103"> proporciona el soporte para habilitar el reconocimiento de los servicios en tiempo de ejecución de forma interoperable mediante el protocolo WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-103"> provides support to enable services to be discoverable at runtime in an interoperable way using the WS-Discovery protocol.</span></span> <span data-ttu-id="d2cc7-104">Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden anunciar su disponibilidad a la red mediante un mensaje de multidifusión o a un servidor proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can announce their availability to the network using a multicast message or to a discovery proxy server.</span></span> <span data-ttu-id="d2cc7-105">Las aplicaciones cliente pueden buscar en la red o en un servidor proxy de detección para encontrar servicios que cumplan un conjunto de criterios.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-105">Client applications can search the network or a discovery proxy server to find services that meet a set of criteria.</span></span> <span data-ttu-id="d2cc7-106">Los temas de esta sección proporcionan información general y describen el modelo de programación para esta característica de forma detallada.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-106">The topics in this section provide an overview and describe the programming model for this feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d2cc7-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d2cc7-107">In This Section</span></span>  
 [<span data-ttu-id="d2cc7-108">Información general sobre la detección WCF</span><span class="sxs-lookup"><span data-stu-id="d2cc7-108">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 <span data-ttu-id="d2cc7-109">Proporciona información general acerca del soporte de WS-Discovery proporcionado por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2cc7-109">Provides an overview of WS-Discovery support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="d2cc7-110">Modelo de objetos de detección WCF</span><span class="sxs-lookup"><span data-stu-id="d2cc7-110">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)  
 <span data-ttu-id="d2cc7-111">Describe las clases de modelo de objetos y extensibilidad del soporte de WS-Discovery.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-111">Describes the classes in the object model and extensibility of WS-Discovery support.</span></span>  
  
 [<span data-ttu-id="d2cc7-112">Cómo: agregar detectabilidad mediante programación a un servicio WCF y un cliente</span><span class="sxs-lookup"><span data-stu-id="d2cc7-112">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)  
 <span data-ttu-id="d2cc7-113">Muestra cómo hacer que un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] sea reconocible.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-113">Shows how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span>  
  
 [<span data-ttu-id="d2cc7-114">Implementar a un Proxy de detección</span><span class="sxs-lookup"><span data-stu-id="d2cc7-114">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 <span data-ttu-id="d2cc7-115">Describe los pasos necesarios para implementar un proxy de detección, un servicio reconocible que se registra con el proxy de detección, y un cliente que usa el proxy de detección para encontrar el servicio reconocible.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-115">Describes the steps required to implement a discovery proxy, a discoverable service that registers with the discovery proxy, and a client that uses the discovery proxy to find the discoverable service.</span></span>  
  
 [<span data-ttu-id="d2cc7-116">Versión de la detección</span><span class="sxs-lookup"><span data-stu-id="d2cc7-116">Discovery Versioning</span></span>](../../../../docs/framework/wcf/feature-details/discovery-versioning.md)  
 <span data-ttu-id="d2cc7-117">Proporciona información general breve sobre una implementación del prototipo de algunas nuevas características de detección.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-117">Provides a brief overview of a prototype implementation of some new discovery features.</span></span> <span data-ttu-id="d2cc7-118">También proporciona información general sobre cómo seleccionar la versión de detección que se desea usar.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-118">It also gives an overview on how to select the discovery version to use.</span></span>  
  
 [<span data-ttu-id="d2cc7-119">Configurar la detección en un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d2cc7-119">Configuring Discovery in a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/configuring-discovery-in-a-configuration-file.md)  
 <span data-ttu-id="d2cc7-120">Muestra cómo configurar detección en la configuración.</span><span class="sxs-lookup"><span data-stu-id="d2cc7-120">Shows how to configure Discovery in configuration.</span></span>  
  
 [<span data-ttu-id="d2cc7-121">Usar el canal de cliente de detección</span><span class="sxs-lookup"><span data-stu-id="d2cc7-121">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 <span data-ttu-id="d2cc7-122">Muestra cómo usar un canal del cliente de detección al escribir una aplicación cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2cc7-122">Shows how to use a Discovery Client Channel when writing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span>
