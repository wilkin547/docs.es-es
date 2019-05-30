---
title: Actividades de equipo de estado en WF
ms.date: 03/30/2017
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
ms.openlocfilehash: 64af2698c878066464e2ca3f32d4522d99999aec
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378049"
---
# <a name="state-machine-activities-in-wf"></a>Actividades de equipo de estado en WF
.NET framework 4.5 proporciona varias actividades proporcionadas por el sistema y los diseñadores de actividad para crear flujos de trabajo de máquina de Estados.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.|  
|<xref:System.Activities.Statements.State>|Representa un estado en un equipo de estado.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Representa un estado de terminación en una máquina de estados. <xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación. Para obtener más información, consulte [Diseñador de actividad FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Representa la transición entre dos estados. No hay ningún **cuadro de herramientas** de elemento para <xref:System.Activities.Statements.Transition>; las transiciones se crean en el Diseñador de flujo de trabajo arrastrando y colocando una línea entre dos Estados, o colocando un estado en los triángulos que aparecen al mantener un estado frente a otro . Para obtener más información, consulte [Diseñador de actividad Transition](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Vea también

- [Tutorial de introducción](getting-started-tutorial.md)
