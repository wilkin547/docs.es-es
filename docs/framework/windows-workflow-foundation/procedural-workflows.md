---
title: Flujos de trabajo de procedimiento
description: En Workflow Foundation, los flujos de trabajo de procedimientos usan métodos de control de flujo similares a los que se encuentran en los lenguajes de procedimientos.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 13d1b5e55b84687e2a78db1a94317b8b1e33328c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246035"
---
# <a name="procedural-workflows"></a><span data-ttu-id="99915-103">Flujos de trabajo de procedimiento</span><span class="sxs-lookup"><span data-stu-id="99915-103">Procedural Workflows</span></span>

<span data-ttu-id="99915-104">Los flujos de trabajo de procedimiento usan métodos de control de flujo similares a los que se encuentren en lenguajes de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="99915-104">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="99915-105">Estas construcciones incluyen `While` y `If`.</span><span class="sxs-lookup"><span data-stu-id="99915-105">These constructs include `While` and `If`.</span></span> <span data-ttu-id="99915-106">Estos flujos de trabajo se pueden crear libremente con otras actividades de control de flujo como <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="99915-106">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="99915-107">Controlar el flujo de ejecución</span><span class="sxs-lookup"><span data-stu-id="99915-107">Controlling Execution Flow</span></span>  

 <span data-ttu-id="99915-108">La biblioteca de actividades del flujo de trabajo tiene actividades para modelar la mayoría de los métodos de control de flujo usados en lenguajes de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="99915-108">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="99915-109">Se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="99915-109">These include:</span></span>  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="99915-110">Para usar las actividades de control de flujo, arrástrelas y colóquelas desde el cuadro de herramientas de **actividad** en una actividad compuesta dentro de la ventana del diseñador.</span><span class="sxs-lookup"><span data-stu-id="99915-110">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99915-111">Si usa las características de hospedaje de Windows Server AppFabric para hospedar flujos de trabajo en una granja de servidores Web, AppFabric moverá las instancias entre diferentes servidores de AppFabric.</span><span class="sxs-lookup"><span data-stu-id="99915-111">If using the hosting features of Windows Server AppFabric to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="99915-112">Esto necesita que los recursos se puedan compartir entre todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="99915-112">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="99915-113">Ninguna de las actividades de flujo de trabajo predeterminadas de .NET 4 contiene ninguna operación que tenga acceso a recursos locales.</span><span class="sxs-lookup"><span data-stu-id="99915-113">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="99915-114">Puesto que AppFabric no ofrece ningún mecanismo para marcar un flujo de trabajo como inamovible, un desarrollador no debe crear actividades personalizadas que produzcan errores cuando se mueva un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="99915-114">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99915-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="99915-115">See also</span></span>

- [<span data-ttu-id="99915-116">Flujos de trabajo del diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="99915-116">Flowchart Workflows</span></span>](flowchart-workflows.md)
