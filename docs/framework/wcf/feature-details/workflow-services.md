---
title: Servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: e7295041fe4b17e7e2b1560704badf20992d4b92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929706"
---
# <a name="workflow-services"></a><span data-ttu-id="35096-102">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="35096-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="35096-103">le permite describir totalmente un servicio basado en flujo de trabajo mediante declaración en XAML.</span><span class="sxs-lookup"><span data-stu-id="35096-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="35096-104">Puede definir un flujo de trabajo que implemente el servicio y describir los puntos de conexión que expone el servicio, todos completamente en XAML.</span><span class="sxs-lookup"><span data-stu-id="35096-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="35096-105">Los temas de esta sección describen con detalle el modelo de programación que permite escribir servicios mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="35096-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35096-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="35096-106">In This Section</span></span>  
 [<span data-ttu-id="35096-107">Información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="35096-107">Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services-overview.md)  
 <span data-ttu-id="35096-108">Describe los componentes implicados en la creación y hospedaje de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="35096-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="35096-109">Actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="35096-109">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 <span data-ttu-id="35096-110">Describe actividades que permiten a los flujos de trabajo enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="35096-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="35096-111">Cómo: Crear un servicio de flujo de trabajo con actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="35096-111">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="35096-112">Describe cómo utilizar actividades de mensajería para crear un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="35096-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="35096-113">Cómo: Acceso a un servicio desde una aplicación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="35096-113">How To: Access a Service From a Workflow Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="35096-114">Describe cómo llamar a un servicio desde una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="35096-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="35096-115">Correlación</span><span class="sxs-lookup"><span data-stu-id="35096-115">Correlation</span></span>](../../../../docs/framework/wcf/feature-details/correlation.md)  
 <span data-ttu-id="35096-116">Describe cómo la correlación asigna los mensajes entre sí y a las instancias.</span><span class="sxs-lookup"><span data-stu-id="35096-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="35096-117">Procesamiento de un mensaje sin orden</span><span class="sxs-lookup"><span data-stu-id="35096-117">Out-of-Order Message Processing</span></span>](../../../../docs/framework/wcf/feature-details/out-of-order-message-processing.md)  
 <span data-ttu-id="35096-118">Describe la configuración de un servicio para aceptar los mensajes descompuestos.</span><span class="sxs-lookup"><span data-stu-id="35096-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="35096-119">Desarrollo de servicio de flujo de trabajo de contrato primero</span><span class="sxs-lookup"><span data-stu-id="35096-119">Contract First Workflow Service Development</span></span>](../../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="35096-120">Describe la creación de un servicio de flujo de trabajo basado en un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="35096-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="35096-121">Cómo: Crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="35096-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="35096-122">Proporciona un ejemplo paso a paso de la creación de un servicio de flujo de trabajo mediante un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="35096-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="35096-123">Hospedaje de información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="35096-123">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 <span data-ttu-id="35096-124">Describe los distintos aspectos de hospedar un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="35096-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="35096-125">Uso de contratos en flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="35096-125">Using Contracts in Workflow</span></span>](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)  
 <span data-ttu-id="35096-126">Describe los diferentes tipos de contratos e inferencia de contratos.</span><span class="sxs-lookup"><span data-stu-id="35096-126">Describes the different types of contracts and contract inference.</span></span>
