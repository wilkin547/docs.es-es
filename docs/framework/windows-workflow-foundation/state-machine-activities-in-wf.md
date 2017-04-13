---
title: "Actividades de equipo de estado en WF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 93312eaf-07e0-4a55-b4f7-4cdbbc4dee2d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Actividades de equipo de estado en WF
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] proporciona varias actividades y diseñadores de actividad proporcionados por el sistema para crear flujos de trabajo de máquina de estados.  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.StateMachine>|Ejecuta actividades contenidas mediante el paradigma conocido de máquina de estados.|  
|<xref:System.Activities.Statements.State>|Representa un estado en una máquina de estados.|  
|<xref:System.Activities.Core.Presentation.FinalState>|Representa un estado de terminación en una máquina de estados.<xref:System.Activities.Core.Presentation.FinalState> es un diseñador de actividad que cuando se usa crea un <xref:System.Activities.Statements.State> preconfigurado como estado de terminación.Para obtener más información, vea [Diseñador de actividad FinalState](../Topic/FinalState%20Activity%20Designer.md).|  
|<xref:System.Activities.Statements.Transition>|Representa la transición entre dos estados.No hay ningún elemento **Cuadro de herramientas** para <xref:System.Activities.Statements.Transition>; las transiciones se crean en el diseñador de flujo de trabajo arrastrando y colocando una línea entre dos estados, o colocando un estado en los triángulos que aparecen cuando se mantiene el mouse en un estado sobre otro.Para obtener más información, vea [Diseñadores de actividad de transición](../Topic/Transition%20Activity%20Designer.md).|  
  
## Vea también  
 [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)