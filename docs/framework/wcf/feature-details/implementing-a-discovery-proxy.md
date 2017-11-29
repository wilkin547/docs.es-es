---
title: "Implementar un proxy de detección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ddea7bf69f697c5b9ecd9d41021bff2407522a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="cda5c-102">Implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="cda5c-102">Implementing a Discovery Proxy</span></span>
<span data-ttu-id="cda5c-103">Esta sección describe los pasos necesarios para implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="cda5c-103">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="cda5c-104">Un proxy de detección es un servicio independiente que contiene un repositorio de servicios.</span><span class="sxs-lookup"><span data-stu-id="cda5c-104">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="cda5c-105">Los clientes pueden consultar un proxy de detección para buscar servicios reconocibles que el proxy conoce.</span><span class="sxs-lookup"><span data-stu-id="cda5c-105">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="cda5c-106">El modo en que un proxy se rellena con servicios depende del implementador.</span><span class="sxs-lookup"><span data-stu-id="cda5c-106">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="cda5c-107">Por ejemplo, un proxy de detección puede conectarse a un repositorio de servicio existente y hacer que esa información sea reconocible, un administrador puede utilizar una API de administración para agregar servicios reconocibles a un proxy, o un proxy de detección puede utilizar la funcionalidad de anuncio para actualizar su memoria caché interna.</span><span class="sxs-lookup"><span data-stu-id="cda5c-107">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="cda5c-108">La implementación WCF proporciona clases base que le permiten compilar un proxy con facilidad.</span><span class="sxs-lookup"><span data-stu-id="cda5c-108">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="cda5c-109">Puede utilizar estas API para compilar un proxy de detección encima de un repositorio existente.</span><span class="sxs-lookup"><span data-stu-id="cda5c-109">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="cda5c-110">El proxy de detección implementado aquí es como cualquier otro servicio de WCF y también puede hacer que el proxy de detección se pueda detectar y que los clientes busquen sus extremos.</span><span class="sxs-lookup"><span data-stu-id="cda5c-110">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cda5c-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cda5c-111">In This Section</span></span>  
 [<span data-ttu-id="cda5c-112">Cómo: implementar un Proxy de detección</span><span class="sxs-lookup"><span data-stu-id="cda5c-112">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="cda5c-113">Describe cómo implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="cda5c-113">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="cda5c-114">Cómo: implementar un servicio reconocible que se registra con el Proxy de detección</span><span class="sxs-lookup"><span data-stu-id="cda5c-114">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="cda5c-115">Describe cómo implementar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reconocible que se registra con el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="cda5c-115">Describes how to implement a discoverable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="cda5c-116">Cómo: implementar una aplicación de cliente que utiliza el Proxy de detección para buscar un servicio</span><span class="sxs-lookup"><span data-stu-id="cda5c-116">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="cda5c-117">Describe cómo implementar una aplicación cliente de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utiliza el proxy de detección para buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="cda5c-117">Describes how to implement a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="cda5c-118">Cómo: probar el Proxy de detección</span><span class="sxs-lookup"><span data-stu-id="cda5c-118">How to: Test the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="cda5c-119">Describe cómo probar el código escrito en los tres temas los anteriores.</span><span class="sxs-lookup"><span data-stu-id="cda5c-119">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda5c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="cda5c-120">See Also</span></span>  
 [<span data-ttu-id="cda5c-121">Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="cda5c-121">WCF Discovery</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
 [<span data-ttu-id="cda5c-122">Cómo: agregar detectabilidad mediante programación a un servicio WCF y un cliente</span><span class="sxs-lookup"><span data-stu-id="cda5c-122">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
