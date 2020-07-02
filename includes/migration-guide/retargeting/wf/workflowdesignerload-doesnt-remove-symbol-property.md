---
ms.openlocfilehash: ddc98448101c65003001ad05e67f29d75d99ad44
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616086"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="8a2e7-101">El método WorkflowDesigner.Load no elimina una propiedad de símbolo</span><span class="sxs-lookup"><span data-stu-id="8a2e7-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

#### <a name="details"></a><span data-ttu-id="8a2e7-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8a2e7-102">Details</span></span>

<span data-ttu-id="8a2e7-103">Al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo y cargar un flujo de trabajo de la versión 3.5 rehospedado con el método <xref:System.Activities.Presentation.WorkflowDesigner.Load>, se inicia una excepción <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> mientras se guarda el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a2e7-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=fullName> is thrown while saving the workflow.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8a2e7-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8a2e7-104">Suggestion</span></span>

<span data-ttu-id="8a2e7-105">Este error solo se manifiesta al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo, por lo que una solución alternativa consiste en establecer `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` en la versión 4.0 de .NET Framework. Como alternativa, el problema se puede solucionar si se usa el método <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> para cargar el flujo de trabajo, en lugar de <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="8a2e7-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the `WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName` to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>

| <span data-ttu-id="8a2e7-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="8a2e7-106">Name</span></span>    | <span data-ttu-id="8a2e7-107">Valor</span><span class="sxs-lookup"><span data-stu-id="8a2e7-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8a2e7-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8a2e7-108">Scope</span></span>   | <span data-ttu-id="8a2e7-109">Major</span><span class="sxs-lookup"><span data-stu-id="8a2e7-109">Major</span></span>       |
| <span data-ttu-id="8a2e7-110">Versión</span><span class="sxs-lookup"><span data-stu-id="8a2e7-110">Version</span></span> | <span data-ttu-id="8a2e7-111">4.5</span><span class="sxs-lookup"><span data-stu-id="8a2e7-111">4.5</span></span>         |
| <span data-ttu-id="8a2e7-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a2e7-112">Type</span></span>    | <span data-ttu-id="8a2e7-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="8a2e7-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="8a2e7-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8a2e7-114">Affected APIs</span></span>

- <xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType>
