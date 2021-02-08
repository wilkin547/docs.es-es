---
description: 'Más información sobre: WorkflowHostingEndpoint resume Bookmark'
title: Reanudar marcador WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: 3da4579a7c0c09122cacaa5e3db39359b8e62936
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798139"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="a4fc7-103">Reanudar marcador WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="a4fc7-103">WorkflowHostingEndpoint Resume Bookmark</span></span>

<span data-ttu-id="a4fc7-104">En este ejemplo se muestra cómo se puede utilizar <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con <xref:System.ServiceModel.Activities.WorkflowServiceHost> para crear instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-104">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="a4fc7-105">Muestra</span><span class="sxs-lookup"><span data-stu-id="a4fc7-105">Demonstrates</span></span>  

 <span data-ttu-id="a4fc7-106"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="a4fc7-106"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="a4fc7-107">Debate</span><span class="sxs-lookup"><span data-stu-id="a4fc7-107">Discussion</span></span>  

 <span data-ttu-id="a4fc7-108">Este ejemplo usa <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> para crear una instancia de flujo de trabajo hospedada mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-108">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="a4fc7-109"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> es un punto de extensibilidad para <xref:System.ServiceModel.Activities.WorkflowServiceHost> que se puede usar en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="a4fc7-109"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
- <span data-ttu-id="a4fc7-110">Crear instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-110">Creating new workflow instances.</span></span>  
  
- <span data-ttu-id="a4fc7-111">Reanudar marcadores en una instancia de flujo de trabajo hospedada en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-111">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="a4fc7-112">El punto de conexión de ejemplo que se incluye expone un contrato que proporciona operaciones para crear un flujo de trabajo y devolver un Id. de instancia o para crear una instancia con un identificador concreto.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-112">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="a4fc7-113">La aplicación de consola de ejemplo crea una instancia de <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definición de flujo de trabajo básica y agrega un `CreationEndpoint` al host.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-113">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="a4fc7-114">A continuación, llama a la operación `Create` en el punto de conexión para crear una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-114">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a4fc7-115">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4fc7-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a4fc7-116">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-116">Build the solution.</span></span>  
  
2. <span data-ttu-id="a4fc7-117">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-117">Run the application.</span></span> <span data-ttu-id="a4fc7-118">La consola `CreationEndpoint` muestra un mensaje que incluye el Id. de instancia cuando se crea la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-118">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="a4fc7-119">El mensaje "Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="a4fc7-119">The message "Hello World!"</span></span> <span data-ttu-id="a4fc7-120">lo imprime el flujo de trabajo cuando se reanuda correctamente el marcador.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-120">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a4fc7-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4fc7-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-122">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a4fc7-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4fc7-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a4fc7-124">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
