---
description: 'Más información sobre: <services> de <workflowRuntime>'
title: <services> de <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: 87cac8903263b4588db43c15d7849dcd7443d41c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682805"
---
# <a name="services-of-workflowruntime"></a><span data-ttu-id="379af-103">\<services> de \<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="379af-103">\<services> of \<workflowRuntime></span></span>

<span data-ttu-id="379af-104">Representa la colección de servicios que se agregarán al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="379af-104">Represents a collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="379af-105">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="379af-105">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="379af-106">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="379af-106">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="379af-107">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="379af-107">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="379af-108">Consulte <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="379af-108">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="379af-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="379af-109">See also</span></span>

- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="379af-110">[Archivos de configuración del flujo de trabajo](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="379af-110">[Workflow Configuration Files](/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
