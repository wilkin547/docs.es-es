---
description: 'Más información sobre: Introducción a los servicios de flujo de trabajo de hospedaje'
title: Hospedar información general de servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: e183dfd7428c11cf20e731ab4a9975a7388b6f98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743088"
---
# <a name="hosting-workflow-services-overview"></a><span data-ttu-id="37010-103">Hospedar información general de servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37010-103">Hosting Workflow Services Overview</span></span>

<span data-ttu-id="37010-104">Los servicios de flujo de trabajo deben estar hospedados para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="37010-104">Workflow services must be hosted to execute.</span></span> <span data-ttu-id="37010-105">La clase <xref:System.ServiceModel.WorkflowServiceHost> es el host de flujo de trabajo que hospeda varias instancias, la configuración y la mensajería WCF (aunque no es necesario que los flujos de trabajo usen la mensajería para ser hospedados).</span><span class="sxs-lookup"><span data-stu-id="37010-105">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-the-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren’t required to use messaging in order to be hosted).</span></span>  <span data-ttu-id="37010-106">También se integra con la persistencia, el seguimiento y el control de instancias a través de un conjunto de comportamientos de servicio.</span><span class="sxs-lookup"><span data-stu-id="37010-106">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span>  <span data-ttu-id="37010-107">Al igual que el <xref:System.ServiceModel.ServiceHost> de WCF, el <xref:System.ServiceModel.WorkflowServiceHost> puede ser autohospedado por cualquier aplicación .NET administrada u hospedada en web (como un archivo .xamlx) en IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="37010-107">Just like WCF’s <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in any managed .NET application, or web-hosted (as a .xamlx file) in IIS / WAS.</span></span>  <span data-ttu-id="37010-108">Los temas de esta sección describen cómo hospedar un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37010-108">Topics in this section describe how to host a workflow service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37010-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="37010-109">In This Section</span></span>  

 [<span data-ttu-id="37010-110">Hospedar servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37010-110">Hosting Workflow Services</span></span>](hosting-workflow-services.md)  
 <span data-ttu-id="37010-111">Describe los servicios de hospedaje de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37010-111">Describes hosting workflow services.</span></span>  
  
 [<span data-ttu-id="37010-112">Información interna de extensiones del host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37010-112">Workflow Service Host Internals</span></span>](workflow-service-host-internals.md)  
 <span data-ttu-id="37010-113">Describe cómo procesa la clase <xref:System.ServiceModel.WorkflowServiceHost> los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="37010-113">Describes how <xref:System.ServiceModel.WorkflowServiceHost> processes incoming messages.</span></span>  
  
 [<span data-ttu-id="37010-114">Extensibilidad de host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37010-114">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)  
 <span data-ttu-id="37010-115">Describe cómo ampliar la funcionalidad del host de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37010-115">Describes how to extend the functionality of the workflow service host.</span></span>  
  
 [<span data-ttu-id="37010-116">Extremo de control de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37010-116">Workflow Control Endpoint</span></span>](workflow-control-endpoint.md)  
 <span data-ttu-id="37010-117">Describe cómo definir un punto de conexión que permite controlar instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37010-117">Describes how to define an endpoint that allows you to create workflow instances.</span></span>
  
 [<span data-ttu-id="37010-118">Procedimiento para hospedar un servicio de flujo de trabajo con Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="37010-118">How to: Host a Workflow Service with Windows Server App Fabric</span></span>](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 <span data-ttu-id="37010-119">Muestra cómo hospedar un servicio de flujo de trabajo existente en Windows Server App Fabric.</span><span class="sxs-lookup"><span data-stu-id="37010-119">Demonstrates how to host an existing workflow service in Windows Server App Fabric.</span></span>  
  
 [<span data-ttu-id="37010-120">Configurar WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="37010-120">Configuring WorkflowServiceHost</span></span>](configuring-workflowservicehost.md)  
 <span data-ttu-id="37010-121">Describe cómo controlar la persistencia, el seguimiento, la inactividad y el comportamiento de las excepciones no controladas.</span><span class="sxs-lookup"><span data-stu-id="37010-121">Describes how to control persistence, tracking, idle, and unhandled exception behavior.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="37010-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="37010-122">Reference</span></span>  

 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a><span data-ttu-id="37010-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="37010-123">Related Sections</span></span>  

 [<span data-ttu-id="37010-124">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37010-124">Workflow Services</span></span>](workflow-services.md)
