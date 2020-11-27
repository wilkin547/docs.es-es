---
title: Ciclo de vida de programación básica
description: Obtenga información sobre las tareas para compilar una aplicación WCF. WCF permite que las aplicaciones se comuniquen en el mismo equipo, a través de redes o en distintas plataformas de aplicaciones.
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: f958bd06f617a5648b31332ebe9e7662d45cd241
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294851"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="bd574-104">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="bd574-104">Basic Programming Lifecycle</span></span>

<span data-ttu-id="bd574-105">Windows Communication Foundation (WCF) permite a las aplicaciones comunicar si están en el mismo equipo, a través de Internet o en distintas plataformas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd574-105">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="bd574-106">En este tema se describen las tareas necesarias para compilar una aplicación WCF.</span><span class="sxs-lookup"><span data-stu-id="bd574-106">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="bd574-107">Para obtener una aplicación de ejemplo en funcionamiento, vea el [tutorial de introducción](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-107">For a working sample application, see [Getting Started Tutorial](getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="bd574-108">Las tareas básicas</span><span class="sxs-lookup"><span data-stu-id="bd574-108">The Basic Tasks</span></span>  

 <span data-ttu-id="bd574-109">Las tareas básicas que se van a realizar son, en orden:</span><span class="sxs-lookup"><span data-stu-id="bd574-109">The basic tasks to perform are, in order:</span></span>  
  
1. <span data-ttu-id="bd574-110">Definir el contrato de servicios.</span><span class="sxs-lookup"><span data-stu-id="bd574-110">Define the service contract.</span></span> <span data-ttu-id="bd574-111">Un contrato de servicio especifica la firma de un servicio, los datos que intercambia y el resto de los datos necesarios contractualmente.</span><span class="sxs-lookup"><span data-stu-id="bd574-111">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="bd574-112">Para obtener más información, consulte [Designing Service Contracts](designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-112">For more information, see [Designing Service Contracts](designing-service-contracts.md).</span></span>  
  
2. <span data-ttu-id="bd574-113">Implementar el contrato.</span><span class="sxs-lookup"><span data-stu-id="bd574-113">Implement the contract.</span></span> <span data-ttu-id="bd574-114">Para implementar un contrato de servicio, cree una clase que implemente el contrato y especifique comportamientos personalizados que deba tener el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bd574-114">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="bd574-115">Para obtener más información, consulte [implementación de contratos de servicio](implementing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-115">For more information, see [Implementing Service Contracts](implementing-service-contracts.md).</span></span>  
  
3. <span data-ttu-id="bd574-116">Configurar el servicio especificando los puntos de conexión y el resto de la información de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="bd574-116">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="bd574-117">Para obtener más información, vea [configuración de servicios](configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-117">For more information, see [Configuring Services](configuring-services.md).</span></span>  
  
4. <span data-ttu-id="bd574-118">Hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bd574-118">Host the service.</span></span> <span data-ttu-id="bd574-119">Para obtener más información, vea [servicios de hospedaje](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-119">For more information, see [Hosting Services](hosting-services.md).</span></span>  
  
5. <span data-ttu-id="bd574-120">Compilar una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="bd574-120">Build a client application.</span></span> <span data-ttu-id="bd574-121">Para obtener más información, consulte [Building clients](building-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-121">For more information, see [Building Clients](building-clients.md).</span></span>  
  
 <span data-ttu-id="bd574-122">Aunque los temas de esta sección sigan este orden, algunos escenarios no se inician al principio.</span><span class="sxs-lookup"><span data-stu-id="bd574-122">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="bd574-123">Por ejemplo, si desea crear un cliente para un servicio existente, ha de comenzar en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="bd574-123">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="bd574-124">O si está creando un servicio que usarán otros, puede omitir el paso 5.</span><span class="sxs-lookup"><span data-stu-id="bd574-124">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="bd574-125">Una vez que esté familiarizado con el desarrollo de contratos de servicio, también puede leer la [Introducción a la extensibilidad](introduction-to-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="bd574-125">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](introduction-to-extensibility.md).</span></span> <span data-ttu-id="bd574-126">Si tiene problemas con el servicio, consulte la guía de [Inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md) para ver si otros tienen problemas o similares.</span><span class="sxs-lookup"><span data-stu-id="bd574-126">If you have problems with your service, check [WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd574-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd574-127">See also</span></span>

- [<span data-ttu-id="bd574-128">Implementación de contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="bd574-128">Implementing Service Contracts</span></span>](implementing-service-contracts.md)
