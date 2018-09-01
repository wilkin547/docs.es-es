---
title: Validar relaciones de actividad
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: 50f08118fb5ad4d9b8fe809e7ab3cc5d57f28149
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394690"
---
# <a name="activity-relationships-validation"></a><span data-ttu-id="82ed1-102">Validar relaciones de actividad</span><span class="sxs-lookup"><span data-stu-id="82ed1-102">Activity Relationships Validation</span></span>
<span data-ttu-id="82ed1-103">Este ejemplo consta de tres actividades, `CreateCity`, `CreateState` y `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="82ed1-103">This sample consists of three activities, `CreateCity`, `CreateState`, and `CreateCountry`.</span></span> <span data-ttu-id="82ed1-104">`CreateCity` debe estar dentro de una actividad `CreateState` y `CreateState` debe estar dentro de una actividad `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="82ed1-104">`CreateCity` must be inside a `CreateState` activity, and `CreateState` must be inside a `CreateCountry` activity.</span></span> <span data-ttu-id="82ed1-105">Para este ejemplo, la lógica de validación está en código para la actividad `CreateState` y en XAML para la actividad `CreateCity`.</span><span class="sxs-lookup"><span data-stu-id="82ed1-105">For the purpose of this sample, the validation logic is in code for the `CreateState` activity, and in XAML for the `CreateCity` activity.</span></span> <span data-ttu-id="82ed1-106">Ambas restricciones tienen el mismo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="82ed1-106">Both constraints have the same behavior.</span></span>  
  
 <span data-ttu-id="82ed1-107">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] proporciona las tres actividades auxiliares siguientes que permiten al desarrollador validar las relaciones entre las actividades.</span><span class="sxs-lookup"><span data-stu-id="82ed1-107">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] provides the following three helper activities that allow the developer to validate relationships between activities:</span></span>  
  
 <xref:System.Activities.Validation.GetParentChain>  
 <span data-ttu-id="82ed1-108">Proporciona la colección de todas las actividades que pertenecen al elemento primario del nodo actual</span><span class="sxs-lookup"><span data-stu-id="82ed1-108">Provides the collection of all activities that belong to the parent of the current node</span></span>  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 <span data-ttu-id="82ed1-109">Proporciona la colección de todas las actividades que pertenecen al subárbol del nodo actual, excluido el nodo actual</span><span class="sxs-lookup"><span data-stu-id="82ed1-109">Provides the collection of all activities that belong to the sub-tree of the current node, excluding the current node</span></span>  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 <span data-ttu-id="82ed1-110">Proporciona la colección de todas las actividades incluidas en el mismo árbol que el nodo actual</span><span class="sxs-lookup"><span data-stu-id="82ed1-110">Provides the collection of all activities in the same tree as the current node</span></span>  
  
 <span data-ttu-id="82ed1-111">En el ejemplo, se usa una actividad <xref:System.Activities.Statements.ForEach%601> para recorrer la colección que devuelve <xref:System.Activities.Validation.GetParentChain>.</span><span class="sxs-lookup"><span data-stu-id="82ed1-111">In the sample, a <xref:System.Activities.Statements.ForEach%601> activity is used to walk through the collection returned by <xref:System.Activities.Validation.GetParentChain>.</span></span> <span data-ttu-id="82ed1-112">En cada elemento de la colección, su tipo se compara con `CreateCountry` (o `CreateState` si se está validando `CreateCity`); y cuando se encuentra una coincidencia, la marca de resultado se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="82ed1-112">For every element in the collection, its type is compared to `CreateCountry` (or `CreateState` if `CreateCity` is being validated), and when a match is found the result flag is set to `true`.</span></span> <span data-ttu-id="82ed1-113">Finalmente, <xref:System.Activities.Validation.AssertValidation> se utiliza para generar un error de validación si la marca del resultado se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="82ed1-113">Finally, an <xref:System.Activities.Validation.AssertValidation> is used to generate a validation error if the result flag is set to `false`.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="82ed1-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="82ed1-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="82ed1-115">Abra la solución de ejemplo ContainmentValidation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82ed1-115">Open the ContainmentValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="82ed1-116">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="82ed1-116">Build the solution.</span></span>  
  
3.  <span data-ttu-id="82ed1-117">Presione CTRL + F5 para iniciar el programa.</span><span class="sxs-lookup"><span data-stu-id="82ed1-117">Press CTRL + F5 to launch the program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82ed1-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="82ed1-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="82ed1-119">Compruebe el siguiente directorio (predeterminado) antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="82ed1-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="82ed1-120">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="82ed1-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="82ed1-121">Este ejemplo se encuentra en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="82ed1-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
