---
title: "Flujos de trabajo de procedimiento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Flujos de trabajo de procedimiento
Los flujos de trabajo de procedimiento usan métodos de control de flujo similares a los que se encuentren en lenguajes de procedimiento.Estas construcciones incluyen `While` y `If`.Estos flujos de trabajo se pueden crear libremente con otras actividades de control de flujo como <xref:System.Activities.Statements.Flowchart> y <xref:System.Activities.Statements.Sequence>.  
  
## Controlar el flujo de ejecución  
 La biblioteca de actividades del flujo de trabajo tiene actividades para modelar la mayoría de los métodos de control de flujo usados en lenguajes de procedimientos.Entre otros podemos destacar:  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 Para usar las actividades de control de flujo, arrástrelas desde el cuadro de herramientas **Actividad** y colóquelas en una actividad compuesta dentro de la ventana de diseñador.  
  
> [!NOTE]
>  Si se usa [!INCLUDE[dublin](../../../includes/dublin-md.md)] para hospedar flujos de trabajo en una granja de servidores web, AppFabric moverá instancias entre diferentes servidores de AppFabric.Esto necesita que los recursos se puedan compartir entre todos los nodos.Ninguna de las actividades de flujo de trabajo predeterminadas de .NET 4 contiene ninguna operación que tenga acceso a recursos locales.Puesto que AppFabric no ofrece ningún mecanismo para marcar un flujo de trabajo como inamovible, un desarrollador no debe crear actividades personalizadas que produzcan errores cuando se mueva un flujo de trabajo.  
  
## Vea también  
 [Flujos de trabajo del diagrama de flujo](../../../docs/framework/windows-workflow-foundation//flowchart-workflows.md)