---
title: '&lt;services&gt; de &lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 219a05b1-f573-45c9-849b-e86bc373b62f
ms.openlocfilehash: a17e40ef3aea1f60abc8aa2f1101141ed80b62b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675124"
---
# <a name="ltservicesgt-of-ltworkflowruntimegt"></a><span data-ttu-id="0e370-102">&lt;services&gt; de &lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="0e370-102">&lt;services&gt; of &lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="0e370-103">Representa la colección de servicios que se agregarán al motor <xref:System.Workflow.Runtime.WorkflowRuntime>.</span><span class="sxs-lookup"><span data-stu-id="0e370-103">Represents a collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="0e370-104">Los elementos son de tipo <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span><span class="sxs-lookup"><span data-stu-id="0e370-104">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="0e370-105">El motor en tiempo de ejecución del flujo de trabajo inicializará y agregará los servicios especificados en la colección a sus servicios cuando se llame al constructor <xref:System.Workflow.Runtime.WorkflowRuntime> adecuado.</span><span class="sxs-lookup"><span data-stu-id="0e370-105">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="0e370-106">Por consiguiente los servicios especificados en la colección deben seguir ciertas reglas sobre las firmas de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="0e370-106">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="0e370-107">Vea <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0e370-107">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e370-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e370-108">See also</span></span>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="0e370-109">[Archivos de configuración de flujo de trabajo](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0e370-109">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
