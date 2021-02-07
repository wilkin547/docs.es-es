---
description: 'Más información sobre: actividades de equipo de estado en WF'
title: Actividades de equipo de estado en WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 4571bdbabc30e721523ae18449454627c0bf7319
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755257"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="0666f-103">Actividades de equipo de estado en WF</span><span class="sxs-lookup"><span data-stu-id="0666f-103">State Machine Activities in WF</span></span>

<span data-ttu-id="0666f-104">.NET Framework 4,5 proporciona varias actividades proporcionadas por el sistema y diseñadores de actividades para crear flujos de trabajo de máquina de Estados.</span><span class="sxs-lookup"><span data-stu-id="0666f-104">.NET Framework 4.5 provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="0666f-105">Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="0666f-105">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="0666f-106">Representa un estado en un equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="0666f-106">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="0666f-107">Representa un estado de terminación en una máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="0666f-107">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="0666f-108"><xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación.</span><span class="sxs-lookup"><span data-stu-id="0666f-108"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="0666f-109">Para obtener más información, vea [Diseñador de actividades FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="0666f-109">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="0666f-110">Representa la transición entre dos estados.</span><span class="sxs-lookup"><span data-stu-id="0666f-110">Represents the transition between two states.</span></span> <span data-ttu-id="0666f-111">No hay ningún elemento del **cuadro de herramientas** para <xref:System.Activities.Statements.Transition> ; las transiciones se crean en el diseñador de flujo de trabajo arrastrando y colocando una línea entre dos Estados, o colocando un estado en los triángulos que aparecen cuando un estado se mantiene sobre otro.</span><span class="sxs-lookup"><span data-stu-id="0666f-111">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="0666f-112">Para obtener más información, vea [Diseñador de actividades de transición](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="0666f-112">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0666f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0666f-113">See also</span></span>

- [<span data-ttu-id="0666f-114">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="0666f-114">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
