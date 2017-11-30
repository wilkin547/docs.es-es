---
title: Controlar valores nulos en expresiones de consulta
description: "Cómo se controlan valores nulos en expresiones de consulta."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: ac63ae8b-724d-4251-9334-528f4e884ae7
ms.openlocfilehash: d16256e31b073a599504ffef6501ed34430a7694
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="handle-null-values-in-query-expressions"></a><span data-ttu-id="5dd78-104">Controlar valores nulos en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="5dd78-104">Handle null values in query expressions</span></span>

<span data-ttu-id="5dd78-105">En este ejemplo se muestra cómo controlar los posibles valores nulos en colecciones de origen.</span><span class="sxs-lookup"><span data-stu-id="5dd78-105">This example shows how to handle possible null values in source collections.</span></span> <span data-ttu-id="5dd78-106">Una colección de objetos como <xref:System.Collections.Generic.IEnumerable%601> puede contener elementos cuyo valor es [NULL](../language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="5dd78-106">An object collection such as an <xref:System.Collections.Generic.IEnumerable%601> can contain elements whose value is [null](../language-reference/keywords/null.md).</span></span> <span data-ttu-id="5dd78-107">Si una colección de origen es nula o contiene un elemento cuyo valor es NULL, y la consulta no controla los valores NULL, se iniciará una <xref:System.NullReferenceException> cuando se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="5dd78-107">If a source collection is null or contains an element whose value is null, and your query does not handle null values, a <xref:System.NullReferenceException> will be thrown when you execute the query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dd78-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dd78-108">Example</span></span>

 <span data-ttu-id="5dd78-109">Se pueden codificar de forma defensiva para evitar una excepción de referencia nula, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5dd78-109">You can code defensively to avoid a null reference exception as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#82](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_1.cs)]  
  
 <span data-ttu-id="5dd78-110">En el ejemplo anterior, la cláusula `where` filtra todos los elementos nulos de la secuencia de categorías.</span><span class="sxs-lookup"><span data-stu-id="5dd78-110">In the previous example, the `where` clause filters out all null elements in the categories sequence.</span></span> <span data-ttu-id="5dd78-111">Esta técnica es independiente de la comprobación de null en la cláusula join.</span><span class="sxs-lookup"><span data-stu-id="5dd78-111">This technique is independent of the null check in the join clause.</span></span> <span data-ttu-id="5dd78-112">La expresión condicional con null de este ejemplo funciona porque `Products.CategoryID` es de tipo `int?`, que es una abreviatura de `Nullable<int>`.</span><span class="sxs-lookup"><span data-stu-id="5dd78-112">The conditional expression with null in this example works because `Products.CategoryID` is of type `int?` which is shorthand for `Nullable<int>`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dd78-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dd78-113">Example</span></span>

 <span data-ttu-id="5dd78-114">En una cláusula join, si solo una de las claves de comparación es un tipo que acepta valores NULL, puede convertir la otra en un tipo que acepta valores NULL en la expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="5dd78-114">In a join clause, if only one of the comparison keys is a nullable value type, you can cast the other to a nullable type in the query expression.</span></span> <span data-ttu-id="5dd78-115">En el ejemplo siguiente, suponga que `EmployeeID` es una columna que contiene valores de tipo `int?`:</span><span class="sxs-lookup"><span data-stu-id="5dd78-115">In the following example, assume that `EmployeeID` is a column that contains values of type `int?`:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#83](../../../samples/snippets/csharp/concepts/linq/how-to-handle-null-values-in-query-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5dd78-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dd78-116">See also</span></span>  
 <xref:System.Nullable%601>  
 [<span data-ttu-id="5dd78-117">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="5dd78-117">LINQ query expressions</span></span>](index.md)  
 <span data-ttu-id="5dd78-118">[Nullable types](../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="5dd78-118">[Nullable types](../programming-guide/nullable-types/index.md)</span></span>
