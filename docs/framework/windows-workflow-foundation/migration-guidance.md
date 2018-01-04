---
title: "Guía de migración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a8b8321239e3f01b30bcbe0400930a292a8f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="migration-guidance"></a>Guía de migración
En [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], Microsoft lanza la segunda versión principal de [!INCLUDE[wf](../../../includes/wf-md.md)]. [!INCLUDE[wf1](../../../includes/wf1-md.md)] se lanzó en [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (incluía los tipos de los espacios de nombres System.Workflow.*; ahora se conoce como WF3) y se mejoró en [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. WF3 también es parte de la [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], aunque está presente junto con la nueva tecnología de flujo de trabajo (los tipos de System.Activities.\* espacios de nombres; conoce como WF4). A la hora de plantearse cuándo adoptar WF4, es importante reconocer primero que controla el tiempo.  
  
-   WF3 es totalmente compatible con [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
-   Aplicaciones WF3 se ejecutan en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] sin modificación alguna y siguen siendo totalmente compatibles.  
  
-   Se pueden crear nuevas aplicaciones WF3, mientras que las ya existentes se pueden editar en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. Todas ellas serán compatibles.  
  
 Por lo tanto, la decisión de adoptar .NET Framework 4 se separa de la decisión de mover a WF4 (System.Activities) desde WF3 (System.Workflow.\*). En este tema se proporcionan vínculos a la guía de migración de WF que proporciona información sobre cómo trabajar con WF3 y WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Notas del producto y guías básicas sobre migración de WF  
 El [información general sobre la migración de WF](http://go.microsoft.com/fwlink/?LinkId=153873) tema proporciona una amplia perspectiva de la relación entre las estrategias de migración y WF4 y WF3. Los temas de ayuda profundizan en asuntos específicos.  
  
 [Información general sobre la migración de WF](http://go.microsoft.com/fwlink/?LinkId=153873)  
 Describe la relación entre WF3 y WF4, además las opciones que tiene como usuario o usuario potencial de tecnología del flujo de trabajo en .NET 4.  
  
 [Migración de WF: Procedimientos recomendados para el desarrollo de WF3](http://go.microsoft.com/fwlink/?LinkId=153852)  
 Describe cómo diseñar los artefactos de WF3 de modo que se puedan migrar más fácilmente a WF4.  
  
 [Guía de WF: reglas](http://go.microsoft.com/fwlink/?LinkId=153854)  
 Trata sobre cómo presentar las inversiones relacionadas con las reglas en soluciones de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
 [Guía de WF: Equipo de estado de](http://go.microsoft.com/fwlink/?LinkId=153855)  
 Trata sobre el modelado de flujo de control de WF4 en ausencia de una actividad de máquina de estados.  
  
 Tenga en cuenta que esta guía se aplica solamente a proyectos de flujo de trabajo que tienen como destino .NET Framework 4. Los flujos de trabajo de máquina de estados se agregaron en .NET 4.0.1 con el lanzamiento de la Actualización de plataforma 1, y se incluyeron como parte de .NET Framework 4.5. [!INCLUDE[crabout](../../../includes/crabout-md.md)]flujos de trabajo de máquina de Estados en .NET 4.0.1 - 4.0.3 y .NET Framework 4.5, consulte [actualización 4.0.1 para características de Microsoft .NET Framework 4](http://msdn.microsoft.com/en-us/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) y [flujos de trabajo de máquina de estados](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).  
  
 [Libro de cocina de migración de WF: Las actividades personalizadas](http://go.microsoft.com/fwlink/?LinkId=153856)  
 Proporciona ejemplos e instrucciones para rediseñar actividades personalizadas de WF3 en WF4.  
  
 [Guía de migración de WF: Actividades personalizadas avanzadas](http://go.microsoft.com/fwlink/?LinkId=275560)  
 Proporciona una guía para rediseñar actividades personalizadas WF3 avanzadas que usan colas WF3 y programan actividades secundarias como actividades personalizadas de WF4.  
  
 [Guía de migración de WF: flujos de trabajo](http://go.microsoft.com/fwlink/?LinkId=153858)  
 Proporciona ejemplos e instrucciones para rediseñar flujos de trabajo de WF3 en WF4.  
  
 [Libro de cocina de migración de WF: Hospedaje de flujo de trabajo](http://go.microsoft.com/fwlink/?LinkId=275561)  
 Proporciona una guía para rediseñar el código de hospedaje de WF3 como un código de hospedaje WF4. El objetivo es tratar las diferencias clave entre WF3 Y WF4 en el hospedaje de flujos de trabajo.  
  
 [Libro de cocina de migración de WF: Seguimiento de flujo de trabajo](http://go.microsoft.com/fwlink/?LinkId=275562)  
 Proporciona una guía para rediseñar el código de seguimiento WF3 y la configuración mediante un código y una configuración de seguimiento de WF4 equivalentes.  
  
 [Guía de WF: Servicios de flujo de trabajo de](http://go.microsoft.com/fwlink/?LinkId=275564)  
 Proporciona instrucciones paso a paso basadas en ejemplos para rediseñar flujos de trabajo que implementan los servicios web de Windows Communication Foundation (más conocidos como servicios de flujo de trabajo) creados en WF3 para usar WF4, para escenarios comunes en actividades estándar.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Activities.Statements.Interop>
