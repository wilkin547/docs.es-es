---
title: Guía de migración
description: 'Más información acerca de: Guía de migración'
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 83c6af4d8eed396501aafc568de8e64d30ae7cfe
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104866"
---
# <a name="migration-guidance"></a>Guía de migración

En .NET Framework 4, Microsoft lanzó la segunda versión principal de Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] se lanzó en WinFX (esto incluía los tipos de System. Workflow. \* namespaces; ahora conocido como WF3) y se mejoró en .NET Framework 3,5. WF3 también forma parte de .NET Framework 4, pero existe allí junto con la nueva tecnología de flujo de trabajo (los tipos de System. Activities. \* namespaces; denominados WF4). A la hora de plantearse cuándo adoptar WF4, es importante reconocer primero que controla el tiempo.

- WF3 es una parte totalmente compatible de .NET Framework 4.

- Las aplicaciones de WF3 se ejecutan en .NET Framework 4 sin modificaciones y continúan siendo totalmente compatibles.

- Se pueden crear nuevas aplicaciones WF3 y las aplicaciones existentes se pueden editar en Visual Studio 2012 y son totalmente compatibles.

Por lo tanto, la decisión de adoptar .NET Framework 4 está desacoplada de la decisión de pasar a WF4 (System. Activities. \* ) de WF3 (System. Workflow. \* ). En este tema se proporcionan vínculos a la guía de migración de WF que proporciona información sobre cómo trabajar con WF3 y WF4.

## <a name="wf-migration-white-papers-and-cookbooks"></a>Notas del producto y guías de migración de WF

 [Información general sobre la migración de WF](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Overview.docx)\
 Describe la relación entre WF3 y WF4, así como las opciones que tiene como usuario o un posible usuario de la tecnología de flujo de trabajo en .NET Framework 4.

 [Migración de WF: procedimientos recomendados para el desarrollo de WF3](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Best%20Practices.docx)\
 Describe cómo diseñar los artefactos de WF3 de modo que se puedan migrar más fácilmente a WF4.

 [Guía de WF: reglas](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20Rules%20Guidance.docx)\
 Describe cómo incorporar las inversiones relacionadas con las reglas a las soluciones de .NET Framework 4.

 [Guía de WF: equipo de estado](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20State%20Machine%20Guidance.doc) Describe el modelado del flujo de control de WF4 en ausencia de una actividad State-Machine. Esta guía solo se aplica a los proyectos de flujo de trabajo que tienen como destino .NET Framework 4. Los flujos de trabajo de equipo de estado se agregaron en .NET Framework 4.0.1 con la versión de la actualización 1 de la plataforma y se incluyeron como parte de .NET Framework 4,5. Para obtener más información acerca de los flujos de trabajo de máquina de Estados en .NET Framework 4.0.1-4.0.3 y .NET Framework 4,5, consulte [actualización 4.0.1 para las características de Microsoft .NET Framework 4](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) y los [flujos de trabajo de máquina de Estados](state-machine-workflows.md).

 [Guía de migración de WF: actividades personalizadas](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Custom%20Activities.docx)\
 Proporciona ejemplos e instrucciones para rediseñar actividades personalizadas de WF3 en WF4.

 [Guía de migración de WF: actividades personalizadas avanzadas](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Advanced%20Custom%20Activities.docx)\
 Proporciona una guía para rediseñar actividades personalizadas WF3 avanzadas que usan colas WF3 y programan actividades secundarias como actividades personalizadas de WF4.
%20 [Guía de migración de WF: flujos de trabajo](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflows.docx)\
 Proporciona ejemplos e instrucciones para rediseñar flujos de trabajo de WF3 en WF4.

 [Guía de migración de WF: hospedaje de flujo de trabajo](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflow%20Hosting.docx)\
 Proporciona una guía para rediseñar el código de hospedaje de WF3 como un código de hospedaje WF4. El objetivo es tratar las diferencias clave entre WF3 Y WF4 en el hospedaje de flujos de trabajo.

 [Guía de migración de WF: seguimiento del flujo de trabajo](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflow%20Tracking.docx)\
 Proporciona una guía para rediseñar el código de seguimiento WF3 y la configuración mediante un código y una configuración de seguimiento de WF4 equivalentes.

 [Guía de WF: servicios de flujo de trabajo](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20Workflow%20Services%20Guidance.docx)\
 Proporciona instrucciones paso a paso basadas en ejemplos para rediseñar flujos de trabajo que implementan los servicios web de Windows Communication Foundation (más conocidos como servicios de flujo de trabajo) creados en WF3 para usar WF4, para escenarios comunes en actividades estándar.

## <a name="see-also"></a>Consulte también

- <xref:System.Activities.Statements.Interop>
