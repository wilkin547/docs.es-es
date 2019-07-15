---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804639"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a><span data-ttu-id="046ba-101">El método WorkflowDesigner.Load no elimina una propiedad de símbolo</span><span class="sxs-lookup"><span data-stu-id="046ba-101">WorkflowDesigner.Load doesn't remove symbol property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="046ba-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="046ba-102">Details</span></span>|<span data-ttu-id="046ba-103">Al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo y cargar un flujo de trabajo de la versión 3.5 rehospedado con el método <xref:System.Activities.Presentation.WorkflowDesigner.Load>, se inicia una excepción <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> mientras se guarda el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="046ba-103">When targeting the .NET Framework 4.5 in the workflow designer, and loading a re-hosted 3.5 workflow with the <xref:System.Activities.Presentation.WorkflowDesigner.Load> method, a <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> is thrown while saving the workflow.</span></span>|
|<span data-ttu-id="046ba-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="046ba-104">Suggestion</span></span>|<span data-ttu-id="046ba-105">Este error solo se manifiesta al seleccionar .NET Framework 4.5 como destino en el Diseñador de flujo de trabajo, por lo que una solución alternativa consiste en establecer <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> en la versión 4.0 de .NET Framework. Como alternativa, el problema se puede solucionar si se usa el método <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> para cargar el flujo de trabajo, en lugar de <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span><span class="sxs-lookup"><span data-stu-id="046ba-105">This bug only manifests when targeting .NET Framework 4.5 in the workflow designer, so it can be worked around by setting the <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> to the 4.0 .NET Framework.Alternatively, the issue may be avoided by using the <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> method to load the workflow, instead of <xref:System.Activities.Presentation.WorkflowDesigner.Load>.</span></span>|
|<span data-ttu-id="046ba-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="046ba-106">Scope</span></span>|<span data-ttu-id="046ba-107">Major</span><span class="sxs-lookup"><span data-stu-id="046ba-107">Major</span></span>|
|<span data-ttu-id="046ba-108">Versión</span><span class="sxs-lookup"><span data-stu-id="046ba-108">Version</span></span>|<span data-ttu-id="046ba-109">4.5</span><span class="sxs-lookup"><span data-stu-id="046ba-109">4.5</span></span>|
|<span data-ttu-id="046ba-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="046ba-110">Type</span></span>|<span data-ttu-id="046ba-111">Redestinación</span><span class="sxs-lookup"><span data-stu-id="046ba-111">Retargeting</span></span>|
|<span data-ttu-id="046ba-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="046ba-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

