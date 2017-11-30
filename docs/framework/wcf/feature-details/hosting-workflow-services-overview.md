---
title: "Hospedar información general de servicios de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="88a49-102">Hospedar información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="88a49-102">Hosting Workflow Services Overview</span></span>
<span data-ttu-id="88a49-103">Los servicios de flujo de trabajo deben estar hospedados para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="88a49-103">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="88a49-104">La clase <xref:System.ServiceModel.WorkflowServiceHost> es el host de flujo de trabajo que hospeda varias instancias, la configuración y la mensajería WCF (aunque no es necesario que los flujos de trabajo usen la mensajería para ser hospedados).</span><span class="sxs-lookup"><span data-stu-id="88a49-104">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="88a49-105">También se integra con la persistencia, el seguimiento y el control de instancias a través de un conjunto de comportamientos de servicio.</span><span class="sxs-lookup"><span data-stu-id="88a49-105">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="88a49-106">Al igual que el <xref:System.ServiceModel.ServiceHost> de WCF, el <xref:System.ServiceModel.WorkflowServiceHost> puede ser autohospedado por cualquier aplicación .NET administrada u hospedada en web (como un archivo .xamlx) en IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="88a49-106">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="88a49-107">Los temas de esta sección describen cómo hospedar un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="88a49-107">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88a49-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="88a49-108">In This Section</span></span>  
 [<span data-ttu-id="88a49-109">Servicios de hospedaje de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="88a49-109">Hosting Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 <span data-ttu-id="88a49-110">Describe los servicios de hospedaje de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="88a49-110">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="88a49-111">Funcionamiento interno de Host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="88a49-111">Workflow Service Host Internals</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 <span data-ttu-id="88a49-112">Describe cómo procesa la clase <xref:System.ServiceModel.WorkflowServiceHost> los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="88a49-112">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="88a49-113">Extensibilidad de Host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="88a49-113">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 <span data-ttu-id="88a49-114">Describe cómo ampliar la funcionalidad del host de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="88a49-114">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="88a49-115">Extremo de Control de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="88a49-115">Workflow Control Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 <span data-ttu-id="88a49-116">Describe cómo definir un punto de conexión que permite controlar instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="88a49-116">Describes how to define an endpoint that allows you to create workflow instances.</span></span>  
  
 [<span data-ttu-id="88a49-117">Cómo: hospedar un flujo de trabajo no pertenecientes al servicio en IIS</span><span class="sxs-lookup"><span data-stu-id="88a49-117">How to: Host a non-service workflow in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 <span data-ttu-id="88a49-118">Muestra cómo hospedar un flujo de trabajo que no es un servicio de flujo de trabajo en IIS.</span><span class="sxs-lookup"><span data-stu-id="88a49-118">Demonstrates hosting a workflow that is not a workflow service in IIS.</span></span>  
  
 [<span data-ttu-id="88a49-119">Cómo: hospedar un servicio de flujo de trabajo con Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="88a49-119">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="88a49-120">Muestra cómo hospedar un servicio de flujo de trabajo existente en Windows Server App Fabric.</span><span class="sxs-lookup"><span data-stu-id="88a49-120">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="88a49-121">Configurar WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="88a49-121">Configuring WorkflowServiceHost</span></span>](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 <span data-ttu-id="88a49-122">Describe cómo controlar la persistencia, el seguimiento, la inactividad y el comportamiento de las excepciones no controladas.</span><span class="sxs-lookup"><span data-stu-id="88a49-122">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="88a49-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="88a49-123">Reference</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="88a49-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="88a49-124">Related Sections</span></span>  
 [<span data-ttu-id="88a49-125">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="88a49-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
