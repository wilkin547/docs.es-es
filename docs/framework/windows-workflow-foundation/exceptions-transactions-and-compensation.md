---
title: Excepciones, transacciones y compensación
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 2d8574c0f0f6bd3f66214367c1ed15292adc24a9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280252"
---
# <a name="exceptions-transactions-and-compensation"></a>Excepciones, transacciones y compensación

[!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona varios mecanismos diferentes para administrar las condiciones de error en tiempo de ejecución en flujos de trabajo. Los flujos de trabajo pueden usar una combinación de controladores de excepciones, transacciones, cancelación y compensación para administrar y recuperar sin contratiempos las condiciones de error.  
  
## <a name="in-this-section"></a>En esta sección  

 [Excepciones](exceptions.md)  
 Muestra cómo usar la actividad <xref:System.Activities.Statements.TryCatch> para administrar las excepciones en un flujo de trabajo.  
  
 [Transacciones](workflow-transactions.md)  
 Muestra cómo usar la actividad <xref:System.Activities.Statements.TransactionScope> para utilizar excepciones en un flujo de trabajo.  
  
 [Compensación](compensation.md)  
 Describe la compensación en flujos de trabajo y muestra cómo usar actividades de compensación como <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> y <xref:System.Activities.Statements.Confirm>.  
  
 [Cancelación](modeling-cancellation-behavior-in-workflows.md)  
 Describe cómo realizar el control de la cancelación en flujos de trabajo utilizando actividades integradas así como actividades personalizadas.  
  
 [Depurar flujos de trabajo](debugging-workflows.md)  
 Describe cómo depurar los flujos de trabajo.
