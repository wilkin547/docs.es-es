---
title: 'Palabras clave de consulta: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- query keywords [C#]
- LINQ [C#], query keywords
ms.assetid: 6c9bec16-dbd7-4a7c-a060-fe4600b2021f
ms.openlocfilehash: 01134eda540c5141afbd11b2c89ff779da495a9a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173528"
---
# <a name="query-keywords-c-reference"></a><span data-ttu-id="a7d99-102">Palabras clave de consulta (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a7d99-102">Query keywords (C# Reference)</span></span>

<span data-ttu-id="a7d99-103">En esta sección, se incluyen las palabras clave contextuales que se usan en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="a7d99-103">This section contains the contextual keywords used in query expressions.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a7d99-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a7d99-104">In this section</span></span>

|<span data-ttu-id="a7d99-105">Cláusula</span><span class="sxs-lookup"><span data-stu-id="a7d99-105">Clause</span></span>|<span data-ttu-id="a7d99-106">Description</span><span class="sxs-lookup"><span data-stu-id="a7d99-106">Description</span></span>|
|------------|-----------------|
|[<span data-ttu-id="a7d99-107">from</span><span class="sxs-lookup"><span data-stu-id="a7d99-107">from</span></span>](from-clause.md)|<span data-ttu-id="a7d99-108">Especifica un origen de datos y una variable de rango (similar a una variable de iteración).</span><span class="sxs-lookup"><span data-stu-id="a7d99-108">Specifies a data source and a range variable (similar to an iteration variable).</span></span>|
|[<span data-ttu-id="a7d99-109">where</span><span class="sxs-lookup"><span data-stu-id="a7d99-109">where</span></span>](where-clause.md)|<span data-ttu-id="a7d99-110">Filtra los elementos de origen en función de una o varias expresiones booleanas separadas por operadores lógicos AND y OR (`&&` o <code>&#124;&#124;</code>).</span><span class="sxs-lookup"><span data-stu-id="a7d99-110">Filters source elements based on one or more Boolean expressions separated by logical AND and OR operators ( `&&` or <code>&#124;&#124;</code> ).</span></span>|
|[<span data-ttu-id="a7d99-111">select</span><span class="sxs-lookup"><span data-stu-id="a7d99-111">select</span></span>](select-clause.md)|<span data-ttu-id="a7d99-112">Especifica el tipo y la forma que tendrán los elementos de la secuencia devuelta cuando se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="a7d99-112">Specifies the type and shape that the elements in the returned sequence will have when the query is executed.</span></span>|
|[<span data-ttu-id="a7d99-113">group</span><span class="sxs-lookup"><span data-stu-id="a7d99-113">group</span></span>](group-clause.md)|<span data-ttu-id="a7d99-114">Agrupa los resultados de la consulta según un valor clave especificado.</span><span class="sxs-lookup"><span data-stu-id="a7d99-114">Groups query results according to a specified key value.</span></span>|
|[<span data-ttu-id="a7d99-115">into</span><span class="sxs-lookup"><span data-stu-id="a7d99-115">into</span></span>](into.md)|<span data-ttu-id="a7d99-116">Proporciona un identificador que puede actuar como una referencia a los resultados de una combinación, un grupo o una cláusula select.</span><span class="sxs-lookup"><span data-stu-id="a7d99-116">Provides an identifier that can serve as a reference to the results of a join, group or select clause.</span></span>|
|[<span data-ttu-id="a7d99-117">orderby</span><span class="sxs-lookup"><span data-stu-id="a7d99-117">orderby</span></span>](orderby-clause.md)|<span data-ttu-id="a7d99-118">Ordena los resultados de las consultas en orden ascendente o descendente según el comparador predeterminado del tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="a7d99-118">Sorts query results in ascending or descending order based on the default comparer for the element type.</span></span>|
|[<span data-ttu-id="a7d99-119">join</span><span class="sxs-lookup"><span data-stu-id="a7d99-119">join</span></span>](join-clause.md)|<span data-ttu-id="a7d99-120">Combina dos orígenes de datos en función de una comparación de igualdad entre dos criterios de coincidencia especificados.</span><span class="sxs-lookup"><span data-stu-id="a7d99-120">Joins two data sources based on an equality comparison between two specified matching criteria.</span></span>|
|[<span data-ttu-id="a7d99-121">let</span><span class="sxs-lookup"><span data-stu-id="a7d99-121">let</span></span>](let-clause.md)|<span data-ttu-id="a7d99-122">Presenta una variable de rango para almacenar los resultados de la subexpresión en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a7d99-122">Introduces a range variable to store sub-expression results in a query expression.</span></span>|
|[<span data-ttu-id="a7d99-123">in</span><span class="sxs-lookup"><span data-stu-id="a7d99-123">in</span></span>](in.md)|<span data-ttu-id="a7d99-124">Palabra clave contextual en una cláusula [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7d99-124">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="a7d99-125">on</span><span class="sxs-lookup"><span data-stu-id="a7d99-125">on</span></span>](on.md)|<span data-ttu-id="a7d99-126">Palabra clave contextual en una cláusula [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7d99-126">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="a7d99-127">equals</span><span class="sxs-lookup"><span data-stu-id="a7d99-127">equals</span></span>](equals.md)|<span data-ttu-id="a7d99-128">Palabra clave contextual en una cláusula [join](join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7d99-128">Contextual keyword in a [join](join-clause.md) clause.</span></span>|
|[<span data-ttu-id="a7d99-129">by</span><span class="sxs-lookup"><span data-stu-id="a7d99-129">by</span></span>](by.md)|<span data-ttu-id="a7d99-130">Palabra clave contextual en una cláusula [group](group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7d99-130">Contextual keyword in a [group](group-clause.md) clause.</span></span>|
|[<span data-ttu-id="a7d99-131">ascending</span><span class="sxs-lookup"><span data-stu-id="a7d99-131">ascending</span></span>](ascending.md)|<span data-ttu-id="a7d99-132">Palabra clave contextual en una cláusula [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7d99-132">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|
|[<span data-ttu-id="a7d99-133">descending</span><span class="sxs-lookup"><span data-stu-id="a7d99-133">descending</span></span>](descending.md)|<span data-ttu-id="a7d99-134">Palabra clave contextual en una cláusula [orderby](orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="a7d99-134">Contextual keyword in an [orderby](orderby-clause.md) clause.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a7d99-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7d99-135">See also</span></span>

- [<span data-ttu-id="a7d99-136">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a7d99-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a7d99-137">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="a7d99-137">LINQ (Language-Integrated Query)</span></span>](../../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="a7d99-138">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="a7d99-138">LINQ in C#</span></span>](../../linq/index.md)
