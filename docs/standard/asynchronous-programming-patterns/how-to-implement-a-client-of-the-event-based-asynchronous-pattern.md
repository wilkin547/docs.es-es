---
title: "How to: Implement a Client of the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Implement a Client of the Event-based Asynchronous Pattern
El siguiente ejemplo de código muestra cómo utilizar un componente conforme a [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  El formulario de este ejemplo utiliza el componente  `PrimeNumberCalculator` , que se describe en [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 Cuando ejecute un proyecto que utilice este ejemplo, verá un formulario de cálculo de números primos \("Prime Number Calculator"\) con una cuadrícula y dos botones: **Iniciar tarea nueva** y **Cancelar**.  Puede hacer clic en el botón **Iniciar tarea nueva** varias veces seguidas; por cada clic, una operación asincrónica iniciará un cálculo para determinar si un número de prueba generado aleatoriamente es primo.  El formulario mostrará periódicamente el progreso y los resultados incrementales.  A cada operación se le asigna un identificador de tarea único.  El resultado del cálculo se muestra en la columna **Resultado**; si el número de prueba no es primo, se le asigna la etiqueta **Compuesto** y se muestra su primer divisor.  
  
 Cualquier operación pendiente puede cancelarse con el botón **Cancelar**.  Se pueden realizar selecciones múltiples.  
  
> [!NOTE]
>  La mayoría de los números no serán primos.  Si tras realizar varias operaciones no encuentra ningún número primo, simplemente inicie más tareas; acabará encontrando algún número primo.  
  
## Ejemplo  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## Vea también  
 <xref:System.ComponentModel.AsyncOperation>   
 <xref:System.ComponentModel.AsyncOperationManager>   
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>