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
# <a name="state-machine-activities-in-wf"></a>Actividades de equipo de estado en WF

.NET Framework 4,5 proporciona varias actividades proporcionadas por el sistema y diseñadores de actividades para crear flujos de trabajo de máquina de Estados.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.|  
|<xref:System.Activities.Statements.State>|Representa un estado en un equipo de estado.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Representa un estado de terminación en una máquina de estados. <xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación. Para obtener más información, vea [Diseñador de actividades FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Representa la transición entre dos estados. No hay ningún elemento del **cuadro de herramientas** para <xref:System.Activities.Statements.Transition> ; las transiciones se crean en el diseñador de flujo de trabajo arrastrando y colocando una línea entre dos Estados, o colocando un estado en los triángulos que aparecen cuando un estado se mantiene sobre otro. Para obtener más información, vea [Diseñador de actividades de transición](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Vea también

- [Tutorial de introducción](getting-started-tutorial.md)
