---
title: Biblioteca de actividades
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61909186"
---
# <a name="activity-library"></a>Biblioteca de actividades
Esta sección contiene ejemplos que muestran las actividades personalizadas avanzadas en Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>En esta sección

 [Actividad personalizada SendMail](sendmail-custom-activity.md)  
 Muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo mediante SMTP para el uso dentro de una aplicación de flujo de trabajo.  
  
 [Throttled Parallel ForEach](throttled-parallel-foreach.md)  
 Muestra cómo la actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutarán.
  
 [Actividades de acceso a bases de datos](database-access-activities.md)  
 Muestra cómo crear actividades que permiten tener acceso a las bases de datos para recuperar o modificar información y usar [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) para tener acceso a la base de datos.  
  
 [Actividad Externalized Policy en .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Muestra cómo la actividad ExternalizedPolicy4 permite ejecutar Windows Workflow Foundation existente en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> objetos de Windows Workflow Foundation en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) directamente utilizando el motor de reglas que es se distribuye con WF 3.5. 
  
 [ForEach no genérico](non-generic-foreach.md)  
 Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ForEach%601>.  
  
 [ParallelForEach no genérico](non-generic-parallelforeach.md)  
 Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Get WorkflowInstanceId](get-workflowinstanceid.md)  
 Muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.
