---
title: Controlar excepciones en expresiones de consulta
description: "Cómo: Controlar excepciones en expresiones de consulta"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 376bd461bfeb51653471fd374a2215aa15872976
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="c3bff-104">Controlar excepciones en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="c3bff-104">Handle exceptions in query expressions</span></span>

<span data-ttu-id="c3bff-105">Es posible llamar a cualquier método en el contexto de una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-105">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="c3bff-106">Pero se recomienda evitar llamar a cualquier método en una expresión de consulta que pueda crear un efecto secundario, como modificar el contenido del origen de datos o producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="c3bff-106">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="c3bff-107">En este ejemplo se muestra cómo evitar que se produzcan excepciones al llamar a métodos en una expresión de consulta sin infringir las directrices generales de .NET Framework sobre el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="c3bff-107">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="c3bff-108">Esas directrices indican que es aceptable detectar una excepción concreta al comprender por qué se producirá en un contexto determinado.</span><span class="sxs-lookup"><span data-stu-id="c3bff-108">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="c3bff-109">Para obtener más información, vea [Procedimientos recomendados para excepciones](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="c3bff-109">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="c3bff-110">En el último ejemplo se muestra cómo controlar los casos en los que se debe producir una excepción durante la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-110">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3bff-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3bff-111">Example</span></span>  

 <span data-ttu-id="c3bff-112">En el ejemplo siguiente se muestra cómo mover código de control de excepciones fuera de una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-112">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="c3bff-113">Esto solo es posible cuando el método no depende de ninguna variable local de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-113">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="c3bff-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c3bff-114">Example</span></span> 

 <span data-ttu-id="c3bff-115">En algunos casos, la mejor respuesta a una excepción que se produce dentro de una consulta podría ser detener la ejecución de la consulta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="c3bff-115">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="c3bff-116">En el ejemplo siguiente se muestra cómo controlar las excepciones que pueden producirse desde el cuerpo de una consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-116">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="c3bff-117">Supongamos que `SomeMethodThatMightThrow` puede producir una excepción que requiere que se detenga la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-117">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="c3bff-118">Tenga en cuenta que el bloque `try` encierra el bucle `foreach` y no la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-118">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="c3bff-119">Esto es porque el bucle `foreach` es el punto en el que se ejecuta realmente la consulta.</span><span class="sxs-lookup"><span data-stu-id="c3bff-119">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="c3bff-120">Para obtener más información, vea [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md) (Introducción a las consultas LINQ).</span><span class="sxs-lookup"><span data-stu-id="c3bff-120">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="c3bff-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3bff-121">See Also</span></span>  
 [<span data-ttu-id="c3bff-122">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="c3bff-122">LINQ query expressions</span></span>](index.md)
