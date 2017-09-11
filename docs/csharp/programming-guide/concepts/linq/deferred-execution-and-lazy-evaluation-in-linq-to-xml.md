---
title: "Ejecución aplazada y evaluación diferida en LINQ to XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10ecebc2563df5a12b71a743727b1be21b19b671
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a><span data-ttu-id="e8e24-102">Ejecución aplazada y evaluación diferida en LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e8e24-102">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>
<span data-ttu-id="e8e24-103">Las operaciones de consulta y de eje a menudo se implementan para usar la ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="e8e24-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="e8e24-104">Este tema describe los requisitos y las ventajas de la ejecución aplazada, y algunas consideraciones acerca de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e8e24-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="e8e24-105">Ejecución aplazada</span><span class="sxs-lookup"><span data-stu-id="e8e24-105">Deferred Execution</span></span>  
 <span data-ttu-id="e8e24-106">La ejecución aplazada significa que la evaluación de una expresión se retrasa hasta que su valor *realizado* sea realmente necesario.</span><span class="sxs-lookup"><span data-stu-id="e8e24-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="e8e24-107">La ejecución aplazada puede mejorar considerablemente el rendimiento cuando deba manipular grandes recolecciones de datos, sobre todo en programas que contengan una serie de manipulaciones o consultas encadenadas.</span><span class="sxs-lookup"><span data-stu-id="e8e24-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="e8e24-108">En el mejor de los casos, la ejecución aplazada solo habilita una iteración a través de la recolección de origen.</span><span class="sxs-lookup"><span data-stu-id="e8e24-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="e8e24-109">Las tecnologías LINQ usan intensivamente la ejecución aplazada tanto en los miembros de las clases <xref:System.Linq?displayProperty=fullName> principales como en los métodos de extensión de los diversos espacios de nombres LINQ, por ejemplo, <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e8e24-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=fullName> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="e8e24-110">El lenguaje C# admite directamente la ejecución aplazada mediante la palabra clave [yield](../../../../csharp/language-reference/keywords/yield.md) (en forma de instrucción `yield-return`) cuando se usa en un bloque de iteradores.</span><span class="sxs-lookup"><span data-stu-id="e8e24-110">Deferred execution is supported directly in the C# language by the [yield](../../../../csharp/language-reference/keywords/yield.md) keyword (in the form of the `yield-return` statement) when used within an iterator block.</span></span> <span data-ttu-id="e8e24-111">Este tipo de iterador debe devolver una colección de tipo <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> (o bien un tipo derivado).</span><span class="sxs-lookup"><span data-stu-id="e8e24-111">Such an iterator must return a collection of type <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> (or a derived type).</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="e8e24-112">Diferencias entre la evaluación diligente y la evaluación diferida</span><span class="sxs-lookup"><span data-stu-id="e8e24-112">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="e8e24-113">Al escribir un método que implemente una ejecución aplazada, también debe decidir si implementa el método con la evaluación diferida o la evaluación diligente.</span><span class="sxs-lookup"><span data-stu-id="e8e24-113">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="e8e24-114">En la *evaluación diferida*, un único elemento de la colección de origen se procesa durante cada llamada al iterador.</span><span class="sxs-lookup"><span data-stu-id="e8e24-114">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="e8e24-115">Esta es la forma habitual en la que se implementan los iteradores.</span><span class="sxs-lookup"><span data-stu-id="e8e24-115">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="e8e24-116">En la *evaluación diligente*, la primera llamada al iterador hará que se procese toda la colección.</span><span class="sxs-lookup"><span data-stu-id="e8e24-116">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="e8e24-117">Es posible que también se requiera una copia temporal de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="e8e24-117">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="e8e24-118">Por ejemplo, el método <xref:System.Linq.Enumerable.OrderBy%2A> debe ordenar toda la colección antes de devolver el primer elemento.</span><span class="sxs-lookup"><span data-stu-id="e8e24-118">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="e8e24-119">Normalmente, la evaluación diferida presenta un mejor rendimiento, ya que distribuye el procesamiento de sobrecarga de forma equitativa durante la evaluación de la colección y minimiza el uso de los datos temporales.</span><span class="sxs-lookup"><span data-stu-id="e8e24-119">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="e8e24-120">Obviamente, para algunas operaciones, no existe otra alternativa que materializar resultados intermedios.</span><span class="sxs-lookup"><span data-stu-id="e8e24-120">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e8e24-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e8e24-121">Next Steps</span></span>  
 <span data-ttu-id="e8e24-122">El siguiente tema de este tutorial ilustra la ejecución aplazada:</span><span class="sxs-lookup"><span data-stu-id="e8e24-122">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="e8e24-123">Ejemplo de ejecución diferida (C#)</span><span class="sxs-lookup"><span data-stu-id="e8e24-123">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8e24-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8e24-124">See Also</span></span>  
 <span data-ttu-id="e8e24-125">[Tutorial: Encadenar consultas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) </span><span class="sxs-lookup"><span data-stu-id="e8e24-125">[Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) </span></span>  
 <span data-ttu-id="e8e24-126">[Conceptos y terminología (transformación funcional) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="e8e24-126">[Concepts and Terminology (Functional Transformation) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md) </span></span>  
 <span data-ttu-id="e8e24-127">[Operaciones de agregación (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) </span><span class="sxs-lookup"><span data-stu-id="e8e24-127">[Aggregation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) </span></span>  
 [<span data-ttu-id="e8e24-128">yield</span><span class="sxs-lookup"><span data-stu-id="e8e24-128">yield</span></span>](../../../../csharp/language-reference/keywords/yield.md)

