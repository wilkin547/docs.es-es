---
title: 'Cómo: Controlar excepciones en una consulta PLINQ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
ms.openlocfilehash: aa583d8c31381d23e22f271db3d42d35e1fa14b2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826949"
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Cómo: Controlar excepciones en una consulta PLINQ

El primer ejemplo de este tema muestra cómo controlar la clase <xref:System.AggregateException?displayProperty=nameWithType> que se puede iniciar desde una consulta PLINQ cuando se ejecuta. El segundo ejemplo muestra cómo colocar bloques try-catch dentro de los delegados, lo más cerca posible de donde se producirá la excepción. De este modo, se pueden detectar en cuanto se producen y posiblemente continuar con la ejecución de la consulta. Cuando las excepciones pueden propagarse de nuevo al subproceso de unión, es posible que una consulta continúe procesando algunos elementos después de que se haya producido la excepción.

En algunos casos, cuando PLINQ vuelve a realizar la ejecución por secuencias y cuando se produce una excepción, esta puede propagarse directamente y no ajustarse en una excepción <xref:System.AggregateException>. Además, las excepciones <xref:System.Threading.ThreadAbortException> siempre se propagan directamente.

> [!NOTE]
> Cuando está habilitada la opción "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.
>
> La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).

## <a name="example"></a>Ejemplo

Este ejemplo muestra cómo colocar los bloques try-catch alrededor del código que ejecuta la consulta para detectar cualquier excepción <xref:System.AggregateException?displayProperty=nameWithType> que se produzca.

[!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
[!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]

En este ejemplo, la consulta no puede continuar después de que se produce la excepción. En el momento en que el código de la aplicación detecta la excepción, PLINQ ya ha detenido la consulta en todos los subprocesos.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo colocar un bloque try-catch en un delegado para que sea posible detectar una excepción y continuar con la ejecución de la consulta.

[!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
[!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]

## <a name="compiling-the-code"></a>Compilar el código

- Para compilar y ejecutar estos ejemplos, cópielos en el ejemplo de datos de PLINQ y llame al método desde Main.

## <a name="robust-programming"></a>Programación sólida

No se detecta ninguna excepción a menos que sepa cómo controlarla para que no se dañe el estado del programa.

## <a name="see-also"></a>Vea también

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
