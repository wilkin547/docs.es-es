---
description: 'Más información acerca de: servicios de flujo de trabajo'
title: Servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: 195ecf0322146a8735362dfbb82dc19bf1c04312
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704477"
---
# <a name="workflow-services"></a><span data-ttu-id="b6b3f-103">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b6b3f-103">Workflow Services</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="b6b3f-104">le permite describir totalmente un servicio basado en flujo de trabajo mediante declaración en XAML.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-104">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="b6b3f-105">Puede definir un flujo de trabajo que implemente el servicio y describir los puntos de conexión que expone el servicio, todos completamente en XAML.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-105">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="b6b3f-106">Los temas de esta sección describen con detalle el modelo de programación que permite escribir servicios mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-106">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6b3f-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b6b3f-107">In This Section</span></span>  

 [<span data-ttu-id="b6b3f-108">Información general sobre los servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b6b3f-108">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="b6b3f-109">Describe los componentes implicados en la creación y hospedaje de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-109">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="b6b3f-110">Actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="b6b3f-110">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="b6b3f-111">Describe actividades que permiten a los flujos de trabajo enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-111">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="b6b3f-112">Procedimiento para crear un servicio de flujo de trabajo con actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="b6b3f-112">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="b6b3f-113">Describe cómo utilizar actividades de mensajería para crear un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-113">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="b6b3f-114">Cómo obtener acceso a un servicio desde una aplicación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b6b3f-114">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="b6b3f-115">Describe cómo llamar a un servicio desde una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-115">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="b6b3f-116">Correlación</span><span class="sxs-lookup"><span data-stu-id="b6b3f-116">Correlation</span></span>](correlation.md)  
 <span data-ttu-id="b6b3f-117">Describe cómo la correlación asigna los mensajes entre sí y a las instancias.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-117">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="b6b3f-118">Procesar un mensaje sin orden</span><span class="sxs-lookup"><span data-stu-id="b6b3f-118">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="b6b3f-119">Describe la configuración de un servicio para aceptar los mensajes descompuestos.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-119">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="b6b3f-120">Desarrollo de servicio de flujo de trabajo de contrato primero</span><span class="sxs-lookup"><span data-stu-id="b6b3f-120">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="b6b3f-121">Describe la creación de un servicio de flujo de trabajo basado en un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-121">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="b6b3f-122">Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="b6b3f-122">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="b6b3f-123">Proporciona un ejemplo paso a paso de la creación de un servicio de flujo de trabajo mediante un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-123">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="b6b3f-124">Hospedar información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b6b3f-124">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="b6b3f-125">Describe los distintos aspectos de hospedar un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-125">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="b6b3f-126">Utilizar contratos en flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b6b3f-126">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="b6b3f-127">Describe los diferentes tipos de contratos e inferencia de contratos.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-127">Describes the different types of contracts and contract inference.</span></span>
