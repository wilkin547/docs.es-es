---
title: Guía de migración
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 64f71061dda96279a7aa0fffa3642ae6d2d01c8f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649381"
---
# <a name="migration-guidance"></a>Guía de migración
En el [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], Microsoft está lanzando la segunda versión principal de Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] se lanzó en [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] (incluía los tipos de los espacios de nombres System.Workflow.*; ahora se conoce como WF3) y se mejoró en [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]. WF3 también es parte de la [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], aunque está presente junto con la nueva tecnología de flujo de trabajo (los tipos de System.Activities.\* espacios de nombres; conoce como WF4). A la hora de plantearse cuándo adoptar WF4, es importante reconocer primero que controla el tiempo.  
  
- WF3 es totalmente compatible con [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
- Aplicaciones WF3 se ejecutan en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] sin modificación alguna y siguen siendo totalmente compatibles.  
  
- Se pueden crear nuevas aplicaciones WF3 y las aplicaciones existentes se pueden editar en Visual Studio 2012 y son totalmente compatibles.  
  
 Por lo tanto, la decisión de adoptar .NET Framework 4 se separa de su decisión de migrar a WF4 (System.Activities) desde WF3 (System.Workflow.\*). En este tema se proporcionan vínculos a la guía de migración de WF que proporciona información sobre cómo trabajar con WF3 y WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Notas del producto y guías básicas sobre migración de WF  
 El [información general sobre la migración de WF](https://go.microsoft.com/fwlink/?LinkId=153873) tema proporciona una amplia visión general de la relación entre las estrategias de migración y WF4 y WF3. Los temas de ayuda profundizan en asuntos específicos.  
  
 [Información general sobre la migración de WF](https://go.microsoft.com/fwlink/?LinkId=153873)  
 Describe la relación entre WF3 y WF4, además las opciones que tiene como usuario o usuario potencial de tecnología del flujo de trabajo en .NET 4.  
  
 [Migración de WF: Procedimientos recomendados para el desarrollo de WF3](https://go.microsoft.com/fwlink/?LinkId=153852)  
 Describe cómo diseñar los artefactos de WF3 de modo que se puedan migrar más fácilmente a WF4.  
  
 [Guía de WF: reglas](https://go.microsoft.com/fwlink/?LinkId=153854)  
 Trata sobre cómo presentar las inversiones relacionadas con las reglas en soluciones de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
 [Guía de WF: Equipo de estado](https://go.microsoft.com/fwlink/?LinkId=153855)  
 Trata sobre el modelado de flujo de control de WF4 en ausencia de una actividad de máquina de estados.  
  
 Tenga en cuenta que esta guía se aplica solamente a proyectos de flujo de trabajo que tienen como destino .NET Framework 4. Los flujos de trabajo de máquina de estados se agregaron en .NET 4.0.1 con el lanzamiento de la Actualización de plataforma 1, y se incluyeron como parte de .NET Framework 4.5. Para obtener más información sobre los flujos de trabajo de máquina de Estados en .NET 4.0.1 - 4.0.3 y .NET Framework 4.5, vea [actualización 4.0.1 para Microsoft .NET Framework 4 características](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) y [flujos de trabajo de máquina de estados](state-machine-workflows.md).  
  
 [Guía básica de migración de WF: Actividades personalizadas](https://go.microsoft.com/fwlink/?LinkId=153856)  
 Proporciona ejemplos e instrucciones para rediseñar actividades personalizadas de WF3 en WF4.  
  
 [Guía básica de migración de WF: Actividades personalizadas avanzadas](https://go.microsoft.com/fwlink/?LinkId=275560)  
 Proporciona una guía para rediseñar actividades personalizadas WF3 avanzadas que usan colas WF3 y programan actividades secundarias como actividades personalizadas de WF4.  
  
 [Guía básica de migración de WF: Flujos de trabajo](https://go.microsoft.com/fwlink/?LinkId=153858)  
 Proporciona ejemplos e instrucciones para rediseñar flujos de trabajo de WF3 en WF4.  
  
 [Guía básica de migración de WF: Hospedaje de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=275561)  
 Proporciona una guía para rediseñar el código de hospedaje de WF3 como un código de hospedaje WF4. El objetivo es tratar las diferencias clave entre WF3 Y WF4 en el hospedaje de flujos de trabajo.  
  
 [Guía básica de migración de WF: Seguimiento de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=275562)  
 Proporciona una guía para rediseñar el código de seguimiento WF3 y la configuración mediante un código y una configuración de seguimiento de WF4 equivalentes.  
  
 [Guía de WF: Servicios de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=275564)  
 Proporciona instrucciones paso a paso basadas en ejemplos para rediseñar flujos de trabajo que implementan los servicios web de Windows Communication Foundation (más conocidos como servicios de flujo de trabajo) creados en WF3 para usar WF4, para escenarios comunes en actividades estándar.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.Interop>
