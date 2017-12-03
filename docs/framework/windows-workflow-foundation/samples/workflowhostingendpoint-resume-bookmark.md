---
title: Reanudar marcador WorkflowHostingEndpoint
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1179d09d68d8730847776cf98e3996e3e6817753
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="b54cc-102">Reanudar marcador WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="b54cc-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="b54cc-103">En este ejemplo se muestra cómo se puede utilizar <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con <xref:System.ServiceModel.Activities.WorkflowServiceHost> para crear instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b54cc-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b54cc-104">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="b54cc-104">Demonstrates</span></span>  
 <span data-ttu-id="b54cc-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="b54cc-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b54cc-106">Explicación</span><span class="sxs-lookup"><span data-stu-id="b54cc-106">Discussion</span></span>  
 <span data-ttu-id="b54cc-107">Este ejemplo usa <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> para crear una instancia de flujo de trabajo hospedada mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b54cc-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="b54cc-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> es un punto de extensibilidad para <xref:System.ServiceModel.Activities.WorkflowServiceHost> que se puede usar en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="b54cc-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="b54cc-109">Crear instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b54cc-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="b54cc-110">Reanudar marcadores en una instancia de flujo de trabajo hospedada en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b54cc-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="b54cc-111">El extremo de ejemplo que se incluye expone un contrato que proporciona operaciones para crear un flujo de trabajo y devolver un Id. de instancia o para crear una instancia con un identificador concreto.</span><span class="sxs-lookup"><span data-stu-id="b54cc-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="b54cc-112">La aplicación de consola de ejemplo crea una instancia de <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definición de flujo de trabajo básica y agrega un `CreationEndpoint` al host.</span><span class="sxs-lookup"><span data-stu-id="b54cc-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="b54cc-113">A continuación, llama a la operación `Create` en el extremo para crear una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b54cc-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b54cc-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b54cc-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b54cc-115">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="b54cc-115">Build the solution.</span></span>  
  
2.  <span data-ttu-id="b54cc-116">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b54cc-116">Run the application.</span></span> <span data-ttu-id="b54cc-117">La consola `CreationEndpoint` muestra un mensaje que incluye el Id. de instancia cuando se crea la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b54cc-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="b54cc-118">El mensaje "¡Hello World!"</span><span class="sxs-lookup"><span data-stu-id="b54cc-118">The message "Hello World!"</span></span> <span data-ttu-id="b54cc-119">se imprime el flujo de trabajo correcta reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="b54cc-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b54cc-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b54cc-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b54cc-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b54cc-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b54cc-122">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b54cc-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b54cc-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b54cc-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
