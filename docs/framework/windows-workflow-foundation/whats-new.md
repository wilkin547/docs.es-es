---
title: Novedades de Windows Workflow Foundation
description: Obtenga información sobre los cambios de Windows Workflow Foundation en .NET Framework 4. Los flujos de trabajo son más fáciles de crear, ejecutar y mantener.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
ms.openlocfilehash: d6a3cda7b9334ca4710ada5aa0848eb5be815b0a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293837"
---
# <a name="whats-new-in-windows-workflow-foundation"></a>Novedades de Windows Workflow Foundation

Windows Workflow Foundation (WF) en .NET Framework 4 cambia varios paradigmas de desarrollo de las versiones anteriores. Los flujos de trabajo son ahora más fáciles de crear, ejecutar, mantener e implementan un host de nuevas funciones. Para obtener más información sobre cómo migrar las aplicaciones de flujo de trabajo .NET Framework 3,0 y .NET Framework 3,5 para usar la versión más reciente, consulte la [Guía de migración](migration-guidance.md).

## <a name="workflow-activity-model"></a>Modelo de la actividad de flujo de trabajo

 La actividad es ahora la unidad base para crear un flujo de trabajo, en lugar de usar las clases <xref:System.Workflow.Activities.SequentialWorkflowActivity> o <xref:System.Workflow.Activities.StateMachineWorkflowActivity>. La clase <xref:System.Activities.Activity> proporciona la abstracción básica del comportamiento del flujo de trabajo. Los autores de actividad pueden implementar <xref:System.Activities.CodeActivity> para la funcionalidad de actividad personalizada básica o <xref:System.Activities.NativeActivity> para la funcionalidad de actividad personalizada que usa toda la riqueza del runtime. <xref:System.Activities.Activity> es una clase que usan los autores de actividad para expresar nuevos comportamientos de forma declarativa en términos de otros <xref:System.Activities.NativeActivity> <xref:System.Activities.CodeActivity> objetos,, <xref:System.Activities.AsyncCodeActivity> o <xref:System.Activities.DynamicActivity> , tanto si están desarrollados de forma personalizada como si están incluidos en la [biblioteca de actividades integrada](net-framework-4-5-built-in-activity-library.md).

## <a name="rich-composite-activity-options"></a>Opciones de actividad compuestas y enriquecidas

 <xref:System.Activities.Statements.Flowchart> es una nueva actividad eficaz de flujo de control que permite a los autores modelar bucles arbitrarios y bifurcaciones condicionales. <xref:System.Activities.Statements.Flowchart> proporciona un modelo de programación controlado por eventos que anteriormente solo se podía implementar con <xref:System.Workflow.Activities.StateMachineWorkflowActivity>. Los flujos de trabajo de procedimiento se benefician de las nuevas actividades de control de flujo que modelan las estructuras de control de flujo tradicionales, como <xref:System.Activities.Statements.TryCatch> y <xref:System.Activities.Statements.Switch%601>.

## <a name="expanded-built-in-activity-library"></a>Biblioteca de actividades integrada y expandida

 Las nuevas características de la biblioteca de actividades incluyen:

- Nuevas actividades de control de flujo: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> y <xref:System.Activities.Statements.ParallelForEach%601>.

- Actividades para manipular los datos de miembros, como <xref:System.Activities.Statements.Assign> y actividades de colección como <xref:System.Activities.Statements.AddToCollection%601>.

- Actividades para controlar las transacciones, como <xref:System.Activities.Statements.TransactionScope> y <xref:System.Activities.Statements.Compensate>.

- Nuevas actividades de mensajería como <xref:System.ServiceModel.Activities.SendContent> y <xref:System.ServiceModel.Activities.ReceiveReply>.

## <a name="explicit-activity-data-model"></a>Modelo de datos de actividad explícito

 .NET Framework 4 incluye nuevas opciones para almacenar o mover datos. Se pueden almacenar datos en una actividad usando <xref:System.Activities.Variable>. Al mover datos hacia dentro de una actividad y fuera de ella, los tipos de argumento especializados se usan para determinar la dirección en la que se están moviendo los datos. Estos tipos son <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> y <xref:System.Activities.OutArgument>. Para obtener más información, vea [modelo de datos de Windows Workflow Foundation](data-model.md).

## <a name="enhanced-hosting-persistence-and-tracking-options"></a>Hospedaje, persistencia y opciones de seguimiento mejoradas

 .NET Framework 4 contiene mejoras de persistencia como las siguientes:

- Hay más opciones para ejecutar los flujos de trabajo, incluidas <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> y <xref:System.Activities.WorkflowInvoker>.

- Se pueden conservar explícitamente los datos de estado del flujo de trabajo mediante la actividad <xref:System.Activities.Statements.Persist>.

- Un host puede conservar un <xref:System.Activities.ActivityInstance> sin descargarlo.

- Los flujos de trabajo pueden especificar zonas sin conservación mientras trabajan con datos que no se pueden conservar, de manera que la persistencia se posponga hasta que salga la zona sin conservación.

- Las transacciones se pueden fluir en un flujo de trabajo mediante <xref:System.Activities.Statements.TransactionScope>.

- El seguimiento puede llevarse a cabo de una forma más sencilla con <xref:System.Activities.Tracking.TrackingParticipant>.

- Se proporciona el seguimiento del registro de eventos del sistema mediante <xref:System.Activities.Tracking.EtwTrackingParticipant>.

- Actualmente, reanudar un flujo de trabajo pendiente se administra mediante un objeto <xref:System.Activities.Bookmark>.

## <a name="easier-ability-to-extend-wf-designer-experience"></a>Mejor capacidad para ampliar la experiencia de diseñador de WF

 El nuevo diseñador de WF se basa en Windows Presentation Foundation (WPF) y proporciona un modelo más sencillo para usar al volver a hospedar el diseñador de WF fuera de Visual Studio y también proporciona mecanismos más sencillos para crear diseñadores de actividad personalizados. Para obtener más información, vea [personalizar la experiencia de diseño de flujo de trabajo](customizing-the-workflow-design-experience.md).
