---
title: "How to: Handle Exceptions in Parallel Loops | Microsoft Docs"
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
  - "parallel loops, how to handle exceptions"
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Handle Exceptions in Parallel Loops
Las sobrecargas <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> no tienen ningún mecanismo especial para controlar las excepciones que puedan iniciarse.  En este sentido, se asemejan a bucles `for` y `foreach` normales \(`For` y `For Each` en Visual Basic\). Una excepción no controlada hace que el bucle finalice inmediatamente.  
  
 Cuando agregue su propia lógica de control de excepciones a los bucles paralelos, tenga en cuenta la posibilidad de que se inicien excepciones similares en varios subprocesos al mismo tiempo y la opción de que una excepción iniciada en un subproceso puede hacer que se inicie otra excepción en otro subproceso.  Puede controlar ambos casos ajustando todas las excepciones del bucle en <xref:System.AggregateException?displayProperty=fullName>.  En el ejemplo siguiente, se muestra un posible enfoque.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", en algunos casos, Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno.  Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en el siguiente ejemplo.  Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla «Solo mi código» en **Herramientas, Opciones, Depuración, General**.  
  
## Ejemplo  
 En este ejemplo, se detectan todas las excepciones y, a continuación, se ajusta en un <xref:System.AggregateException?displayProperty=fullName> que se produce.  El llamador puede decidir qué excepciones se deben administrar.  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## Vea también  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)