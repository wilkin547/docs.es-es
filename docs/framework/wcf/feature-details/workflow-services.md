---
title: Servicios de flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e33915105ca9ff095f09bcd52431212e7c8e927
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-services"></a><span data-ttu-id="5ec60-102">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ec60-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="5ec60-103"> le permite describir totalmente un servicio basado en flujo de trabajo mediante declaración en XAML.</span><span class="sxs-lookup"><span data-stu-id="5ec60-103"> allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="5ec60-104">Puede definir un flujo de trabajo que implemente el servicio y describir los puntos de conexión que expone el servicio, todos completamente en XAML.</span><span class="sxs-lookup"><span data-stu-id="5ec60-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="5ec60-105">Los temas de esta sección describen con detalle el modelo de programación que permite escribir servicios mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="5ec60-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ec60-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5ec60-106">In This Section</span></span>  
 [<span data-ttu-id="5ec60-107">Información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ec60-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="5ec60-108">Describe los componentes implicados en la creación y hospedaje de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ec60-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="5ec60-109">Actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="5ec60-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="5ec60-110">Describe actividades que permiten a los flujos de trabajo enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="5ec60-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="5ec60-111">Creación de un servicio de flujo de trabajo con actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="5ec60-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="5ec60-112">Describe cómo utilizar actividades de mensajería para crear un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ec60-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="5ec60-113">Acceso a un servicio desde una aplicación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ec60-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="5ec60-114">Describe cómo llamar a un servicio desde una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ec60-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="5ec60-115">Correlación</span><span class="sxs-lookup"><span data-stu-id="5ec60-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="5ec60-116">Describe cómo la correlación asigna los mensajes entre sí y a las instancias.</span><span class="sxs-lookup"><span data-stu-id="5ec60-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="5ec60-117">Procesamiento de un mensaje sin orden</span><span class="sxs-lookup"><span data-stu-id="5ec60-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="5ec60-118">Describe la configuración de un servicio para aceptar los mensajes descompuestos.</span><span class="sxs-lookup"><span data-stu-id="5ec60-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="5ec60-119">Creación de un servicio de flujo de trabajo que llame a otro servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ec60-119">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 <span data-ttu-id="5ec60-120">Describe cómo llamar a un servicio de flujo de trabajo de forma sincrónica desde dentro de otro servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ec60-120">Describes how to synchronously call a workflow service from within another workflow service.</span></span>  
  
 [<span data-ttu-id="5ec60-121">Desarrollo de servicio de flujo de trabajo de contrato primero</span><span class="sxs-lookup"><span data-stu-id="5ec60-121">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="5ec60-122">Describe la creación de un servicio de flujo de trabajo basado en un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="5ec60-122">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="5ec60-123">Cómo crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="5ec60-123">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="5ec60-124">Proporciona un ejemplo paso a paso de la creación de un servicio de flujo de trabajo mediante un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="5ec60-124">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="5ec60-125">Hospedaje de información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ec60-125">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="5ec60-126">Describe los distintos aspectos de hospedar un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5ec60-126">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="5ec60-127">Uso de contratos en flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5ec60-127">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="5ec60-128">Describe los diferentes tipos de contratos e inferencia de contratos.</span><span class="sxs-lookup"><span data-stu-id="5ec60-128">Describes the different types of contracts and contract inference.</span></span>
