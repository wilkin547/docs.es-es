---
title: 'Cómo: Crear flujos de trabajo'
ms.date: 03/30/2017
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
ms.openlocfilehash: adaa322d4129f56abcad4fd848204ee373e907bd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502489"
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="c778e-102">Cómo: Crear flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c778e-102">How to: Create a Workflow</span></span>
<span data-ttu-id="c778e-103">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c778e-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="c778e-104">En los temas de esta sección recorren la creación de un flujo de trabajo que usa tanto las actividades integradas, como el <xref:System.Activities.Statements.Flowchart> actividad y las actividades personalizadas del anterior [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) tema.</span><span class="sxs-lookup"><span data-stu-id="c778e-104">This topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="c778e-105">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="c778e-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="c778e-106">Solo se necesita uno de los temas de esta sección para completar el tutorial; debe elegir el estilo que le interese y seguir ese paso.</span><span class="sxs-lookup"><span data-stu-id="c778e-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="c778e-107">Sin embargo, puede completar todos los temas si lo desea.</span><span class="sxs-lookup"><span data-stu-id="c778e-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c778e-108">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="c778e-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="c778e-109">Para completar este tema, primero debe completar [Cómo: crear una actividad](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="c778e-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c778e-110">Para descargar una versión completada del tutorial, consulte [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="c778e-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c778e-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c778e-111">In This Section</span></span>  
 [<span data-ttu-id="c778e-112">Crear un flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="c778e-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="c778e-113">Describe cómo crear un flujo de trabajo secuencial usando la actividad <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="c778e-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="c778e-114">Crear un flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="c778e-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="c778e-115">Describe cómo crear un flujo de trabajo de diagrama de flujo usando la actividad <xref:System.Activities.Statements.Flowchart> .</span><span class="sxs-lookup"><span data-stu-id="c778e-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="c778e-116">Crear un flujo de trabajo de máquina de estados</span><span class="sxs-lookup"><span data-stu-id="c778e-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="c778e-117">Describe cómo crear un flujo de trabajo de máquina de estados usando la actividad <xref:System.Activities.Statements.StateMachine>.</span><span class="sxs-lookup"><span data-stu-id="c778e-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c778e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c778e-118">See Also</span></span>  
 [<span data-ttu-id="c778e-119">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="c778e-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
