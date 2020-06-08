---
title: Procedimiento para cancelar una consulta PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
ms.openlocfilehash: 09405a8a9f5d96d80454bcc98cbf29db54df6725
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288217"
---
# <a name="how-to-cancel-a-plinq-query"></a>Procedimiento para cancelar una consulta PLINQ
En los siguientes ejemplos se muestran dos formas de cancelar una consulta PLINQ. El primer ejemplo muestra cómo cancelar una consulta que se compone principalmente de un cruce seguro de datos. El segundo ejemplo muestra cómo cancelar una consulta que contiene una función de usuario que es cara desde el punto de vista computacional.

> [!NOTE]
> Cuando está habilitada la opción "Solo mi código", Visual Studio se interrumpe en la línea que produce la excepción y muestra el mensaje de error "Excepción no controlada por el código de usuario". Este error es benigno. Puede presionar F5 para continuar y ver el comportamiento de control de excepciones que se muestra en estos ejemplos. Para evitar que Visual Studio se interrumpa con el primer error, desactive la casilla "Solo mi código" en **Herramientas, Opciones, Depurar, General**.
>
> La finalidad de este ejemplo es mostrar el uso, y puede que su ejecución no sea tan rápida como la de la consulta LINQ to Objects secuencial equivalente. Para más información sobre la velocidad, vea [Introducción a la velocidad en PLINQ](understanding-speedup-in-plinq.md).

## <a name="example"></a>Ejemplo

[!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
[!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]

El marco PLINQ no revierte una clase <xref:System.OperationCanceledException> única en <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> debe controlarse en un bloque de filtrado independiente. Si uno o varios de los delegados de usuario produce una clase OperationCanceledException(externalCT) (mediante el uso de una referencia externa <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), pero ninguna otra excepción, y la consulta se ha definido como `AsParallel().WithCancellation(externalCT)`, a continuación, PLINQ emitirá una única clase <xref:System.OperationCanceledException> (externalCT) en lugar de una clase <xref:System.AggregateException?displayProperty=nameWithType>. Sin embargo, si un usuario delegado inicia una clase <xref:System.OperationCanceledException> y otro delegado inicia otro tipo de excepción, ambas excepciones se propagarán a <xref:System.AggregateException>.

Las instrucciones generales sobre la cancelación son las siguientes:

1. Si realiza la cancelación de un delegado de usuario, debe informar a PLINQ sobre la clase externa <xref:System.Threading.CancellationToken> e iniciar <xref:System.OperationCanceledException> (externalCT).

2. Si se produce la cancelación y no se inicia ninguna otra excepción, controle un elemento <xref:System.OperationCanceledException> en lugar de uno <xref:System.AggregateException>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo controlar la cancelación cuando se tiene una función cara desde el punto de vista computacional en el código de usuario.

[!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
[!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]

Al controlar la cancelación en el código de usuario, no tiene que usar <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> en la definición de consulta. Sin embargo, se recomienda el uso de <xref:System.Linq.ParallelEnumerable.WithCancellation%2A>, porque <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> no tiene ningún efecto en el rendimiento de las consultas y permite que los operadores de consulta y el código de usuario controlen la cancelación.

Con el fin de garantizar la capacidad de respuesta del sistema, se recomienda que compruebe la cancelación una vez por cada milisegundo; sin embargo, cualquier período que transcurre hasta diez milisegundos se considera aceptable. Esta frecuencia no debe tener un impacto negativo en el rendimiento del código.

Cuando se elimina un enumerador, por ejemplo cuando el código desencadena un bucle foreach (For Each en Visual Basic) que está iterando en los resultados de la consulta, se cancela la consulta, pero no se inicia ninguna excepción.

## <a name="see-also"></a>Vea también

- <xref:System.Linq.ParallelEnumerable>
- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
- [Cancelación en subprocesos administrados](../threading/cancellation-in-managed-threads.md)
