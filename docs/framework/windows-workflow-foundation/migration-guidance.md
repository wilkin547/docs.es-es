---
title: Guía de migración
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 16f725dcb5d6f6e5d06771b7836fa187be005910
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559205"
---
# <a name="migration-guidance"></a>Guía de migración

En el .NET Framework 4, Microsoft está lanzando la segunda versión principal de Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] se lanzó en WinFX (esto incluía los tipos de System. Workflow. \* namespaces; ahora conocido como WF3) y se mejoró en .NET Framework 3,5. WF3 también forma parte de la .NET Framework 4, pero existe allí junto con la nueva tecnología de flujo de trabajo (los tipos de System. Activities. \* namespaces; denominados WF4). A la hora de plantearse cuándo adoptar WF4, es importante reconocer primero que controla el tiempo.  
  
- WF3 es una parte totalmente compatible del .NET Framework 4.  
  
- Las aplicaciones de WF3 se ejecutan en el .NET Framework 4 sin modificaciones y continúan siendo totalmente compatibles.  
  
- Se pueden crear nuevas aplicaciones WF3 y las aplicaciones existentes se pueden editar en Visual Studio 2012 y son totalmente compatibles.  
  
 Por lo tanto, la decisión de adoptar el .NET Framework 4 está desacoplada de la decisión de pasar a WF4 (System. Activities. \* ) de WF3 (System. Workflow. \* ). En este tema se proporcionan vínculos a la guía de migración de WF que proporciona información sobre cómo trabajar con WF3 y WF4.  
  
## <a name="wf-migration-white-papers-and-cookbooks"></a>Notas del producto y guías de migración de WF

 El tema [información general sobre la migración de WF](/previous-versions/appfabric/ff383417(v=azure.10)) proporciona una amplia información general de la relación entre WF3 y WF4 y las estrategias de migración. Los temas de ayuda profundizan en asuntos específicos.  
  
 [Información general sobre la migración de WF](/previous-versions/appfabric/ff383417(v=azure.10))  
 Describe la relación entre WF3 y WF4, además las opciones que tiene como usuario o usuario potencial de tecnología del flujo de trabajo en .NET 4.  
  
 [Migración de WF: prácticas recomendadas para el desarrollo de WF3](/previous-versions/appfabric/ff383417(v=azure.10))  
 Describe cómo diseñar los artefactos de WF3 de modo que se puedan migrar más fácilmente a WF4.  
  
 [Guía de WF: reglas](/previous-versions/appfabric/ff383417(v=azure.10))  
 Describe cómo incorporar las inversiones relacionadas con las reglas a las soluciones de .NET Framework 4.  
  
 [Guía de WF: máquina de estados](/previous-versions/appfabric/ff383417(v=azure.10))  
 Trata sobre el modelado de flujo de control de WF4 en ausencia de una actividad de máquina de estados.  
  
 Tenga en cuenta que esta guía se aplica solamente a proyectos de flujo de trabajo que tienen como destino .NET Framework 4. Los flujos de trabajo de máquina de estados se agregaron en .NET 4.0.1 con el lanzamiento de la Actualización de plataforma 1, y se incluyeron como parte de .NET Framework 4.5. Para obtener más información acerca de los flujos de trabajo de máquina de Estados en .NET 4.0.1-4.0.3 y .NET Framework 4,5, consulte [actualización 4.0.1 para las características de Microsoft .NET Framework 4](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) y los [flujos de trabajo de máquina de Estados](state-machine-workflows.md).  
  
 [Guía básica sobre migración de WF: actividades personalizadas](/previous-versions/appfabric/ff383417(v=azure.10))  
 Proporciona ejemplos e instrucciones para rediseñar actividades personalizadas de WF3 en WF4.  
  
 [Guía básica sobre migración de WF: actividades personalizadas avanzadas](/previous-versions/appfabric/ff383417(v=azure.10))  
 Proporciona una guía para rediseñar actividades personalizadas WF3 avanzadas que usan colas WF3 y programan actividades secundarias como actividades personalizadas de WF4.  
  
 [Guía básica de migración de WF: flujos de trabajo](/previous-versions/appfabric/ff383417(v=azure.10))  
 Proporciona ejemplos e instrucciones para rediseñar flujos de trabajo de WF3 en WF4.  
  
 [Guía básica de migración de WF: hospedaje del flujo de trabajo](/previous-versions/appfabric/ff383417(v=azure.10))  
 Proporciona una guía para rediseñar el código de hospedaje de WF3 como un código de hospedaje WF4. El objetivo es tratar las diferencias clave entre WF3 Y WF4 en el hospedaje de flujos de trabajo.  
  
 [Guía básica de migración de WF: seguimiento del flujo de trabajo](/previous-versions/appfabric/ff383417(v=azure.10))  
 Proporciona una guía para rediseñar el código de seguimiento WF3 y la configuración mediante un código y una configuración de seguimiento de WF4 equivalentes.  
  
 [Guía de WF: servicios de flujo de trabajo](/previous-versions/appfabric/ff383417(v=azure.10))  
 Proporciona instrucciones paso a paso basadas en ejemplos para rediseñar flujos de trabajo que implementan los servicios web de Windows Communication Foundation (más conocidos como servicios de flujo de trabajo) creados en WF3 para usar WF4, para escenarios comunes en actividades estándar.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Statements.Interop>
