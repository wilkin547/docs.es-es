---
title: Actividades de equipo de estado en WF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ed2b5ace499af3c050529e9f0f2cdd3634c247fd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="state-machine-activities-in-wf"></a>Actividades de equipo de estado en WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] proporciona varias actividades y diseñadores de actividad proporcionados por el sistema para crear flujos de trabajo de máquina de estados.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.|  
|<xref:System.Activities.Statements.State>|Representa un estado en un equipo de estado.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Representa un estado de terminación en una máquina de estados. <xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación. Para obtener más información, consulte [Diseñador de actividad FinalState](/visualstudio/workflow-designer/finalstate-activity-designer).|  
|<xref:System.Activities.Statements.Transition>|Representa la transición entre dos estados. No hay ningún **cuadro de herramientas** de elemento para <xref:System.Activities.Statements.Transition>; las transiciones se crean en el Diseñador de flujo de trabajo arrastrando y colocando una línea entre dos Estados, o colocando un estado en los triángulos que aparecen cuando un estado se mantiene el mouse sobre a otro . Para obtener más información, consulte [Diseñador de actividad Transition](/visualstudio/workflow-designer/transition-activity-designer).|  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)
