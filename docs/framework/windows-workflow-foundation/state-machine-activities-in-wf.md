---
title: Actividades de equipo de estado en WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: dd0bfae1f24ecd9f98c0a2f04265581f880202a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261727"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="8998d-102">Actividades de equipo de estado en WF</span><span class="sxs-lookup"><span data-stu-id="8998d-102">State Machine Activities in WF</span></span>

<span data-ttu-id="8998d-103">.NET Framework 4,5 proporciona varias actividades proporcionadas por el sistema y diseñadores de actividades para crear flujos de trabajo de máquina de Estados.</span><span class="sxs-lookup"><span data-stu-id="8998d-103">.NET Framework 4.5 provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="8998d-104">Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="8998d-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="8998d-105">Representa un estado en un equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="8998d-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="8998d-106">Representa un estado de terminación en una máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="8998d-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="8998d-107"><xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación.</span><span class="sxs-lookup"><span data-stu-id="8998d-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="8998d-108">Para obtener más información, vea [Diseñador de actividades FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="8998d-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="8998d-109">Representa la transición entre dos estados.</span><span class="sxs-lookup"><span data-stu-id="8998d-109">Represents the transition between two states.</span></span> <span data-ttu-id="8998d-110">No hay ningún elemento del **cuadro de herramientas** para <xref:System.Activities.Statements.Transition> ; las transiciones se crean en el diseñador de flujo de trabajo arrastrando y colocando una línea entre dos Estados, o colocando un estado en los triángulos que aparecen cuando un estado se mantiene sobre otro.</span><span class="sxs-lookup"><span data-stu-id="8998d-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="8998d-111">Para obtener más información, vea [Diseñador de actividades de transición](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="8998d-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8998d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8998d-112">See also</span></span>

- [<span data-ttu-id="8998d-113">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="8998d-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
