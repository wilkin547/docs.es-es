---
description: Más información acerca de cómo implementar un proxy de detección
title: Implementar un proxy de detección
ms.date: 03/30/2017
ms.assetid: dda20e79-8df3-438e-a281-69d779d978ec
ms.openlocfilehash: cfd897e114c99bcacb24e9981ee4a3e99e06636c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734040"
---
# <a name="implementing-a-discovery-proxy"></a><span data-ttu-id="23005-103">Implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="23005-103">Implementing a Discovery Proxy</span></span>

<span data-ttu-id="23005-104">Esta sección describe los pasos necesarios para implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="23005-104">This section describes the steps required to implement a discovery proxy.</span></span> <span data-ttu-id="23005-105">Un proxy de detección es un servicio independiente que contiene un repositorio de servicios.</span><span class="sxs-lookup"><span data-stu-id="23005-105">A discovery proxy is a standalone service that contains a repository of services.</span></span> <span data-ttu-id="23005-106">Los clientes pueden consultar un proxy de detección para buscar servicios reconocibles que el proxy conoce.</span><span class="sxs-lookup"><span data-stu-id="23005-106">Clients can query a discovery proxy to find discoverable services that the proxy is aware of.</span></span> <span data-ttu-id="23005-107">El modo en que un proxy se rellena con servicios depende del implementador.</span><span class="sxs-lookup"><span data-stu-id="23005-107">How a proxy is populated with services is up to the implementer.</span></span> <span data-ttu-id="23005-108">Por ejemplo, un proxy de detección puede conectarse a un repositorio de servicio existente y hacer que esa información sea reconocible, un administrador puede utilizar una API de administración para agregar servicios reconocibles a un proxy, o un proxy de detección puede utilizar la funcionalidad de anuncio para actualizar su memoria caché interna.</span><span class="sxs-lookup"><span data-stu-id="23005-108">For example, a discovery proxy can connect to an existing service repository and make that information discoverable, an administrator can use a management API to add discoverable services to a proxy, or a discovery proxy can use the announcement functionality to update its internal cache.</span></span>  
  
 <span data-ttu-id="23005-109">La implementación WCF proporciona clases base que le permiten compilar un proxy con facilidad.</span><span class="sxs-lookup"><span data-stu-id="23005-109">The WCF implementation provides base classes that allow you to easily build a proxy.</span></span> <span data-ttu-id="23005-110">Puede utilizar estas API para compilar un proxy de detección encima de un repositorio existente.</span><span class="sxs-lookup"><span data-stu-id="23005-110">You can utilize these APIs to build a Discovery Proxy on top of your existing repository.</span></span>  
  
 <span data-ttu-id="23005-111">El proxy de detección implementado aquí es como cualquier otro servicio de WCF y también puede hacer que el proxy de detección se pueda detectar y que los clientes busquen sus puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="23005-111">The discovery proxy implemented here is like any other WCF services, in that you can also make the discovery proxy discoverable and have the clients locate its endpoints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23005-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="23005-112">In This Section</span></span>  

 [<span data-ttu-id="23005-113">Procedimiento para implementar un proxy de detección</span><span class="sxs-lookup"><span data-stu-id="23005-113">How to: Implement a Discovery Proxy</span></span>](how-to-implement-a-discovery-proxy.md)  
 <span data-ttu-id="23005-114">Describe cómo implementar un proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="23005-114">Describes how to implement a discovery proxy.</span></span>  
  
 [<span data-ttu-id="23005-115">Procedimiento para implementar un servicio reconocible que se registra con el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="23005-115">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](discoverable-service-that-registers-with-the-discovery-proxy.md)  
 <span data-ttu-id="23005-116">Describe cómo implementar un servicio WCF reconocible que se registra con el proxy de detección.</span><span class="sxs-lookup"><span data-stu-id="23005-116">Describes how to implement a discoverable WCF service that registers with the discovery proxy.</span></span>  
  
 [<span data-ttu-id="23005-117">Procedimiento para implementar una aplicación cliente que usa el proxy de detección para buscar un servicio</span><span class="sxs-lookup"><span data-stu-id="23005-117">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](client-app-discovery-proxy-to-find-a-service.md)  
 <span data-ttu-id="23005-118">Describe cómo implementar una aplicación cliente de WCF que usa el proxy de detección para buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="23005-118">Describes how to implement a WCF client application that uses the discovery proxy to search for a service.</span></span>  
  
 [<span data-ttu-id="23005-119">Procedimiento para probar el proxy de detección</span><span class="sxs-lookup"><span data-stu-id="23005-119">How to: Test the Discovery Proxy</span></span>](how-to-test-the-discovery-proxy.md)  
 <span data-ttu-id="23005-120">Describe cómo probar el código escrito en los tres temas los anteriores.</span><span class="sxs-lookup"><span data-stu-id="23005-120">Describes how to test the code written in the previous three topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23005-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="23005-121">See also</span></span>

- [<span data-ttu-id="23005-122">Detección de WCF</span><span class="sxs-lookup"><span data-stu-id="23005-122">WCF Discovery</span></span>](wcf-discovery.md)
- [<span data-ttu-id="23005-123">Procedimiento para agregar detectabilidad mediante programación a un cliente y un servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="23005-123">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>](how-to-programmatically-add-discoverability-to-a-wcf-service-and-client.md)
