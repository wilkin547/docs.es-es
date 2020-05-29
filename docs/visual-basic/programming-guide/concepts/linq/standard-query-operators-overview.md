---
title: Información general sobre operadores de consulta estándar
ms.date: 07/20/2015
ms.assetid: 302bd39e-2ec1-495b-94bf-37d370d6f05f
ms.openlocfilehash: 0f68d175b526a9da86853272c47b5e7d7b4a5992
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201083"
---
# <a name="standard-query-operators-overview-visual-basic"></a><span data-ttu-id="37d84-102">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-102">Standard Query Operators Overview (Visual Basic)</span></span>

<span data-ttu-id="37d84-103">Los *operadores de consulta estándar* son los métodos que constituyen el modelo LINQ.</span><span class="sxs-lookup"><span data-stu-id="37d84-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="37d84-104">La mayoría de estos métodos funciona en secuencias; donde una secuencia es un objeto cuyo tipo implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> o la interfaz <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="37d84-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="37d84-105">Los operadores de consulta estándar ofrecen funcionalidades de consulta, como las funciones de filtrado, proyección, agregación y ordenación, entre otras.</span><span class="sxs-lookup"><span data-stu-id="37d84-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>

<span data-ttu-id="37d84-106">Hay dos conjuntos de operadores de consulta estándar de LINQ, uno que actúa sobre objetos de tipo <xref:System.Collections.Generic.IEnumerable%601> y otro que actúa en objetos de tipo <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="37d84-106">There are two sets of LINQ standard query operators, one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601> and the other that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="37d84-107">Los métodos que forman cada conjunto son miembros estáticos de las clases <xref:System.Linq.Enumerable> y <xref:System.Linq.Queryable>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="37d84-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="37d84-108">Se definen como *métodos de extensión* del tipo en el que actúan.</span><span class="sxs-lookup"><span data-stu-id="37d84-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="37d84-109">Esto significa que se pueden llamar mediante sintaxis de método estático o sintaxis de método de instancia.</span><span class="sxs-lookup"><span data-stu-id="37d84-109">This means that they can be called by using either static method syntax or instance method syntax.</span></span>

<span data-ttu-id="37d84-110">Además, varios métodos de operador de consulta estándar funcionan en tipos distintos de los que se basan en <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="37d84-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="37d84-111">El tipo <xref:System.Linq.Enumerable> define dos métodos que funcionan en objetos de tipo <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="37d84-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="37d84-112">Estos métodos, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> y <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, le permiten habilitar una colección no genérica o no parametrizada para consultarse en el patrón LINQ.</span><span class="sxs-lookup"><span data-stu-id="37d84-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="37d84-113">Para ello, se crea una colección fuertemente tipada de objetos.</span><span class="sxs-lookup"><span data-stu-id="37d84-113">They do this by creating a strongly typed collection of objects.</span></span> <span data-ttu-id="37d84-114">La clase <xref:System.Linq.Queryable> define dos métodos similares, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> y <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, que funcionan en objetos de tipo <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="37d84-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>

<span data-ttu-id="37d84-115">Los operadores de consulta estándar difieren en sus intervalos de ejecución, dependiendo de que devuelvan un valor singleton o una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="37d84-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="37d84-116">Esos métodos que devuelven un valor singleton (por ejemplo, <xref:System.Linq.Enumerable.Average%2A> y <xref:System.Linq.Enumerable.Sum%2A>) se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="37d84-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="37d84-117">Los métodos que devuelven una secuencia aplazan la ejecución de la consulta y devuelven un objeto enumerable.</span><span class="sxs-lookup"><span data-stu-id="37d84-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>

<span data-ttu-id="37d84-118">En el caso de los métodos que actúan en colecciones en memoria, es decir, los métodos que extienden <xref:System.Collections.Generic.IEnumerable%601>, el objeto enumerable devuelto captura los argumentos que se han pasado al método.</span><span class="sxs-lookup"><span data-stu-id="37d84-118">In the case of the methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="37d84-119">Cuando se enumera ese objeto, se emplea la lógica del operador de consulta y se devuelven los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="37d84-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>

<span data-ttu-id="37d84-120">En cambio, los métodos que extienden <xref:System.Linq.IQueryable%601> no implementan ningún comportamiento de consulta, pero crean un árbol de la expresión que representa la consulta que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="37d84-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> do not implement any querying behavior, but build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="37d84-121">El procesamiento de consultas se controla mediante el objeto <xref:System.Linq.IQueryable%601> de origen.</span><span class="sxs-lookup"><span data-stu-id="37d84-121">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>

<span data-ttu-id="37d84-122">Las llamadas a métodos de consulta se pueden encadenar juntas en una consulta, lo que permite que las consultas se conviertan en complejas de forma arbitraria.</span><span class="sxs-lookup"><span data-stu-id="37d84-122">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>

