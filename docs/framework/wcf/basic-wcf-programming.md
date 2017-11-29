---
title: "Programación básica de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa43705fd20a60512ca4c460bb3048220aa1e193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="509b8-102">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="509b8-102">Basic WCF Programming</span></span>
<span data-ttu-id="509b8-103">En esta sección se presentan los principios para crear aplicaciones de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509b8-103">This section presents the fundamentals for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="509b8-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="509b8-104">In This Section</span></span>  
 [<span data-ttu-id="509b8-105">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="509b8-105">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 <span data-ttu-id="509b8-106">Describe el ciclo de vida del diseño, creación e implementación de aplicaciones de servicio y cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509b8-106">Describes the lifecycle of designing, building, and deploying [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and client applications.</span></span>  
  
 [<span data-ttu-id="509b8-107">Diseño e implementación de servicios</span><span class="sxs-lookup"><span data-stu-id="509b8-107">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 <span data-ttu-id="509b8-108">Describe cómo diseñar e implementar un contrato de servicios, elegir un patrón de intercambio de mensajes, especificar un contrato de errores y otros aspectos básicos de los servicios.</span><span class="sxs-lookup"><span data-stu-id="509b8-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>  
  
 [<span data-ttu-id="509b8-109">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="509b8-109">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 <span data-ttu-id="509b8-110">Describe cómo configurar un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para admitir los requisitos de contrato, personalizar el comportamiento en tiempo de ejecución local e indicar la dirección para publicar el servicio.</span><span class="sxs-lookup"><span data-stu-id="509b8-110">Describes how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>  
  
 [<span data-ttu-id="509b8-111">Servicios de hospedaje</span><span class="sxs-lookup"><span data-stu-id="509b8-111">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 <span data-ttu-id="509b8-112">Describe los fundamentos de los servicios de hospedaje en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="509b8-112">Describes the basics of hosting services in an application.</span></span>  
  
 [<span data-ttu-id="509b8-113">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="509b8-113">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 <span data-ttu-id="509b8-114">Describe cómo obtener los metadatos de los servicios, convertir eso en código de cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], controlar problemas de seguridad, y crear, configurar y hospedar un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509b8-114">Describes how to obtain metadata from services, convert that into [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code, handle security issues, and build, configure, and host an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
 [<span data-ttu-id="509b8-115">Introducción a la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="509b8-115">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
 <span data-ttu-id="509b8-116">Describe cómo extender [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para crear soluciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="509b8-116">Describes how to extend [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] to create custom solutions.</span></span>  
  
 [<span data-ttu-id="509b8-117">Inicio rápido de solución de problemas de WCF</span><span class="sxs-lookup"><span data-stu-id="509b8-117">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 <span data-ttu-id="509b8-118">Describe algunos de los problemas más comunes que se producen, qué puede hacer para resolverlos y dónde encontrar más información sobre el problema.</span><span class="sxs-lookup"><span data-stu-id="509b8-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>  
  
 [<span data-ttu-id="509b8-119">WCF y ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="509b8-119">WCF and ASP.NET Web API</span></span>](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)  
 <span data-ttu-id="509b8-120">Describe las dos tecnologías, cómo se relacionan entre sí y cuándo se deben usar.</span><span class="sxs-lookup"><span data-stu-id="509b8-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="509b8-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="509b8-121">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="509b8-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="509b8-122">Related Sections</span></span>  
 [<span data-ttu-id="509b8-123">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="509b8-123">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)  
  
 [<span data-ttu-id="509b8-124">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="509b8-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="509b8-125">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="509b8-125">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="509b8-126">Instrucciones y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="509b8-126">Guidelines and Best Practices</span></span>](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
  
 [<span data-ttu-id="509b8-127">Herramientas de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="509b8-127">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
  
 [<span data-ttu-id="509b8-128">Ejemplos de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="509b8-128">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="509b8-129">Introducción</span><span class="sxs-lookup"><span data-stu-id="509b8-129">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
  
 [<span data-ttu-id="509b8-130">Hospedaje de IIS utilizando código en línea</span><span class="sxs-lookup"><span data-stu-id="509b8-130">IIS Hosting Using Inline Code</span></span>](../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)  
  
 [<span data-ttu-id="509b8-131">Autohospedaje</span><span class="sxs-lookup"><span data-stu-id="509b8-131">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
