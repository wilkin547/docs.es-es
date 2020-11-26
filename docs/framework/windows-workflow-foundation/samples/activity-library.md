---
title: Biblioteca de actividades
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 1a0c289315d7181645573098916788f18493abb8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245715"
---
# <a name="activity-library"></a>Biblioteca de actividades

Esta sección contiene ejemplos que muestran las actividades personalizadas avanzadas en Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>En esta sección

 [Actividad personalizada SendMail](sendmail-custom-activity.md)  
 Muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo mediante SMTP para el uso dentro de una aplicación de flujo de trabajo.  
  
 [Throttled Parallel ForEach](throttled-parallel-foreach.md)  
 Muestra cómo la actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutarán.
  
 [Actividades de acceso a bases de datos](database-access-activities.md)  
 Muestra cómo crear actividades que permiten el acceso a las bases de datos para recuperar o modificar información y usar [ADO.net](../../data/adonet/index.md) para tener acceso a la base de datos.  
  
 [Actividad Externalized Policy en .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Muestra cómo la actividad ExternalizedPolicy4 permite ejecutar los Windows Workflow Foundation existentes en los objetos .NET Framework 3,5 (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> en Windows Workflow Foundation de [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4,5) directamente mediante el motor de reglas que se incluye en WF 3,5.
  
 [ForEach no genérico](non-generic-foreach.md)  
 Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ForEach%601>.  
  
 [ParallelForEach no genérico](non-generic-parallelforeach.md)  
 Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Get WorkflowInstanceId](get-workflowinstanceid.md)  
 Muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.
