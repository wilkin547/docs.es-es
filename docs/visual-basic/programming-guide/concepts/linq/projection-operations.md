---
description: 'Más información acerca de: operaciones de proyección (Visual Basic)'
title: Operaciones de proyección
ms.date: 07/20/2015
ms.assetid: b8d38e6d-21cf-4619-8dbb-94476f4badc7
ms.openlocfilehash: 5531bec915f3a9ee521e0d67941b8f1d49e90524
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466463"
---
# <a name="projection-operations-visual-basic"></a><span data-ttu-id="087f0-103">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="087f0-103">Projection Operations (Visual Basic)</span></span>

<span data-ttu-id="087f0-104">El término "proyección" hace referencia a la operación de transformar un objeto en una nueva forma que, a menudo, consta solo de aquellas propiedades que se usarán posteriormente.</span><span class="sxs-lookup"><span data-stu-id="087f0-104">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="087f0-105">Utilizando la proyección, puede construir un tipo nuevo creado a partir de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="087f0-105">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="087f0-106">Se puede proyectar una propiedad y realizar una función matemática en ella.</span><span class="sxs-lookup"><span data-stu-id="087f0-106">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="087f0-107">También puede proyectar el objeto original sin cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="087f0-107">You can also project the original object without changing it.</span></span>

<span data-ttu-id="087f0-108">Los métodos del operador de consulta estándar que realizan proyecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="087f0-108">The standard query operator methods that perform projection are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="087f0-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="087f0-109">Methods</span></span>

|<span data-ttu-id="087f0-110">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="087f0-110">Method Name</span></span>|<span data-ttu-id="087f0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="087f0-111">Description</span></span>|<span data-ttu-id="087f0-112">Visual Basic sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="087f0-112">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="087f0-113">Más información</span><span class="sxs-lookup"><span data-stu-id="087f0-113">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="087f0-114">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="087f0-114">Select</span></span>|<span data-ttu-id="087f0-115">Proyecta valores basados en una función de transformación.</span><span class="sxs-lookup"><span data-stu-id="087f0-115">Projects values that are based on a transform function.</span></span>|`Select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|
|<span data-ttu-id="087f0-116">SelectMany</span><span class="sxs-lookup"><span data-stu-id="087f0-116">SelectMany</span></span>|<span data-ttu-id="087f0-117">Proyecta secuencias de valores que se basan en una función de transformación y después los convierte en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="087f0-117">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="087f0-118">Use varias cláusulas `From`</span><span class="sxs-lookup"><span data-stu-id="087f0-118">Use multiple `From` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="087f0-119">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="087f0-119">Query Expression Syntax Examples</span></span>

### <a name="select"></a><span data-ttu-id="087f0-120">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="087f0-120">Select</span></span>

<span data-ttu-id="087f0-121">En el ejemplo siguiente se usa la cláusula `Select` para proyectar la primera letra de cada cadena de una lista de cadenas.</span><span class="sxs-lookup"><span data-stu-id="087f0-121">The following example uses the `Select` clause to project the first letter from each string in a list of strings.</span></span>

```vb
Dim words = New List(Of String) From {"an", "apple", "a", "day"}

Dim query = From word In words
            Select word.Substring(0, 1)

Dim sb As New System.Text.StringBuilder()
For Each letter As String In query
    sb.AppendLine(letter)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' a
' a
' a
' d
```

### <a name="selectmany"></a><span data-ttu-id="087f0-122">SelectMany</span><span class="sxs-lookup"><span data-stu-id="087f0-122">SelectMany</span></span>

<span data-ttu-id="087f0-123">En el ejemplo siguiente se usan varias `From` cláusulas para proyectar cada palabra de cada cadena en una lista de cadenas.</span><span class="sxs-lookup"><span data-stu-id="087f0-123">The following example uses multiple `From` clauses to project each word from each string in a list of strings.</span></span>

```vb
Dim phrases = New List(Of String) From {"an apple a day", "the quick brown fox"}

Dim query = From phrase In phrases
            From word In phrase.Split(" "c)
            Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In query
    sb.AppendLine(str)
Next

' Display the output.
MsgBox(sb.ToString())

' This code produces the following output:

' an
' apple
' a
' day
' the
' quick
' brown
' fox
```

## <a name="select-versus-selectmany"></a><span data-ttu-id="087f0-124">Select frente a SelectMany</span><span class="sxs-lookup"><span data-stu-id="087f0-124">Select versus SelectMany</span></span>

