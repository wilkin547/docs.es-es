---
title: "Excepciones, transacciones y compensación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e83661ba66ca6a71f26c11172902d5bc602a2f6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="exceptions-transactions-and-compensation"></a>Excepciones, transacciones y compensación
[!INCLUDE[wf1](../../../includes/wf1-md.md)] proporciona varios mecanismos diferentes para administrar las condiciones de error en tiempo de ejecución en flujos de trabajo. Los flujos de trabajo pueden usar una combinación de controladores de excepciones, transacciones, cancelación y compensación para administrar y recuperar sin contratiempos las condiciones de error.  
  
## <a name="in-this-section"></a>En esta sección  
 [Excepciones](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 Muestra cómo usar la actividad <xref:System.Activities.Statements.TryCatch> para administrar las excepciones en un flujo de trabajo.  
  
 [Transacciones](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 Muestra cómo usar la actividad <xref:System.Activities.Statements.TransactionScope> para utilizar excepciones en un flujo de trabajo.  
  
 [Compensación](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 Describe la compensación en flujos de trabajo y muestra cómo usar actividades de compensación como <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate> y <xref:System.Activities.Statements.Confirm>.  
  
 [Cancelación](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 Describe cómo realizar el control de la cancelación en flujos de trabajo utilizando actividades integradas así como actividades personalizadas.  
  
 [Depuración de flujos de trabajo](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 Describe cómo depurar los flujos de trabajo.
