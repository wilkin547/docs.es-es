---
title: "Usar una actividad personalizada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Usar una actividad personalizada
Las actividades que se derivan de <xref:System.Activities.Activity> o sus subclases pueden componerse en flujos de trabajo de mayor tamaño o crearse directamente en el código.En este tema se describe cómo usar las actividades personalizadas en flujos de trabajo creados en el código o en el diseñador.  
  
> [!NOTE]
>  Las actividades personalizadas se pueden usar en el mismo proyecto en el que se definen, siempre y cuando la actividad personalizada y la actividad que lo usa estén compiladas \(es decir,cargadas mediante un tipo de creación de instancia generado por el proceso de compilación\). Si la actividad de referencia se carga de forma dinámica \(por ejemplo,mediante ActivityXAMLServices\), el ensamblado al que se hace referencia debe encontrarse en un proyecto diferente, o será necesario editar manualmente el XAML generado por el diseñador para habilitarlo.  
  
#### Usar una actividad personalizada en un proyecto de flujo de trabajo  
  
1.  Agregue una referencia del proyecto host al proyecto de biblioteca de actividades que contiene la actividad personalizada.  
  
2.  Compile la solución.  
  
3.  Para usar la actividad personalizada en el diseñador, busque la actividad personalizada en el cuadro de herramientas y arrástrela sobre la superficie del diseñador.  
  
4.  Para usar la actividad personalizada en código, agregue una instrucción Using que haga referencia al proyecto de actividad personalizada y pase una nueva instancia de la actividad a <xref:System.Activities.WorkflowInvoker.Invoke%2A>.