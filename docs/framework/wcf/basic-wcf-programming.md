---
title: Programación básica de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
ms.openlocfilehash: eff565fa18e3360170584395adcf2a3e7029ac07
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960932"
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="cfff5-102">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="cfff5-102">Basic WCF programming</span></span>

<span data-ttu-id="cfff5-103">En esta sección se presentan los aspectos básicos para crear aplicaciones de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cfff5-103">This section presents the fundamentals for creating Windows Communication Foundation (WCF) applications.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="cfff5-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cfff5-104">In this section</span></span>

 <span data-ttu-id="cfff5-105">[Ciclo de vida de programación básica](basic-programming-lifecycle.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-105">[Basic Programming Lifecycle](basic-programming-lifecycle.md)</span></span>\
 <span data-ttu-id="cfff5-106">Describe el ciclo de vida del diseño, compilación e implementación de aplicaciones cliente y de servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="cfff5-106">Describes the lifecycle of designing, building, and deploying WCF service and client applications.</span></span>

 <span data-ttu-id="cfff5-107">[Diseño e implementación de servicios](designing-and-implementing-services.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-107">[Designing and Implementing Services](designing-and-implementing-services.md)</span></span>\
 <span data-ttu-id="cfff5-108">Describe cómo diseñar e implementar un contrato de servicios, elegir un patrón de intercambio de mensajes, especificar un contrato de errores y otros aspectos básicos de los servicios.</span><span class="sxs-lookup"><span data-stu-id="cfff5-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>

 <span data-ttu-id="cfff5-109">[Configuring Services](configuring-services.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-109">[Configuring Services](configuring-services.md)</span></span>\
 <span data-ttu-id="cfff5-110">Describe cómo configurar un servicio WCF para admitir los requisitos de contrato, personalizar el comportamiento de tiempo de ejecución local e indicar la dirección para publicar el servicio.</span><span class="sxs-lookup"><span data-stu-id="cfff5-110">Describes how to configure a WCF service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>

 <span data-ttu-id="cfff5-111">[Servicios de hospedaje](hosting-services.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-111">[Hosting Services](hosting-services.md)</span></span>\
 <span data-ttu-id="cfff5-112">Describe los fundamentos de los servicios de hospedaje en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="cfff5-112">Describes the basics of hosting services in an application.</span></span>

 <span data-ttu-id="cfff5-113">[Creación de clientes](building-clients.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-113">[Building Clients](building-clients.md)</span></span>\
 <span data-ttu-id="cfff5-114">Describe cómo obtener los metadatos de los servicios, convertirlos en el código de cliente de WCF, controlar los problemas de seguridad y compilar, configurar y hospedar un cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="cfff5-114">Describes how to obtain metadata from services, convert that into WCF client code, handle security issues, and build, configure, and host a WCF client.</span></span>

 <span data-ttu-id="cfff5-115">[Introducción a la extensibilidad](introduction-to-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-115">[Introduction to Extensibility](introduction-to-extensibility.md)</span></span>\
 <span data-ttu-id="cfff5-116">Describe cómo extender WCF para crear soluciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cfff5-116">Describes how to extend WCF to create custom solutions.</span></span>

 <span data-ttu-id="cfff5-117">Guía de [Inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-117">[WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md)</span></span>\
 <span data-ttu-id="cfff5-118">Describe algunos de los problemas más comunes que se producen, qué puede hacer para resolverlos y dónde encontrar más información sobre el problema.</span><span class="sxs-lookup"><span data-stu-id="cfff5-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>

 <span data-ttu-id="cfff5-119">\ [WCF y ASP.net web API](wcf-and-aspnet-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="cfff5-119">[WCF and ASP.NET Web API](wcf-and-aspnet-web-api.md)\</span></span>
 <span data-ttu-id="cfff5-120">Describe las dos tecnologías, cómo se relacionan entre sí y cuándo se deben usar.</span><span class="sxs-lookup"><span data-stu-id="cfff5-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>

## <a name="reference"></a><span data-ttu-id="cfff5-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="cfff5-121">Reference</span></span>

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Description>

## <a name="related-sections"></a><span data-ttu-id="cfff5-122">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cfff5-122">Related sections</span></span>

- [<span data-ttu-id="cfff5-123">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="cfff5-123">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="cfff5-124">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="cfff5-124">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="cfff5-125">Instrucciones y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="cfff5-125">Guidelines and Best Practices</span></span>](guidelines-and-best-practices.md)
- [<span data-ttu-id="cfff5-126">Herramientas de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cfff5-126">Windows Communication Foundation Tools</span></span>](tools.md)
- [<span data-ttu-id="cfff5-127">Ejemplos de Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="cfff5-127">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="cfff5-128">Introducción</span><span class="sxs-lookup"><span data-stu-id="cfff5-128">Getting Started</span></span>](./samples/getting-started-sample.md)
- [<span data-ttu-id="cfff5-129">Hospedaje de IIS mediante código en línea</span><span class="sxs-lookup"><span data-stu-id="cfff5-129">IIS Hosting Using Inline Code</span></span>](./samples/iis-hosting-using-inline-code.md)
- [<span data-ttu-id="cfff5-130">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="cfff5-130">Self-Host</span></span>](./samples/self-host.md)