<span data-ttu-id="37d84-123">En el ejemplo de código siguiente se muestra el uso de los operadores de consulta estándar para obtener información sobre una secuencia.</span><span class="sxs-lookup"><span data-stu-id="37d84-123">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>

```vb
Dim sentence = "the quick brown fox jumps over the lazy dog"
' Split the string into individual words to create a collection.
Dim words = sentence.Split(" "c)

Dim query = From word In words
            Group word.ToUpper() By word.Length Into gr = Group
            Order By Length _
            Select Length, GroupedWords = gr

Dim output As New System.Text.StringBuilder
For Each obj In query
    output.AppendLine(String.Format("Words of length {0}:", obj.Length))
    For Each word As String In obj.GroupedWords
        output.AppendLine(word)
    Next
Next

'Display the output
MsgBox(output.ToString())

' This code example produces the following output:
'
' Words of length 3:
' THE
' FOX
' THE
' DOG
' Words of length 4:
' OVER
' LAZY
' Words of length 5:
' QUICK
' BROWN
' JUMPS
```

## <a name="query-expression-syntax"></a><span data-ttu-id="37d84-124">Sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="37d84-124">Query Expression Syntax</span></span>

<span data-ttu-id="37d84-125">Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis especial de palabras clave dedicadas de lenguaje C# y Visual Basic para que se puedan invocar como parte de una *expresión* *de consulta*.</span><span class="sxs-lookup"><span data-stu-id="37d84-125">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="37d84-126">Para obtener más información sobre los operadores de consulta estándar que tienen palabras clave dedicadas y sus sintaxis correspondientes, vea [Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="37d84-126">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md).</span></span>

## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="37d84-127">Extender los operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="37d84-127">Extending the Standard Query Operators</span></span>

<span data-ttu-id="37d84-128">Puede aumentar el conjunto de operadores de consulta estándar creando métodos específicos de dominio que sean adecuados para su tecnología o dominio de destino.</span><span class="sxs-lookup"><span data-stu-id="37d84-128">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="37d84-129">También puede reemplazar los operadores de consulta estándar con sus propias implementaciones que proporcionen otros servicios tales como evaluación remota, traducción de consultas y optimización.</span><span class="sxs-lookup"><span data-stu-id="37d84-129">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="37d84-130">Vea <xref:System.Linq.Enumerable.AsEnumerable%2A> para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="37d84-130">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>

## <a name="related-sections"></a><span data-ttu-id="37d84-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="37d84-131">Related Sections</span></span>

<span data-ttu-id="37d84-132">Los vínculos siguientes le llevan a temas que ofrecen información adicional sobre los distintos operadores de consulta estándar según la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="37d84-132">The following links take you to topics that provide additional information about the various standard query operators based on functionality.</span></span>

- [<span data-ttu-id="37d84-133">Ordenación de datos</span><span class="sxs-lookup"><span data-stu-id="37d84-133">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)

- [<span data-ttu-id="37d84-134">Operaciones Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-134">Set Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/set-operations.md)

- [<span data-ttu-id="37d84-135">Filtrar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-135">Filtering Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/filtering-data.md)

- [<span data-ttu-id="37d84-136">Operaciones cuantificadoras (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-136">Quantifier Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)

- [<span data-ttu-id="37d84-137">Operaciones de proyección (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-137">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)

- [<span data-ttu-id="37d84-138">Creación de particiones de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-138">Partitioning Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/partitioning-data.md)

- [<span data-ttu-id="37d84-139">Operaciones de combinación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-139">Join Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)

- [<span data-ttu-id="37d84-140">Agrupar datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-140">Grouping Data (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/grouping-data.md)

- [<span data-ttu-id="37d84-141">Operaciones de generación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-141">Generation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/generation-operations.md)

- [<span data-ttu-id="37d84-142">Operaciones de igualdad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-142">Equality Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/equality-operations.md)

- [<span data-ttu-id="37d84-143">Operaciones de elementos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-143">Element Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md)

- [<span data-ttu-id="37d84-144">Convertir tipos de datos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-144">Converting Data Types (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)

- [<span data-ttu-id="37d84-145">Operaciones de concatenación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-145">Concatenation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/concatenation-operations.md)

- [<span data-ttu-id="37d84-146">Operaciones de agregación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-146">Aggregation Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)

## <a name="see-also"></a><span data-ttu-id="37d84-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="37d84-147">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="37d84-148">Introducción a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-148">Introduction to LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [<span data-ttu-id="37d84-149">Sintaxis de expresiones de consulta para operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-149">Query Expression Syntax for Standard Query Operators (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="37d84-150">Clasificación de operadores de consulta estándar por modo de ejecución (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37d84-150">Classification of Standard Query Operators by Manner of Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="37d84-151">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="37d84-151">Extension Methods</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
