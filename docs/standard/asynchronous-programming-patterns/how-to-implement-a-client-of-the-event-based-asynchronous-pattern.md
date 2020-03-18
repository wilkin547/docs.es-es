---
title: 'Cómo: Implementar un cliente en un modelo asincrónico basado en eventos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 50aa36d2caf774638ad20323813f0de3703aab2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "69950716"
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a>Cómo: Implementar un cliente en un modelo asincrónico basado en eventos
En el ejemplo de código siguiente se muestra cómo utilizar un componente que se adhiera a la [Información general sobre el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md). En el formulario de este ejemplo se usa el componente `PrimeNumberCalculator` descrito en [Implementar un componente que admita el modelo asincrónico basado en eventos](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Cuando se ejecuta un proyecto que usa este ejemplo, verá un formulario "Prime Number Calculator" (Calculadora de número primo) con una cuadrícula y dos botones: **Start New Task** (Iniciar nueva tarea) y **Cancel** (Cancelar). Puede hacer clic en el botón **Start New Task** (Iniciar nueva tarea) varias veces seguidas, y por cada clic, una operación asincrónica iniciará un cálculo para determinar si un número de prueba generado aleatoriamente es primo. El formulario mostrará periódicamente el progreso y los resultados incrementales. A cada operación se le asigna un identificador de tarea único. El resultado del cálculo se muestra en la columna **Result** (Resultado); si el número de prueba no es primo, se etiqueta como **Composite** (Compuesto) y se muestra su primer divisor.  
  
 Cualquier operación pendiente puede cancelarse con el botón **Cancel** (Cancelar). Se pueden realizar selecciones múltiples.  
  
> [!NOTE]
> La mayoría de los números no serán primos. Si no ha encontrado un número primo tras realizar varias operaciones, simplemente inicie más tareas y, finalmente, encontrará algunos números primos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.AsyncOperation>
- <xref:System.ComponentModel.AsyncOperationManager>
- <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>
