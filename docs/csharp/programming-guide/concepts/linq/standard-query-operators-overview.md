---
title: Información general sobre operadores de consulta estándar (C#)
ms.date: 07/20/2015
ms.assetid: 812fa119-5f65-4139-b4fa-55dccd8dc3ac
ms.openlocfilehash: 095a0b7a7a8265f235d28a4634ea82cdcd7a60c0
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990013"
---
# <a name="standard-query-operators-overview-c"></a><span data-ttu-id="a697d-102">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="a697d-102">Standard Query Operators Overview (C#)</span></span>
<span data-ttu-id="a697d-103">Los *operadores de consulta estándar* son los métodos que constituyen el modelo LINQ.</span><span class="sxs-lookup"><span data-stu-id="a697d-103">The *standard query operators* are the methods that form the LINQ pattern.</span></span> <span data-ttu-id="a697d-104">La mayoría de estos métodos funciona en secuencias; donde una secuencia es un objeto cuyo tipo implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> o la interfaz <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="a697d-104">Most of these methods operate on sequences, where a sequence is an object whose type implements the <xref:System.Collections.Generic.IEnumerable%601> interface or the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="a697d-105">Los operadores de consulta estándar ofrecen funcionalidades de consulta, como las funciones de filtrado, proyección, agregación y ordenación, entre otras.</span><span class="sxs-lookup"><span data-stu-id="a697d-105">The standard query operators provide query capabilities including filtering, projection, aggregation, sorting and more.</span></span>  
  
 <span data-ttu-id="a697d-106">Hay dos conjuntos de operadores de consulta estándar de LINQ: uno que actúa sobre objetos de tipo <xref:System.Collections.Generic.IEnumerable%601> y otro sobre objetos de tipo <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="a697d-106">There are two sets of LINQ standard query operators: one that operates on objects of type <xref:System.Collections.Generic.IEnumerable%601>, another that operates on objects of type <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="a697d-107">Los métodos que forman cada conjunto son miembros estáticos de las clases <xref:System.Linq.Enumerable> y <xref:System.Linq.Queryable>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a697d-107">The methods that make up each set are static members of the <xref:System.Linq.Enumerable> and <xref:System.Linq.Queryable> classes, respectively.</span></span> <span data-ttu-id="a697d-108">Se definen como *métodos de extensión* del tipo en el que actúan.</span><span class="sxs-lookup"><span data-stu-id="a697d-108">They are defined as *extension methods* of the type that they operate on.</span></span> <span data-ttu-id="a697d-109">Se puede llamar a los métodos de extensión mediante sintaxis de método estático o sintaxis de método de instancia.</span><span class="sxs-lookup"><span data-stu-id="a697d-109">Extension methods can be called by using either static method syntax or instance method syntax.</span></span>  
  
 <span data-ttu-id="a697d-110">Además, varios métodos de operador de consulta estándar funcionan en tipos distintos de los que se basan en <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="a697d-110">In addition, several standard query operator methods operate on types other than those based on <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="a697d-111">El tipo <xref:System.Linq.Enumerable> define dos métodos que funcionan en objetos de tipo <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="a697d-111">The <xref:System.Linq.Enumerable> type defines two such methods that both operate on objects of type <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="a697d-112">Estos métodos, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> y <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, le permiten habilitar una colección no genérica o no parametrizada para consultarse en el patrón LINQ.</span><span class="sxs-lookup"><span data-stu-id="a697d-112">These methods, <xref:System.Linq.Enumerable.Cast%60%601%28System.Collections.IEnumerable%29> and <xref:System.Linq.Enumerable.OfType%60%601%28System.Collections.IEnumerable%29>, let you enable a non-parameterized, or non-generic, collection to be queried in the LINQ pattern.</span></span> <span data-ttu-id="a697d-113">Para ello, se crea una colección de objetos fuertemente tipados.</span><span class="sxs-lookup"><span data-stu-id="a697d-113">They do this by creating a strongly typed collection of objects.</span></span> <span data-ttu-id="a697d-114">La clase <xref:System.Linq.Queryable> define dos métodos similares, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> y <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, que funcionan en objetos de tipo <xref:System.Linq.Queryable>.</span><span class="sxs-lookup"><span data-stu-id="a697d-114">The <xref:System.Linq.Queryable> class defines two similar methods, <xref:System.Linq.Queryable.Cast%60%601%28System.Linq.IQueryable%29> and <xref:System.Linq.Queryable.OfType%60%601%28System.Linq.IQueryable%29>, that operate on objects of type <xref:System.Linq.Queryable>.</span></span>  
  
 <span data-ttu-id="a697d-115">Los operadores de consulta estándar difieren en sus intervalos de ejecución, dependiendo de que devuelvan un valor singleton o una secuencia de valores.</span><span class="sxs-lookup"><span data-stu-id="a697d-115">The standard query operators differ in the timing of their execution, depending on whether they return a singleton value or a sequence of values.</span></span> <span data-ttu-id="a697d-116">Esos métodos que devuelven un valor singleton (por ejemplo, <xref:System.Linq.Enumerable.Average%2A> y <xref:System.Linq.Enumerable.Sum%2A>) se ejecutan inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="a697d-116">Those methods that return a singleton value (for example, <xref:System.Linq.Enumerable.Average%2A> and <xref:System.Linq.Enumerable.Sum%2A>) execute immediately.</span></span> <span data-ttu-id="a697d-117">Los métodos que devuelven una secuencia aplazan la ejecución de la consulta y devuelven un objeto enumerable.</span><span class="sxs-lookup"><span data-stu-id="a697d-117">Methods that return a sequence defer the query execution and return an enumerable object.</span></span>  
  
 <span data-ttu-id="a697d-118">En el caso de los métodos que actúan en colecciones en memoria, es decir, los métodos que extienden <xref:System.Collections.Generic.IEnumerable%601>, el objeto enumerable devuelto captura los argumentos que se han pasado al método.</span><span class="sxs-lookup"><span data-stu-id="a697d-118">For methods that operate on in-memory collections, that is, those methods that extend <xref:System.Collections.Generic.IEnumerable%601>, the returned enumerable object captures the arguments that were passed to the method.</span></span> <span data-ttu-id="a697d-119">Cuando se enumera ese objeto, se emplea la lógica del operador de consulta y se devuelven los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a697d-119">When that object is enumerated, the logic of the query operator is employed and the query results are returned.</span></span>  
  
 <span data-ttu-id="a697d-120">En cambio, los métodos que extienden <xref:System.Linq.IQueryable%601> no implementan ningún comportamiento de realización de consultas.</span><span class="sxs-lookup"><span data-stu-id="a697d-120">In contrast, methods that extend <xref:System.Linq.IQueryable%601> don't implement any querying behavior.</span></span> <span data-ttu-id="a697d-121">Compilan un árbol de expresión que representa la consulta que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="a697d-121">They build an expression tree that represents the query to be performed.</span></span> <span data-ttu-id="a697d-122">El procesamiento de consultas se controla mediante el objeto <xref:System.Linq.IQueryable%601> de origen.</span><span class="sxs-lookup"><span data-stu-id="a697d-122">The query processing is handled by the source <xref:System.Linq.IQueryable%601> object.</span></span>  
  
 <span data-ttu-id="a697d-123">Las llamadas a métodos de consulta se pueden encadenar juntas en una consulta, lo que permite que las consultas se conviertan en complejas de forma arbitraria.</span><span class="sxs-lookup"><span data-stu-id="a697d-123">Calls to query methods can be chained together in one query, which enables queries to become arbitrarily complex.</span></span>  
  
 <span data-ttu-id="a697d-124">En el ejemplo de código siguiente se muestra el uso de los operadores de consulta estándar para obtener información sobre una secuencia.</span><span class="sxs-lookup"><span data-stu-id="a697d-124">The following code example demonstrates how the standard query operators can be used to obtain information about a sequence.</span></span>  
  
```csharp  
string sentence = "the quick brown fox jumps over the lazy dog";  
// Split the string into individual words to create a collection.  
string[] words = sentence.Split(' ');  
  
// Using query expression syntax.  
var query = from word in words  
            group word.ToUpper() by word.Length into gr  
            orderby gr.Key  
            select new { Length = gr.Key, Words = gr };  
  
// Using method-based query syntax.  
var query2 = words.  
    GroupBy(w => w.Length, w => w.ToUpper()).  
    Select(g => new { Length = g.Key, Words = g }).  
    OrderBy(o => o.Length);  
  
foreach (var obj in query)  
{  
    Console.WriteLine("Words of length {0}:", obj.Length);  
    foreach (string word in obj.Words)  
        Console.WriteLine(word);  
}  
  
// This code example produces the following output:  
//  
// Words of length 3:  
// THE  
// FOX  
// THE  
// DOG  
// Words of length 4:  
// OVER  
// LAZY  
// Words of length 5:  
// QUICK  
// BROWN  
// JUMPS
```  
  
## <a name="query-expression-syntax"></a><span data-ttu-id="a697d-125">Sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="a697d-125">Query Expression Syntax</span></span>  
 <span data-ttu-id="a697d-126">Algunos de los operadores de consulta estándar que se usan con más frecuencia tienen una sintaxis especial de palabras clave dedicadas de lenguaje C# y Visual Basic para que se puedan invocar como parte de una *expresión* *de consulta*.</span><span class="sxs-lookup"><span data-stu-id="a697d-126">Some of the more frequently used standard query operators have dedicated C# and Visual Basic language keyword syntax that enables them to be called as part of a *query* *expression*.</span></span> <span data-ttu-id="a697d-127">Para obtener más información sobre los operadores de consulta estándar que incluyen palabras clave dedicadas y sus sintaxis correspondientes, vea [Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#)](./query-expression-syntax-for-standard-query-operators.md).</span><span class="sxs-lookup"><span data-stu-id="a697d-127">For more information about standard query operators that have dedicated keywords and their corresponding syntaxes, see [Query Expression Syntax for Standard Query Operators (C#)](./query-expression-syntax-for-standard-query-operators.md).</span></span>  
  
## <a name="extending-the-standard-query-operators"></a><span data-ttu-id="a697d-128">Extender los operadores de consulta estándar</span><span class="sxs-lookup"><span data-stu-id="a697d-128">Extending the Standard Query Operators</span></span>  
 <span data-ttu-id="a697d-129">Puede aumentar el conjunto de operadores de consulta estándar creando métodos específicos de dominio que sean adecuados para su tecnología o dominio de destino.</span><span class="sxs-lookup"><span data-stu-id="a697d-129">You can augment the set of standard query operators by creating domain-specific methods that are appropriate for your target domain or technology.</span></span> <span data-ttu-id="a697d-130">También puede reemplazar los operadores de consulta estándar con sus propias implementaciones que proporcionen otros servicios tales como evaluación remota, traducción de consultas y optimización.</span><span class="sxs-lookup"><span data-stu-id="a697d-130">You can also replace the standard query operators with your own implementations that provide additional services such as remote evaluation, query translation, and optimization.</span></span> <span data-ttu-id="a697d-131">Vea <xref:System.Linq.Enumerable.AsEnumerable%2A> para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a697d-131">See <xref:System.Linq.Enumerable.AsEnumerable%2A> for an example.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a697d-132">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a697d-132">Related Sections</span></span>  
 <span data-ttu-id="a697d-133">Los vínculos siguientes llevan a artículos que ofrecen información adicional sobre los distintos operadores de consulta estándar según la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a697d-133">The following links take you to articles that provide additional information about the various standard query operators based on functionality.</span></span>  
  
 <span data-ttu-id="a697d-134">[Ordenación de datos [C#]](./sorting-data.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-134">[Sorting Data (C#)](./sorting-data.md)</span></span>  
  
 <span data-ttu-id="a697d-135">[Operaciones set [C#]](./set-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-135">[Set Operations (C#)](./set-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-136">[Filtrado de datos [C#]](./filtering-data.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-136">[Filtering Data (C#)](./filtering-data.md)</span></span>  
  
 <span data-ttu-id="a697d-137">[Operaciones cuantificadoras [C#]](./quantifier-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-137">[Quantifier Operations (C#)](./quantifier-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-138">[Operaciones de proyección [C#]](./projection-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-138">[Projection Operations (C#)](./projection-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-139">[Realizar particiones de datos [C#]](./partitioning-data.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-139">[Partitioning Data (C#)](./partitioning-data.md)</span></span>  
  
 <span data-ttu-id="a697d-140">[Operaciones de combinación [C#]](./join-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-140">[Join Operations (C#)](./join-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-141">[Agrupar datos [C#]](./grouping-data.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-141">[Grouping Data (C#)](./grouping-data.md)</span></span>  
  
 <span data-ttu-id="a697d-142">[Operaciones de generación [C#]](./generation-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-142">[Generation Operations (C#)](./generation-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-143">[Operaciones de igualdad [C#]](./equality-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-143">[Equality Operations (C#)](./equality-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-144">[Operaciones de elementos [C#]](./element-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-144">[Element Operations (C#)](./element-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-145">[Convertir tipos de datos [C#]](./converting-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-145">[Converting Data Types (C#)](./converting-data-types.md)</span></span>  
  
 <span data-ttu-id="a697d-146">[Operaciones de concatenación [C#]](./concatenation-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-146">[Concatenation Operations (C#)](./concatenation-operations.md)</span></span>  
  
 <span data-ttu-id="a697d-147">[Operaciones de agregación [C#]](./aggregation-operations.md)</span><span class="sxs-lookup"><span data-stu-id="a697d-147">[Aggregation Operations (C#)](./aggregation-operations.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a697d-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="a697d-148">See also</span></span>

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [<span data-ttu-id="a697d-149">Introducción a las consultas LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="a697d-149">Introduction to LINQ Queries (C#)</span></span>](./introduction-to-linq-queries.md)
- [<span data-ttu-id="a697d-150">Sintaxis de las expresiones de consulta para operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="a697d-150">Query Expression Syntax for Standard Query Operators (C#)</span></span>](./query-expression-syntax-for-standard-query-operators.md)
- [<span data-ttu-id="a697d-151">Clasificación de operadores de consulta estándar por modo de ejecución (C#)</span><span class="sxs-lookup"><span data-stu-id="a697d-151">Classification of Standard Query Operators by Manner of Execution (C#)</span></span>](./classification-of-standard-query-operators-by-manner-of-execution.md)
- [<span data-ttu-id="a697d-152">Métodos de extensión</span><span class="sxs-lookup"><span data-stu-id="a697d-152">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
