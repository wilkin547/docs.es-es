---
title: "Excepciones, transacciones y compensaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "programar [WF], control de errores"
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Excepciones, transacciones y compensaci&#243;n
[!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona varios mecanismos diferentes para administrar las condiciones de error en tiempo de ejecución en flujos de trabajo.Los flujos de trabajo pueden usar una combinación de controladores de excepciones, transacciones, cancelación y compensación para administrar y recuperar sin contratiempos las condiciones de error.  
  
## En esta sección  
 [Excepciones](../../../docs/framework/windows-workflow-foundation//exceptions.md)  
 Muestra cómo usar la actividad <xref:System.Activities.Statements.TryCatch> para administrar las excepciones en un flujo de trabajo.  
  
 [Transacciones](../../../docs/framework/windows-workflow-foundation//workflow-transactions.md)  
 Muestra cómo usar la actividad <xref:System.Activities.Statements.TransactionScope> para utilizar excepciones en un flujo de trabajo.  
  
 [Compensación](../../../docs/framework/windows-workflow-foundation//compensation.md)  
 Describe la compensación en flujos de trabajo y muestra cómo usar actividades de compensación como <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> y <xref:System.Activities.Statements.Confirm>.  
  
 [Cancelación](../../../docs/framework/windows-workflow-foundation//modeling-cancellation-behavior-in-workflows.md)  
 Describe cómo realizar el control de la cancelación en flujos de trabajo utilizando actividades integradas así como actividades personalizadas.  
  
 [Depurar flujos de trabajo](../../../docs/framework/windows-workflow-foundation//debugging-workflows.md)  
 Describe cómo depurar los flujos de trabajo.