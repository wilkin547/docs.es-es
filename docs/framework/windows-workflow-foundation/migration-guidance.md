---
title: Guía de migración
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: b9b90aedc06fb4a4564596d61aa0ac2dc4c6143f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733599"
---
# <a name="migration-guidance"></a>Guía de migración

En el .NET Framework 4, Microsoft está lanzando la segunda versión principal de Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] se lanzó en WinFX (esto incluía los tipos de System. Workflow. \* namespaces; ahora conocido como WF3) y se mejoró en .NET Framework 3,5. WF3 también forma parte de la .NET Framework 4, pero existe allí junto con la nueva tecnología de flujo de trabajo (los tipos de System. Activities. \* namespaces; denominados WF4). A la hora de plantearse cuándo adoptar WF4, es importante reconocer primero que controla el tiempo.

- WF3 es una parte totalmente compatible del .NET Framework 4.

- Las aplicaciones de WF3 se ejecutan en el .NET Framework 4 sin modificaciones y continúan siendo totalmente compatibles.

- Se pueden crear nuevas aplicaciones WF3 y las aplicaciones existentes se pueden editar en Visual Studio 2012 y son totalmente compatibles.

 Por lo tanto, la decisión de adoptar el .NET Framework 4 está desacoplada de la decisión de pasar a WF4 (System. Activities. \* ) de WF3 (System. Workflow. \* ). En este tema se proporcionan vínculos a la guía de migración de WF que proporciona información sobre cómo trabajar con WF3 y WF4.

## <a name="wf-migration-white-papers-and-cookbooks"></a>Notas del producto y guías de migración de WF

 El tema [información general sobre la migración de WF](/previous-versions/appfabric/ff383417(v=azure.10)) proporciona una amplia información general de la relación entre WF3 y WF4 y las estrategias de migración. Los temas de ayuda profundizan en asuntos específicos.

 [Información general sobre la migración de WF](/previous-versions/appfabric/ff383417(v=azure.10)) Describe la relación entre WF3 y WF4, así como las opciones que tiene como usuario o un posible usuario de la tecnología de flujo de trabajo en .NET Framework 4.

 [Migración de WF: procedimientos recomendados para el desarrollo de WF3](/previous-versions/appfabric/ff383417(v=azure.10)) Describe cómo diseñar artefactos de WF3 para que se puedan migrar más fácilmente a WF4.

 [Guía de WF: reglas](/previous-versions/appfabric/ff383417(v=azure.10)) Describe cómo incorporar las inversiones relacionadas con las reglas a las soluciones de .NET Framework 4.

 [Guía de WF: equipo de estado](/previous-versions/appfabric/ff383417(v=azure.10)) Describe el modelado del flujo de control de WF4 en ausencia de una actividad State-Machine.

 Tenga en cuenta que esta guía se aplica solamente a proyectos de flujo de trabajo que tienen como destino .NET Framework 4. Los flujos de trabajo de equipo de estado se agregaron en .NET Framework 4.0.1 con la versión de la actualización 1 de la plataforma y se incluyeron como parte de .NET Framework 4,5. Para obtener más información acerca de los flujos de trabajo de máquina de Estados en .NET Framework 4.0.1-4.0.3 y .NET Framework 4,5, consulte [actualización 4.0.1 para las características de Microsoft .NET Framework 4](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) y los [flujos de trabajo de máquina de Estados](state-machine-workflows.md).

 [Guía de migración de WF: actividades personalizadas](/previous-versions/appfabric/ff383417(v=azure.10)) Proporciona ejemplos e instrucciones para rediseñar actividades personalizadas de WF3 en WF4.

 [Guía de migración de WF: actividades personalizadas avanzadas](/previous-versions/appfabric/ff383417(v=azure.10)) Proporciona instrucciones para volver a diseñar actividades personalizadas de WF3 avanzadas que usan colas de WF3 y programar actividades secundarias como actividades personalizadas de WF4.

 [Guía de migración de WF: flujos de trabajo](/previous-versions/appfabric/ff383417(v=azure.10)) Proporciona ejemplos e instrucciones para rediseñar flujos de trabajo de WF3 en WF4.

 [Guía de migración de WF: hospedaje de flujo de trabajo](/previous-versions/appfabric/ff383417(v=azure.10)) Proporciona instrucciones para rediseñar el código de hospedaje de WF3 como código de hospedaje de WF4. El objetivo es tratar las diferencias clave entre WF3 Y WF4 en el hospedaje de flujos de trabajo.

 [Guía de migración de WF: seguimiento del flujo de trabajo](/previous-versions/appfabric/ff383417(v=azure.10)) Proporciona instrucciones para rediseñar el código de seguimiento de WF3 y la configuración mediante el código de seguimiento de WF4 y la configuración equivalentes.

 [Guía de WF: servicios de flujo de trabajo](/previous-versions/appfabric/ff383417(v=azure.10)) Proporciona instrucciones paso a paso orientadas a un ejemplo para rediseñar flujos de trabajo que implementan servicios Web de Windows Communication Foundation (WCF) (comúnmente denominados servicios de flujo de trabajo) creados en WF3 para usar WF4, para escenarios comunes para actividades integradas.

## <a name="see-also"></a>Consulte también

- <xref:System.Activities.Statements.Interop>
