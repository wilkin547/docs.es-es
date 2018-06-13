---
title: Controlar excepciones en expresiones de consulta
description: 'Cómo: Controlar excepciones en expresiones de consulta'
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 691373fabeb3934ecc454cbc3b36a5f7bf477bee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284856"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="3115d-103">Controlar excepciones en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="3115d-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="3115d-104">Es posible llamar a cualquier método en el contexto de una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-104">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="3115d-105">Pero se recomienda evitar llamar a cualquier método en una expresión de consulta que pueda crear un efecto secundario, como modificar el contenido del origen de datos o producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="3115d-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="3115d-106">En este ejemplo se muestra cómo evitar que se produzcan excepciones al llamar a métodos en una expresión de consulta sin infringir las directrices generales de .NET Framework sobre el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="3115d-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="3115d-107">Esas directrices indican que es aceptable detectar una excepción concreta al comprender por qué se producirá en un contexto determinado.</span><span class="sxs-lookup"><span data-stu-id="3115d-107">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="3115d-108">Para obtener más información, vea [Procedimientos recomendados para excepciones](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="3115d-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="3115d-109">En el último ejemplo se muestra cómo controlar los casos en los que se debe producir una excepción durante la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3115d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3115d-110">Example</span></span>  

 <span data-ttu-id="3115d-111">En el ejemplo siguiente se muestra cómo mover código de control de excepciones fuera de una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="3115d-112">Esto solo es posible cuando el método no depende de ninguna variable local de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-112">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="3115d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3115d-113">Example</span></span> 

 <span data-ttu-id="3115d-114">En algunos casos, la mejor respuesta a una excepción que se produce dentro de una consulta podría ser detener la ejecución de la consulta inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="3115d-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="3115d-115">En el ejemplo siguiente se muestra cómo controlar las excepciones que pueden producirse desde el cuerpo de una consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="3115d-116">Supongamos que `SomeMethodThatMightThrow` puede producir una excepción que requiere que se detenga la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="3115d-117">Tenga en cuenta que el bloque `try` encierra el bucle `foreach` y no la propia consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="3115d-118">Esto es porque el bucle `foreach` es el punto en el que se ejecuta realmente la consulta.</span><span class="sxs-lookup"><span data-stu-id="3115d-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="3115d-119">Para obtener más información, vea [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md) (Introducción a las consultas LINQ).</span><span class="sxs-lookup"><span data-stu-id="3115d-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="3115d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3115d-120">See Also</span></span>  
 [<span data-ttu-id="3115d-121">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="3115d-121">LINQ query expressions</span></span>](index.md)
