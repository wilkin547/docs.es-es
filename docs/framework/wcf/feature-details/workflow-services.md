---
title: Servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 7b05c766-f181-425d-9a3d-2a5e150c85f7
ms.openlocfilehash: c7a5c6245702497fcd75341b3ff7ba08dc190fa5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600132"
---
# <a name="workflow-services"></a><span data-ttu-id="c30f0-102">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c30f0-102">Workflow Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="c30f0-103">le permite describir totalmente un servicio basado en flujo de trabajo mediante declaración en XAML.</span><span class="sxs-lookup"><span data-stu-id="c30f0-103">allows you to fully describe a workflow-based service declaratively in XAML.</span></span> <span data-ttu-id="c30f0-104">Puede definir un flujo de trabajo que implemente el servicio y describir los puntos de conexión que expone el servicio, todos completamente en XAML.</span><span class="sxs-lookup"><span data-stu-id="c30f0-104">You can define a workflow that implements your service and describe endpoints the service exposes, all entirely in XAML.</span></span> <span data-ttu-id="c30f0-105">Los temas de esta sección describen con detalle el modelo de programación que permite escribir servicios mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="c30f0-105">The topics in this section describe, in detail, the programming model that supports writing services declaratively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c30f0-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c30f0-106">In This Section</span></span>  
 [<span data-ttu-id="c30f0-107">Información general sobre los servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c30f0-107">Workflow Services Overview</span></span>](workflow-services-overview.md)  
 <span data-ttu-id="c30f0-108">Describe los componentes implicados en la creación y hospedaje de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c30f0-108">Describes the components involved in creating and hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="c30f0-109">Actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="c30f0-109">Messaging Activities</span></span>](messaging-activities.md)  
 <span data-ttu-id="c30f0-110">Describe actividades que permiten a los flujos de trabajo enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="c30f0-110">Discusses activities that allow workflows to send and receive messages.</span></span>  
  
 [<span data-ttu-id="c30f0-111">Procedimiento para crear un servicio de flujo de trabajo con actividades de mensajería</span><span class="sxs-lookup"><span data-stu-id="c30f0-111">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)  
 <span data-ttu-id="c30f0-112">Describe cómo utilizar actividades de mensajería para crear un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c30f0-112">Describes how to use messaging activities to create a workflow service.</span></span>  
  
 [<span data-ttu-id="c30f0-113">Cómo obtener acceso a un servicio desde una aplicación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c30f0-113">How To: Access a Service From a Workflow Application</span></span>](how-to-access-a-service-from-a-workflow-application.md)  
 <span data-ttu-id="c30f0-114">Describe cómo llamar a un servicio desde una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c30f0-114">Discusses how to call a service from a workflow application.</span></span>  
  
 [<span data-ttu-id="c30f0-115">Relación</span><span class="sxs-lookup"><span data-stu-id="c30f0-115">Correlation</span></span>](correlation.md)  
 <span data-ttu-id="c30f0-116">Describe cómo la correlación asigna los mensajes entre sí y a las instancias.</span><span class="sxs-lookup"><span data-stu-id="c30f0-116">Discusses how correlation maps messages to each other and to instances.</span></span>  
  
 [<span data-ttu-id="c30f0-117">Procesar un mensaje sin orden</span><span class="sxs-lookup"><span data-stu-id="c30f0-117">Out-of-Order Message Processing</span></span>](out-of-order-message-processing.md)  
 <span data-ttu-id="c30f0-118">Describe la configuración de un servicio para aceptar los mensajes descompuestos.</span><span class="sxs-lookup"><span data-stu-id="c30f0-118">Describes configuring a service to accept out of order messages.</span></span>  
  
 [<span data-ttu-id="c30f0-119">Desarrollo de servicio de flujo de trabajo de contrato primero</span><span class="sxs-lookup"><span data-stu-id="c30f0-119">Contract First Workflow Service Development</span></span>](../../windows-workflow-foundation/contract-first-workflow-service-development.md)  
 <span data-ttu-id="c30f0-120">Describe la creación de un servicio de flujo de trabajo basado en un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="c30f0-120">Describes creating a workflow service based on an existing service contract.</span></span>  
  
 [<span data-ttu-id="c30f0-121">Procedimiento para crear un servicio de flujo de trabajo que consuma un contrato de servicio existente</span><span class="sxs-lookup"><span data-stu-id="c30f0-121">How to: Create a workflow service that consumes an existing service contract</span></span>](../../windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)  
 <span data-ttu-id="c30f0-122">Proporciona un ejemplo paso a paso de la creación de un servicio de flujo de trabajo mediante un contrato de servicio existente.</span><span class="sxs-lookup"><span data-stu-id="c30f0-122">Provides a step-by-step example of creating a workflow service using an existing service contract.</span></span>  
  
 [<span data-ttu-id="c30f0-123">Hospedar información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c30f0-123">Hosting Workflow Services Overview</span></span>](hosting-workflow-services-overview.md)  
 <span data-ttu-id="c30f0-124">Describe los distintos aspectos de hospedar un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c30f0-124">Describes the different aspects of hosting a workflow service.</span></span>  
  
 [<span data-ttu-id="c30f0-125">Utilizar contratos en flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c30f0-125">Using Contracts in Workflow</span></span>](using-contracts-in-workflow.md)  
 <span data-ttu-id="c30f0-126">Describe los diferentes tipos de contratos e inferencia de contratos.</span><span class="sxs-lookup"><span data-stu-id="c30f0-126">Describes the different types of contracts and contract inference.</span></span>
