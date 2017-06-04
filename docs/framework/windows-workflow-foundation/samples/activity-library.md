---
title: "Biblioteca de actividades | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Biblioteca de actividades
Esta sección contiene ejemplos que muestran las actividades personalizadas avanzadas en [!INCLUDE[wf](../../../../includes/wf-md.md)].  
  
## En esta sección  
 [Actividad Policy en .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md)  
 Muestra cómo la actividad Policy4 permite utilizar objetos <xref:System.Workflow.Activities.Rules.RuleSet> de [!INCLUDE[wf2](../../../../includes/wf2-md.md)] en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]\(WF 3.5\) directamente en [!INCLUDE[wf2](../../../../includes/wf2-md.md)] en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF 4.5\) utilizando el motor de reglas que se distribuye con WF 3.5.  
  
 [Actividad personalizada para cambiar en un intervalo de valores](../../../../docs/framework/windows-workflow-foundation/samples/custom-activity-to-switch-on-a-range-of-values.md)  
 Muestra cómo crear una actividad personalizada que amplía el uso de <xref:System.Activities.Statements.Switch%601>.  
  
 [Actividad de LINQ to Objects](../../../../docs/framework/windows-workflow-foundation/samples/linq-to-objects-activity.md)  
 Muestra cómo crear una actividad para utilizar LINQ to Objects para consultar elementos de una colección.  
  
 [LINQ to SQL](../../../../docs/framework/windows-workflow-foundation/samples/linq-to-sql-sample.md)  
 Muestra cómo crear una actividad para utilizar las entidades de consulta de LINQ to SQL de las tablas en bases de datos de SQL Server.  
  
 [Uso de la actividad InvokePowerShell](../../../../docs/framework/windows-workflow-foundation/samples/using-the-invokepowershell-activity.md)  
 Muestra cómo invocar comandos de Windows PowerShell mediante la actividad InvokePowerShell.  
  
 [Actividad RangeEnumeration](../../../../docs/framework/windows-workflow-foundation/samples/rangeenumeration-activity.md)  
 Muestra cómo crear una actividad personalizada que recorre en iteración una colección de números.  
  
 [Actividades de expresión normales](../../../../docs/framework/windows-workflow-foundation/samples/regular-expression-activities.md)  
 Muestra cómo crear un conjunto de actividades que exponen la funcionalidad de expresión regular del espacio de nombres <xref:System.Text.RegularExpressions>.  
  
 [Actividad personalizada SendMail](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 Muestra cómo crear una actividad personalizada que deriva de <xref:System.Activities.AsyncCodeActivity> para enviar correo usando SMTP para el uso dentro de una aplicación de flujo de trabajo.  
  
 [Actividad For](../../../../docs/framework/windows-workflow-foundation/samples/for-activity.md)  
 Muestra cómo compilar una actividad personalizada que hereda de <xref:System.Activities.NativeActivity> y la utiliza en un flujo de trabajo para recorrer en iteración un intervalo de valores.  
  
 [Actividad Wait For Input](../../../../docs/framework/windows-workflow-foundation/samples/wait-for-input-activity.md)  
 Muestra cómo crear marcadores con nombre en un flujo de trabajo.  
  
 [Throttled Parallel ForEach](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 Muestra cómo la actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutarán.  
  
 [Actividades de entidad](../../../../docs/framework/windows-workflow-foundation/samples/entity-activities.md)  
 Muestra cómo utilizar ADO.NET Entity Framework con [!INCLUDE[wf2](../../../../includes/wf2-md.md)] para simplificar el acceso a datos.  
  
 [Actividades de acceso a bases de datos](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 Muestra cómo crear actividades que permiten tener acceso a las bases de datos para recuperar o modificar información y cómo usar [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081) para tener acceso a la base de datos.  
  
 [Actividad CommentOut](../../../../docs/framework/windows-workflow-foundation/samples/commentout-activity.md)  
 Muestra cómo escribir una actividad personalizada que quita otras actividades de la ruta de acceso de ejecución, marcándolas como comentario.  
  
 [Actividad Externalized Policy en .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 Muestra cómo la actividad ExternalizedPolicy4 permite ejecutar objetos <xref:System.Workflow.Activities.Rules.RuleSet> de [!INCLUDE[wf2](../../../../includes/wf2-md.md)] en [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] \(WF 3.5\) directamente en [!INCLUDE[wf2](../../../../includes/wf2-md.md)] en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF 4.5\) utilizando el motor de reglas que se distribuye con WF 3.5.  
  
 [Actividad NoPersistScope](../../../../docs/framework/windows-workflow-foundation/samples/nopersistscope-activity.md)  
 Muestra cómo manipular un estado no serializable y descartable dentro de un flujo de trabajo.  
  
 [ForEach no genérico](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ForEach%601>.  
  
 [ParallelForEach no genérico](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 Muestra cómo crear una versión no genérica de la actividad <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Get WorkflowInstanceId](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 Muestra cómo utilizar la actividad personalizada `GetWorkflowInstanceId` para devolver el identificador de la instancia de flujo de trabajo.