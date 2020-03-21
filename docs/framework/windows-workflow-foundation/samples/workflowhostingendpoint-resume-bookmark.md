---
title: Reanudar marcador WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: d393a26dd29624765e01b139e818de8a41f73e06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182744"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="45da5-102">Reanudar marcador WorkflowHostingEndpoint</span><span class="sxs-lookup"><span data-stu-id="45da5-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="45da5-103">En este ejemplo se muestra cómo se puede utilizar <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con <xref:System.ServiceModel.Activities.WorkflowServiceHost> para crear instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45da5-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="45da5-104">Muestra</span><span class="sxs-lookup"><span data-stu-id="45da5-104">Demonstrates</span></span>  
 <span data-ttu-id="45da5-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="45da5-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="45da5-106">Discusión</span><span class="sxs-lookup"><span data-stu-id="45da5-106">Discussion</span></span>  
 <span data-ttu-id="45da5-107">Este ejemplo usa <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> para crear una instancia de flujo de trabajo hospedada mediante <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="45da5-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="45da5-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> es un punto de extensibilidad para <xref:System.ServiceModel.Activities.WorkflowServiceHost> que se puede usar en los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="45da5-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
- <span data-ttu-id="45da5-109">Crear instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45da5-109">Creating new workflow instances.</span></span>  
  
- <span data-ttu-id="45da5-110">Reanudar marcadores en una instancia de flujo de trabajo hospedada en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="45da5-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="45da5-111">El punto de conexión de ejemplo que se incluye expone un contrato que proporciona operaciones para crear un flujo de trabajo y devolver un Id. de instancia o para crear una instancia con un identificador concreto.</span><span class="sxs-lookup"><span data-stu-id="45da5-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="45da5-112">La aplicación de consola de ejemplo crea una instancia de <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definición de flujo de trabajo básica y agrega un `CreationEndpoint` al host.</span><span class="sxs-lookup"><span data-stu-id="45da5-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="45da5-113">A continuación, llama a la operación `Create` en el punto de conexión para crear una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45da5-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="45da5-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="45da5-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="45da5-115">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="45da5-115">Build the solution.</span></span>  
  
2. <span data-ttu-id="45da5-116">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45da5-116">Run the application.</span></span> <span data-ttu-id="45da5-117">La consola `CreationEndpoint` muestra un mensaje que incluye el Id. de instancia cuando se crea la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45da5-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="45da5-118">El mensaje "¡Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="45da5-118">The message "Hello World!"</span></span> <span data-ttu-id="45da5-119">se imprime por el flujo de trabajo en la reanudación correcta del marcador.</span><span class="sxs-lookup"><span data-stu-id="45da5-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="45da5-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="45da5-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="45da5-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="45da5-121">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="45da5-122">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="45da5-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="45da5-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="45da5-123">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
