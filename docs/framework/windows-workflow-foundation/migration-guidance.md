---
title: Guía de migración
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 8abc241331b3d322763ffd67b41ff676ebc680fb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283207"
---
# <a name="migration-guidance"></a>Guía de migración

En el .NET Framework 4, Microsoft está lanzando la segunda versión principal de Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] se lanzó en WinFX (esto incluía los tipos en los espacios de nombres System. Workflow.\*; ahora se conoce como WF3) y se mejoró en .NET Framework 3,5. WF3 también forma parte de la .NET Framework 4, pero existe allí junto con la nueva tecnología de flujo de trabajo (los tipos en los espacios de nombres System. Activities.\*; se hace referencia a ellos como WF4). A la hora de plantearse cuándo adoptar WF4, es importante reconocer primero que controla el tiempo.  
  
- WF3 es una parte totalmente compatible del .NET Framework 4.  
  
- Las aplicaciones de WF3 se ejecutan en el .NET Framework 4 sin modificaciones y continúan siendo totalmente compatibles.  
  
- Se pueden crear nuevas aplicaciones WF3 y las aplicaciones existentes se pueden editar en Visual Studio 2012 y son totalmente compatibles.  
  
 Por lo tanto, la decisión de adoptar el .NET Framework 4 está desacoplada de la decisión de pasar a WF4 (System. Activities.\*) de WF3 (System. Workflow.\*). En este tema se proporcionan vínculos a la guía de migración de WF que proporciona información sobre cómo trabajar con WF3 y WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Notas del producto y guías básicas sobre migración de WF  
 El tema [información general sobre la migración de WF](https://go.microsoft.com/fwlink/?LinkId=153873) proporciona una amplia información general de la relación entre WF3 y WF4 y las estrategias de migración. Los temas de ayuda profundizan en asuntos específicos.  
  
 [Información general sobre la migración de WF](https://go.microsoft.com/fwlink/?LinkId=153873)  
 Describe la relación entre WF3 y WF4, además las opciones que tiene como usuario o usuario potencial de tecnología del flujo de trabajo en .NET 4.  
  
 [Migración de WF: procedimientos recomendados para el desarrollo de WF3](https://go.microsoft.com/fwlink/?LinkId=153852)  
 Describe cómo diseñar los artefactos de WF3 de modo que se puedan migrar más fácilmente a WF4.  
  
 [Guía de WF: reglas](https://go.microsoft.com/fwlink/?LinkId=153854)  
 Describe cómo incorporar las inversiones relacionadas con las reglas a las soluciones de .NET Framework 4.  
  
 [Guía de WF: equipo de estado](https://go.microsoft.com/fwlink/?LinkId=153855)  
 Trata sobre el modelado de flujo de control de WF4 en ausencia de una actividad de máquina de estados.  
  
 Tenga en cuenta que esta guía se aplica solamente a proyectos de flujo de trabajo que tienen como destino .NET Framework 4. Los flujos de trabajo de máquina de estados se agregaron en .NET 4.0.1 con el lanzamiento de la Actualización de plataforma 1, y se incluyeron como parte de .NET Framework 4.5. Para obtener más información acerca de los flujos de trabajo de máquina de Estados en .NET 4.0.1-4.0.3 y .NET Framework 4,5, consulte [actualización 4.0.1 para las características de Microsoft .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) y los [flujos de trabajo de máquina de Estados](state-machine-workflows.md).  
  
 [Guía de migración de WF: actividades personalizadas](https://go.microsoft.com/fwlink/?LinkId=153856)  
 Proporciona ejemplos e instrucciones para rediseñar actividades personalizadas de WF3 en WF4.  
  
 [Guía de migración de WF: actividades personalizadas avanzadas](https://go.microsoft.com/fwlink/?LinkId=275560)  
 Proporciona una guía para rediseñar actividades personalizadas WF3 avanzadas que usan colas WF3 y programan actividades secundarias como actividades personalizadas de WF4.  
  
 [Guía de migración de WF: flujos de trabajo](https://go.microsoft.com/fwlink/?LinkId=153858)  
 Proporciona ejemplos e instrucciones para rediseñar flujos de trabajo de WF3 en WF4.  
  
 [Guía de migración de WF: hospedaje de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=275561)  
 Proporciona una guía para rediseñar el código de hospedaje de WF3 como un código de hospedaje WF4. El objetivo es tratar las diferencias clave entre WF3 Y WF4 en el hospedaje de flujos de trabajo.  
  
 [Guía de migración de WF: seguimiento del flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=275562)  
 Proporciona una guía para rediseñar el código de seguimiento WF3 y la configuración mediante un código y una configuración de seguimiento de WF4 equivalentes.  
  
 [Guía de WF: servicios de flujo de trabajo](https://go.microsoft.com/fwlink/?LinkId=275564)  
 Proporciona instrucciones paso a paso basadas en ejemplos para rediseñar flujos de trabajo que implementan los servicios web de Windows Communication Foundation (más conocidos como servicios de flujo de trabajo) creados en WF3 para usar WF4, para escenarios comunes en actividades estándar.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.Interop>
