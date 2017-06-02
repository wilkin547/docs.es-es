---
title: "How to: Handle Exceptions in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to handle exceptions"
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Handle Exceptions in a PLINQ Query
En el primer ejemplo de este tema se muestra cómo controlar la excepción <xref:System.AggregateException?displayProperty=fullName> que se puede iniciar desde una consulta PLINQ cuando se ejecuta.  En el segundo ejemplo se muestra cómo incluir bloques try\-catch dentro de los delegados, lo más próximos posibles al punto donde se iniciará la excepción.  De esta manera, se pueden detectar en cuanto se producen y, posiblemente, continuar con la ejecución de la consulta.  Cuando las excepciones pueden propagarse de nuevo al subproceso de unión, es posible que una consulta continúe procesando algunos elementos después de que se haya producido la excepción.  
  
 En algunos casos, cuando PLINQ utiliza la ejecución secuencial y se produce una excepción, es posible que esta se propague directamente y no se encapsule en una excepción <xref:System.AggregateException>.  Además, las excepciones <xref:System.Threading.ThreadAbortException> siempre se propagan directamente.  
  
> [!NOTE]
>  Cuando está habilitada la opción "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno.  Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en los ejemplos siguientes.  Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" bajo **Herramientas, Opciones, Depuración, General**.  
>   
>  Este ejemplo está diseñado para mostrar el uso y podría no ejecutarse más rápidamente que la consulta secuencial equivalente de LINQ to Objects.  Para obtener más información sobre la aceleración, vea [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Ejemplo  
 En este ejemplo se muestra cómo colocar los bloques try\-catch alrededor del código que ejecuta la consulta para detectar las excepciones <xref:System.AggregateException?displayProperty=fullName>s que se produzcan.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 En este ejemplo, la consulta no puede continuar una vez producida la excepción.  Cuando el código de aplicación detecta la excepción, PLINQ ya ha detenido la consulta en todos los subprocesos.  
  
## Ejemplo  
 En el siguiente ejemplo se muestra cómo colocar un bloque try\-catch en un delegado para permitir que se detecte una excepción y que continúe la ejecución de la consulta.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## Compilar el código  
  
-   Para compilar y ejecutar estos ejemplos, cópielos en el ejemplo de Ejemplo de datos de PLINQ y llame al método desde Main.  
  
## Programación eficaz  
 No detecte ninguna excepción a menos que sepa cómo controlarla de forma que no dañe el estado del programa.  
  
## Vea también  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)