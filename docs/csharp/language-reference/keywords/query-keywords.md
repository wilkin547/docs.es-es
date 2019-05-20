---
title: 'Palabras clave de consulta: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: dde621395f407cd64e047ddfe8c6539e976b3061
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633024"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="4f2a5-102">Palabras clave de consulta (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4f2a5-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="4f2a5-103">En esta sección, se incluyen las palabras clave contextuales que se usan en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4f2a5-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4f2a5-104">In this section</span></span>

|<span data-ttu-id="4f2a5-105">Cláusula</span><span class="sxs-lookup"><span data-stu-id="4f2a5-105">Clause</span></span>|<span data-ttu-id="4f2a5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f2a5-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="4f2a5-107">from</span><span class="sxs-lookup"><span data-stu-id="4f2a5-107">from</span></span>](from-clause.md)|<span data-ttu-id="4f2a5-108">Especifica un origen de datos y una variable de rango (similar a una variable de iteración).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="4f2a5-109">where</span><span class="sxs-lookup"><span data-stu-id="4f2a5-109">where</span></span>](where-clause.md)|<span data-ttu-id="4f2a5-110">Filtra los elementos de origen en función de una o varias expresiones booleanas separadas por operadores lógicos AND y OR (`&&` o <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="4f2a5-111">select</span><span class="sxs-lookup"><span data-stu-id="4f2a5-111">select</span></span>](select-clause.md)|<span data-ttu-id="4f2a5-112">Especifica el tipo y la forma que tendrán los elementos de la secuencia devuelta cuando se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="4f2a5-113">group</span><span class="sxs-lookup"><span data-stu-id="4f2a5-113">group</span></span>](group-clause.md)|<span data-ttu-id="4f2a5-114">Agrupa los resultados de la consulta según un valor clave especificado.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="4f2a5-115">into</span><span class="sxs-lookup"><span data-stu-id="4f2a5-115">into</span></span>](into.md)|<span data-ttu-id="4f2a5-116">Proporciona un identificador que puede actuar como una referencia a los resultados de una combinación, un grupo o una cláusula select.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="4f2a5-117">orderby</span><span class="sxs-lookup"><span data-stu-id="4f2a5-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="4f2a5-118">Ordena los resultados de las consultas en orden ascendente o descendente según el comparador predeterminado del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="4f2a5-119">join</span><span class="sxs-lookup"><span data-stu-id="4f2a5-119">join</span></span>](join-clause.md)|<span data-ttu-id="4f2a5-120">Combina dos orígenes de datos en función de una comparación de igualdad entre dos criterios de coincidencia especificados.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="4f2a5-121">let</span><span class="sxs-lookup"><span data-stu-id="4f2a5-121">let</span></span>](let-clause.md)|<span data-ttu-id="4f2a5-122">Presenta una variable de rango para almacenar los resultados de la subexpresión en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="4f2a5-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="4f2a5-123">in</span><span class="sxs-lookup"><span data-stu-id="4f2a5-123">in</span></span>](in.md)|<span data-ttu-id="4f2a5-124">Palabra clave contextual en una cláusula [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="4f2a5-125">on</span><span class="sxs-lookup"><span data-stu-id="4f2a5-125">on</span></span>](on.md)|<span data-ttu-id="4f2a5-126">Palabra clave contextual en una cláusula [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="4f2a5-127">equals</span><span class="sxs-lookup"><span data-stu-id="4f2a5-127">equals</span></span>](equals.md)|<span data-ttu-id="4f2a5-128">Palabra clave contextual en una cláusula [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="4f2a5-129">by</span><span class="sxs-lookup"><span data-stu-id="4f2a5-129">by</span></span>](by.md)|<span data-ttu-id="4f2a5-130">Palabra clave contextual en una cláusula [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="4f2a5-131">ascending</span><span class="sxs-lookup"><span data-stu-id="4f2a5-131">ascending</span></span>](ascending.md)|<span data-ttu-id="4f2a5-132">Palabra clave contextual en una cláusula [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="4f2a5-133">descending</span><span class="sxs-lookup"><span data-stu-id="4f2a5-133">descending</span></span>](descending.md)|<span data-ttu-id="4f2a5-134">Palabra clave contextual en una cláusula [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4f2a5-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="4f2a5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f2a5-135">See also</span></span>

- [<span data-ttu-id="4f2a5-136">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4f2a5-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4f2a5-137">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="4f2a5-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="4f2a5-138">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="4f2a5-138">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="4f2a5-139">Introducción a LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="4f2a5-139">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
