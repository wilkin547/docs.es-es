---
title: "How to: Cancel a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to cancel"
  - "cancellation, PLINQ"
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a PLINQ Query
En los siguientes ejemplos se muestran dos maneras de cancelar una consulta PLINQ.  En el primer ejemplo se muestra cómo cancelar una consulta que consta principalmente de recorridos de datos.  En el segundo ejemplo se muestra cómo cancelar una consulta que contiene una función de usuario que resulta cara en los cálculos.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno.  Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en los ejemplos siguientes.  Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" bajo **Herramientas, Opciones, Depuración, General**.  
>   
>  Este ejemplo está diseñado para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 El marco de PLINQ no incluye una única excepción <xref:System.OperationCanceledException> en <xref:System.AggregateException?displayProperty=fullName>; <xref:System.OperationCanceledException> se debe controlar en un bloque catch independiente.  Si uno o más delegados de usuario inician una excepción OperationCanceledException\(externalCT\) \(mediante una estructura <xref:System.Threading.CancellationToken?displayProperty=fullName> externa\) pero ninguna otra excepción, y la consulta se definió como `AsParallel().WithCancellation(externalCT)`, PLINQ emitirá una única excepción <xref:System.OperationCanceledException> \(externalCT\) en lugar de <xref:System.AggregateException?displayProperty=fullName>.  Sin embargo, si un delegado de usuario inicia una excepción <xref:System.OperationCanceledException> y otro delegado inicia otro tipo de excepción, ambas excepciones se incluyen en <xref:System.AggregateException>.  
  
 A continuación se proporciona una orientación general sobre la cancelación:  
  
1.  Si realiza una cancelación del delegado de usuario, debería informar a PLINQ sobre la estructura <xref:System.Threading.CancellationToken> externa e iniciar una excepción <xref:System.OperationCanceledException> \(externalCT\).  
  
2.  Si se produce la cancelación y no se inicia ninguna otra excepción, debería controlar una clase <xref:System.OperationCanceledException> en lugar de <xref:System.AggregateException>.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo controlar la cancelación cuando se cuenta con una función cara en cálculos en el código de usuario.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 Al controlar la cancelación en el código de usuario, no es necesario usar <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> en la definición de la consulta.  Sin embargo, recomendamos usarlo ya que <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> no tiene ningún efecto en el rendimiento de la consulta y permite controlar la cancelación con operadores de consulta y con el código de usuario.  
  
 Para garantizar la capacidad de respuesta del sistema, se recomienda comprobar la cancelación alrededor de una vez por milisegundo; también se considera aceptable, sin embargo, un período máximo de 10 milisegundos.  Esta frecuencia no tiene por qué tener un impacto negativo en el rendimiento del código.  
  
 Cuando se elimina un enumerador, por ejemplo cuando el código sale de un bucle foreach \(For Each en Visual Basic\) que está iterando en los resultados de la consulta, la consulta se cancela pero no se inicia ninguna excepción.  
  
## Vea también  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)