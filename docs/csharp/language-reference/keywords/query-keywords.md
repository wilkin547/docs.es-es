---
title: Palabras clave de consultas (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6dadce6d48e711032cca03a7f7c2ba02360e685f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="a547d-102">Palabras clave de consultas (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a547d-102">Query Keywords (C# Reference)</span></span>
<span data-ttu-id="a547d-103">En esta sección, se incluyen las palabras clave contextuales que se usan en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="a547d-103">This section contains the contextual keywords used in query expressions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a547d-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a547d-104">In This Section</span></span>  
  
|<span data-ttu-id="a547d-105">Cláusula</span><span class="sxs-lookup"><span data-stu-id="a547d-105">Clause</span></span>|<span data-ttu-id="a547d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a547d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a547d-107">from</span><span class="sxs-lookup"><span data-stu-id="a547d-107">from</span></span>](../../../csharp/language-reference/keywords/from-clause.md)|<span data-ttu-id="a547d-108">Especifica un origen de datos y una variable de rango (similar a una variable de iteración).</span><span class="sxs-lookup"><span data-stu-id="a547d-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|  
|[<span data-ttu-id="a547d-109">where</span><span class="sxs-lookup"><span data-stu-id="a547d-109">where</span></span>](../../../csharp/language-reference/keywords/where-clause.md)|<span data-ttu-id="a547d-110">Filtra los elementos de origen en función de una o varias expresiones booleanas separadas por operadores lógicos AND y OR (`&&` o <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="a547d-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|  
|[<span data-ttu-id="a547d-111">select</span><span class="sxs-lookup"><span data-stu-id="a547d-111">select</span></span>](../../../csharp/language-reference/keywords/select-clause.md)|<span data-ttu-id="a547d-112">Especifica el tipo y la forma que tendrán los elementos de la secuencia devuelta cuando se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="a547d-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|  
|[<span data-ttu-id="a547d-113">group</span><span class="sxs-lookup"><span data-stu-id="a547d-113">group</span></span>](../../../csharp/language-reference/keywords/group-clause.md)|<span data-ttu-id="a547d-114">Agrupa los resultados de la consulta según un valor clave especificado.</span><span class="sxs-lookup"><span data-stu-id="a547d-114">Groups query results according to a specified key value.</span></span>|  
|[<span data-ttu-id="a547d-115">into</span><span class="sxs-lookup"><span data-stu-id="a547d-115">into</span></span>](../../../csharp/language-reference/keywords/into.md)|<span data-ttu-id="a547d-116">Proporciona un identificador que puede actuar como una referencia a los resultados de una combinación, un grupo o una cláusula select.</span><span class="sxs-lookup"><span data-stu-id="a547d-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|  
|[<span data-ttu-id="a547d-117">orderby</span><span class="sxs-lookup"><span data-stu-id="a547d-117">orderby</span></span>](../../../csharp/language-reference/keywords/orderby-clause.md)|<span data-ttu-id="a547d-118">Ordena los resultados de las consultas en orden ascendente o descendente según el comparador predeterminado del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="a547d-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|  
|[<span data-ttu-id="a547d-119">join</span><span class="sxs-lookup"><span data-stu-id="a547d-119">join</span></span>](../../../csharp/language-reference/keywords/join-clause.md)|<span data-ttu-id="a547d-120">Combina dos orígenes de datos en función de una comparación de igualdad entre dos criterios de coincidencia especificados.</span><span class="sxs-lookup"><span data-stu-id="a547d-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|  
|[<span data-ttu-id="a547d-121">let</span><span class="sxs-lookup"><span data-stu-id="a547d-121">let</span></span>](../../../csharp/language-reference/keywords/let-clause.md)|<span data-ttu-id="a547d-122">Presenta una variable de rango para almacenar los resultados de la subexpresión en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a547d-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|  
|[<span data-ttu-id="a547d-123">in</span><span class="sxs-lookup"><span data-stu-id="a547d-123">in</span></span>](../../../csharp/language-reference/keywords/in.md)|<span data-ttu-id="a547d-124">Palabra clave contextual en una cláusula [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a547d-124">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a547d-125">on</span><span class="sxs-lookup"><span data-stu-id="a547d-125">on</span></span>](../../../csharp/language-reference/keywords/on.md)|<span data-ttu-id="a547d-126">Palabra clave contextual en una cláusula [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a547d-126">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a547d-127">equals</span><span class="sxs-lookup"><span data-stu-id="a547d-127">equals</span></span>](../../../csharp/language-reference/keywords/equals.md)|<span data-ttu-id="a547d-128">Palabra clave contextual en una cláusula [join](../../../csharp/language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a547d-128">Contextual keyword in a [join](../../../csharp/language-reference/keywords/join-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a547d-129">by</span><span class="sxs-lookup"><span data-stu-id="a547d-129">by</span></span>](../../../csharp/language-reference/keywords/by.md)|<span data-ttu-id="a547d-130">Palabra clave contextual en una cláusula [group](../../../csharp/language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a547d-130">Contextual keyword in a [group](../../../csharp/language-reference/keywords/group-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a547d-131">ascending</span><span class="sxs-lookup"><span data-stu-id="a547d-131">ascending</span></span>](../../../csharp/language-reference/keywords/ascending.md)|<span data-ttu-id="a547d-132">Palabra clave contextual en una cláusula [orderby](../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a547d-132">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
|[<span data-ttu-id="a547d-133">descending</span><span class="sxs-lookup"><span data-stu-id="a547d-133">descending</span></span>](../../../csharp/language-reference/keywords/descending.md)|<span data-ttu-id="a547d-134">Palabra clave contextual en una cláusula [orderby](../../../csharp/language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a547d-134">Contextual keyword in an [orderby](../../../csharp/language-reference/keywords/orderby-clause.md) clause.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a547d-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a547d-135">See Also</span></span>  
 <span data-ttu-id="a547d-136">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a547d-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a547d-137">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="a547d-137">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="a547d-138">[Expresiones de consulta LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="a547d-138">[LINQ Query Expressions](../../../csharp/programming-guide/linq-query-expressions/index.md) </span></span>  
 [<span data-ttu-id="a547d-139">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="a547d-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

