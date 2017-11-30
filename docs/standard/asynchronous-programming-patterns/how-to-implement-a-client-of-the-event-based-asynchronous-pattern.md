---
title: "Cómo: Implementar un cliente en un modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Cómo: Implementar un cliente en un modelo asincrónico basado en eventos
En el ejemplo de código siguiente se muestra cómo utilizar un componente que se adhiera a la [introducción de patrón asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). El formulario en este ejemplo usa el `PrimeNumberCalculator` componente se describe en [Cómo: implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Cuando se ejecuta un proyecto que se usa en este ejemplo, verá un formulario de "Calculadora de número primo" con una cuadrícula y dos botones: **Iniciar nueva tarea** y **cancelar**. Puede hacer clic en el **Iniciar nueva tarea** botón varias veces seguidas, y por cada clic, una operación asincrónica iniciará un cálculo para determinar si un número generado aleatoriamente prueba es primo. El formulario mostrará periódicamente el progreso y resultados incrementales. Cada operación se le asigna un identificador de tarea único. El resultado del cálculo se muestra en el **resultado** columna; si el número de prueba no es primo, se etiqueta como **compuesto,** y se muestra su primer divisor.  
  
 Cualquier operación pendiente puede cancelarse con el **cancelar** botón. Se pueden realizar selecciones múltiples.  
  
> [!NOTE]
>  Casi todos los números no serán primos. Si no ha encontrado un número primo tras realizar varias operaciones, simplemente inicie más tareas y, finalmente, encontrará algunos números primos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