<span data-ttu-id="087f0-125">La función tanto de `Select()` como de `SelectMany()` consiste en generar un valor (o valores) de resultado a partir de valores de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-125">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="087f0-126">`Select()` genera un valor de resultado para cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-126">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="087f0-127">El resultado global, por tanto, es una colección que tiene el mismo número de elementos que la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-127">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="087f0-128">En cambio, `SelectMany()` genera un resultado global único que contiene subcolecciones concatenadas procedentes de cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-128">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="087f0-129">La función de transformación que se pasa como argumento a `SelectMany()` debe devolver una secuencia enumerable de valores para cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-129">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="087f0-130">Luego, `SelectMany()` concatena estas secuencias enumerables para crear una secuencia de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="087f0-130">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>

<span data-ttu-id="087f0-131">Las dos ilustraciones siguientes muestran la diferencia conceptual entre las acciones de estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="087f0-131">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="087f0-132">En cada caso, se supone que la función de selector (transformación) selecciona la matriz de flores de cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-132">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>

<span data-ttu-id="087f0-133">En esta ilustración se muestra cómo `Select()` devuelve una colección que tiene el mismo número de elementos que la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-133">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>

![Gráfico en el que se muestra la acción Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)

<span data-ttu-id="087f0-135">En esta ilustración se muestra cómo `SelectMany()` concatena la secuencia intermedia de matrices en un valor de resultado final que contiene cada uno de los valores de todas las matrices intermedias.</span><span class="sxs-lookup"><span data-stu-id="087f0-135">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>

![Gráfico en el que se muestra la acción SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )

### <a name="code-example"></a><span data-ttu-id="087f0-137">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="087f0-137">Code Example</span></span>

<span data-ttu-id="087f0-138">En el ejemplo siguiente se compara el comportamiento de `Select()` y `SelectMany()`.</span><span class="sxs-lookup"><span data-stu-id="087f0-138">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="087f0-139">El código crea un "ramo" de flores tomando los dos primeros elementos de cada lista de nombres de flores de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="087f0-139">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="087f0-140">En este ejemplo, el "valor único" que la función de transformación <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> usa es una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="087f0-140">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="087f0-141">Para ello, se requiere el bucle adicional `For Each` a fin de enumerar cada una de las cadenas de cada subsecuencia.</span><span class="sxs-lookup"><span data-stu-id="087f0-141">This requires the extra `For Each` loop in order to enumerate each string in each sub-sequence.</span></span>

```vb
Class Bouquet
    Public Flowers As List(Of String)
End Class

Sub SelectVsSelectMany()
    Dim bouquets = New List(Of Bouquet) From {
        New Bouquet With {.Flowers = New List(Of String)(New String() {"sunflower", "daisy", "daffodil", "larkspur"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"tulip", "rose", "orchid"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"gladiolis", "lily", "snapdragon", "aster", "protea"})},
        New Bouquet With {.Flowers = New List(Of String)(New String() {"larkspur", "lilac", "iris", "dahlia"})}}

    Dim output As New System.Text.StringBuilder

    ' Select()
    Dim query1 = bouquets.Select(Function(b) b.Flowers)

    output.AppendLine("Using Select():")
    For Each flowerList In query1
        For Each str As String In flowerList
            output.AppendLine(str)
        Next
    Next

    ' SelectMany()
    Dim query2 = bouquets.SelectMany(Function(b) b.Flowers)

    output.AppendLine(vbCrLf & "Using SelectMany():")
    For Each str As String In query2
        output.AppendLine(str)
    Next

    ' Display the output
    MsgBox(output.ToString())

    ' This code produces the following output:
    '
    ' Using Select():
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

    ' Using SelectMany()
    ' sunflower
    ' daisy
    ' daffodil
    ' larkspur
    ' tulip
    ' rose
    ' orchid
    ' gladiolis
    ' lily
    ' snapdragon
    ' aster
    ' protea
    ' larkspur
    ' lilac
    ' iris
    ' dahlia

End Sub
```

## <a name="see-also"></a><span data-ttu-id="087f0-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="087f0-142">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="087f0-143">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="087f0-143">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="087f0-144">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="087f0-144">Select Clause</span></span>](../../../language-reference/queries/select-clause.md)
- [<span data-ttu-id="087f0-145">Cómo: Combinar datos con cláusulas Join</span><span class="sxs-lookup"><span data-stu-id="087f0-145">How to: Combine Data with Joins</span></span>](../../language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)
- [<span data-ttu-id="087f0-146">Cómo: rellenar colecciones de objetos de varios orígenes (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="087f0-146">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="087f0-147">Procedimiento para devolver el resultado de una consulta con LINQ como tipo específico</span><span class="sxs-lookup"><span data-stu-id="087f0-147">How to: Return a LINQ Query Result as a Specific Type</span></span>](../../language-features/linq/how-to-return-a-linq-query-result-as-a-specific-type.md)
- [<span data-ttu-id="087f0-148">Cómo: dividir un archivo en varios archivos mediante el uso de grupos (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="087f0-148">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)
