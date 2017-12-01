---
title: "Cómo: Controlar excepciones en una consulta PLINQ"
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Cómo: Controlar excepciones en una consulta PLINQ
El primer ejemplo de este tema muestra cómo controlar la <xref:System.AggregateException?displayProperty=nameWithType> que puede iniciar desde una consulta PLINQ cuando se ejecuta. El segundo ejemplo muestra cómo colocar bloques try-catch dentro de los delegados, lo más cercana posible a donde se producirá la excepción. De este modo, se pueden detectar en cuanto se producen y que continúe la ejecución de la consulta. Cuando las excepciones pueden propagarse de nuevo al subproceso de unión, es posible que una consulta continúe procesando algunos elementos después de que se haya producido la excepción.  
  
 En algunos casos cuando PLINQ vuelve a la ejecución secuencial y se produce una excepción, la excepción puede ser propagan directamente y no se ajusta en un <xref:System.AggregateException>. Además, <xref:System.Threading.ThreadAbortException>siempre se propagan directamente.  
  
> [!NOTE]
>  Cuando se habilita "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y mostrar un mensaje de error "excepción no controlada por código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla «Solo mi código» en **herramientas, opciones, depuración, General**.  
>   
>  La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para obtener más información acerca de la velocidad, consulte [Introducción a la velocidad en PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra cómo colocar los bloques try-catch alrededor del código que se ejecuta la consulta para detectar cualquier <xref:System.AggregateException?displayProperty=nameWithType>s que se producen.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 En este ejemplo, la consulta no puede continuar después de que se produce la excepción. En el momento en que el código de aplicación detecta la excepción, PLINQ ya ha detenido la consulta en todos los subprocesos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo colocar un bloque try-catch en un delegado para que sea posible detectar una excepción y continuar con la ejecución de la consulta.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Para compilar y ejecutar estos ejemplos, cópielos en el ejemplo de muestra de datos de PLINQ y llame al método desde Main.  
  
## <a name="robust-programming"></a>Programación sólida  
 No se detecta una excepción a menos que sepa cómo controlarla para que no se dañan el estado del programa.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
