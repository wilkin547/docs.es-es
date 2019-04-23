---
title: Actividades de equipo de estado en WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 5aee2a7cb078d9d62c9296f7dda9f28ff812a88a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120918"
---
# <a name="state-machine-activities-in-wf"></a><span data-ttu-id="8674a-102">Actividades de equipo de estado en WF</span><span class="sxs-lookup"><span data-stu-id="8674a-102">State Machine Activities in WF</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="8674a-103">proporciona varias actividades y diseñadores de actividad proporcionados por el sistema para crear flujos de trabajo de máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="8674a-103">provides several system-provided activities and activity designers for creating state machine workflows.</span></span>  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|<span data-ttu-id="8674a-104">Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="8674a-104">Executes contained activities using the familiar state machine paradigm.</span></span>|  
|<xref:System.Activities.Statements.State>|<span data-ttu-id="8674a-105">Representa un estado en un equipo de estado.</span><span class="sxs-lookup"><span data-stu-id="8674a-105">Represents a state in a state machine.</span></span>|  
|<xref:System.Activities.Core.Presentation.FinalState>|<span data-ttu-id="8674a-106">Representa un estado de terminación en una máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="8674a-106">Represents a terminating state in a state machine.</span></span> <span data-ttu-id="8674a-107"><xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación.</span><span class="sxs-lookup"><span data-stu-id="8674a-107"><xref:System.Activities.Core.Presentation.FinalState> is an activity designer that when used creates a <xref:System.Activities.Statements.State> preconfigured as a terminating state.</span></span> <span data-ttu-id="8674a-108">Para obtener más información, consulte [Diseñador de actividad FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="8674a-108">For more information, see [FinalState Activity Designer](/visualstudio/workflow-designer/finalstate-activity-designer).</span></span>|  
|<xref:System.Activities.Statements.Transition>|<span data-ttu-id="8674a-109">Representa la transición entre dos estados.</span><span class="sxs-lookup"><span data-stu-id="8674a-109">Represents the transition between two states.</span></span> <span data-ttu-id="8674a-110">No hay ningún **cuadro de herramientas** de elemento para <xref:System.Activities.Statements.Transition>; las transiciones se crean en el Diseñador de flujo de trabajo arrastrando y colocando una línea entre dos Estados, o colocando un estado en los triángulos que aparecen al mantener un estado frente a otro .</span><span class="sxs-lookup"><span data-stu-id="8674a-110">There is no **Toolbox** item for <xref:System.Activities.Statements.Transition>; transitions are created on the workflow designer by dragging and dropping a line between two states, or by dropping a state on the triangles that appear when one state is hovered over another.</span></span> <span data-ttu-id="8674a-111">Para obtener más información, consulte [Diseñador de actividad Transition](/visualstudio/workflow-designer/transition-activity-designer).</span><span class="sxs-lookup"><span data-stu-id="8674a-111">For more information, see [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8674a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8674a-112">See also</span></span>

- [<span data-ttu-id="8674a-113">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="8674a-113">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
