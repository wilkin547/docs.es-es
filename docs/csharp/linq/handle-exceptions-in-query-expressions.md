---
title: Controlar excepciones en expresiones de consulta (LINQ en C#)
description: Obtenga información sobre cómo controlar excepciones en expresiones de consulta de LINQ en C#.
ms.date: 12/01/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: f900669412026e69598d3939c51ff8208b51b7ec
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857507"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="8adae-103">Controlar excepciones en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="8adae-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="8adae-104">Es posible llamar a cualquier método en el contexto de una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="8adae-105">Pero se recomienda evitar llamar a cualquier método en una expresión de consulta que pueda crear un efecto secundario, como modificar el contenido del origen de datos o producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="8adae-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="8adae-106">En este ejemplo se muestra cómo evitar que se produzcan excepciones al llamar a métodos en una expresión de consulta sin infringir las instrucciones generales de .NET sobre el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="8adae-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="8adae-107">En esas instrucciones se indica que es aceptable detectar una excepción concreta cuando se comprende por qué se produce en un contexto determinado.</span><span class="sxs-lookup"><span data-stu-id="8adae-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="8adae-108">Para obtener más información, vea [Procedimientos recomendados para excepciones](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="8adae-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="8adae-109">En el último ejemplo se muestra cómo controlar los casos en los que se debe producir una excepción durante la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="8adae-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8adae-110">Example</span></span>

<span data-ttu-id="8adae-111">En el ejemplo siguiente se muestra cómo mover código de control de excepciones fuera de una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="8adae-112">Esto solo es posible cuando el método no depende de ninguna variable local de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="8adae-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8adae-113">Example</span></span>

<span data-ttu-id="8adae-114">En algunos casos, la mejor respuesta a una excepción que se produce dentro de una consulta podría ser detener la ejecución de la consulta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="8adae-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="8adae-115">En el ejemplo siguiente se muestra cómo controlar las excepciones que pueden producirse desde el cuerpo de una consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="8adae-116">Supongamos que `SomeMethodThatMightThrow` puede producir una excepción que requiere que se detenga la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="8adae-117">Tenga en cuenta que el bloque `try` encierra el bucle `foreach` y no la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="8adae-118">Esto es porque el bucle `foreach` es el punto en el que se ejecuta realmente la consulta.</span><span class="sxs-lookup"><span data-stu-id="8adae-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="8adae-119">Para obtener más información, vea [Introducción a las consultas LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="8adae-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="8adae-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8adae-120">See also</span></span>

- [<span data-ttu-id="8adae-121">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="8adae-121">Language Integrated Query (LINQ)</span></span>](index.md)
