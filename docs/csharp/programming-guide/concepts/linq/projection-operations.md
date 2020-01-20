---
title: Operaciones de proyección (C#)
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: a2a2ae762d63d5ff26c7018caef1a83558042fb5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346522"
---
# <a name="projection-operations-c"></a><span data-ttu-id="d47c2-102">Operaciones de proyección (C#)</span><span class="sxs-lookup"><span data-stu-id="d47c2-102">Projection Operations (C#)</span></span>
<span data-ttu-id="d47c2-103">El término "proyección" hace referencia a la operación de transformar un objeto en una nueva forma que, a menudo, consta solo de aquellas propiedades que se usarán posteriormente.</span><span class="sxs-lookup"><span data-stu-id="d47c2-103">Projection refers to the operation of transforming an object into a new form that often consists only of those properties that will be subsequently used.</span></span> <span data-ttu-id="d47c2-104">Utilizando la proyección, puede construir un tipo nuevo creado a partir de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="d47c2-104">By using projection, you can construct a new type that is built from each object.</span></span> <span data-ttu-id="d47c2-105">Se puede proyectar una propiedad y realizar una función matemática en ella.</span><span class="sxs-lookup"><span data-stu-id="d47c2-105">You can project a property and perform a mathematical function on it.</span></span> <span data-ttu-id="d47c2-106">También puede proyectar el objeto original sin cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="d47c2-106">You can also project the original object without changing it.</span></span>  
  
 <span data-ttu-id="d47c2-107">Los métodos del operador de consulta estándar que realizan proyecciones se indican en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="d47c2-107">The standard query operator methods that perform projection are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d47c2-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="d47c2-108">Methods</span></span>  
  
|<span data-ttu-id="d47c2-109">Nombre del método</span><span class="sxs-lookup"><span data-stu-id="d47c2-109">Method Name</span></span>|<span data-ttu-id="d47c2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d47c2-110">Description</span></span>|<span data-ttu-id="d47c2-111">Sintaxis de la expresión de consulta de C#</span><span class="sxs-lookup"><span data-stu-id="d47c2-111">C# Query Expression Syntax</span></span>|<span data-ttu-id="d47c2-112">Más información</span><span class="sxs-lookup"><span data-stu-id="d47c2-112">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="d47c2-113">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="d47c2-113">Select</span></span>|<span data-ttu-id="d47c2-114">Proyecta valores basados en una función de transformación.</span><span class="sxs-lookup"><span data-stu-id="d47c2-114">Projects values that are based on a transform function.</span></span>|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="d47c2-115">SelectMany</span><span class="sxs-lookup"><span data-stu-id="d47c2-115">SelectMany</span></span>|<span data-ttu-id="d47c2-116">Proyecta secuencias de valores que se basan en una función de transformación y después los convierte en una secuencia.</span><span class="sxs-lookup"><span data-stu-id="d47c2-116">Projects sequences of values that are based on a transform function and then flattens them into one sequence.</span></span>|<span data-ttu-id="d47c2-117">Use varias cláusulas `from`</span><span class="sxs-lookup"><span data-stu-id="d47c2-117">Use multiple `from` clauses</span></span>|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="d47c2-118">Ejemplos de sintaxis de expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="d47c2-118">Query Expression Syntax Examples</span></span>  
  
### <a name="select"></a><span data-ttu-id="d47c2-119">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="d47c2-119">Select</span></span>  
 <span data-ttu-id="d47c2-120">En el ejemplo siguiente se usa la cláusula `select` para proyectar la primera letra de cada cadena de una lista de cadenas.</span><span class="sxs-lookup"><span data-stu-id="d47c2-120">The following example uses the `select` clause to project the first letter from each string in a list of strings.</span></span>  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a><span data-ttu-id="d47c2-121">SelectMany</span><span class="sxs-lookup"><span data-stu-id="d47c2-121">SelectMany</span></span>  
 <span data-ttu-id="d47c2-122">En el ejemplo siguiente se usan varias cláusulas `from` para proyectar cada palabra de todas las cadenas de una lista de cadenas.</span><span class="sxs-lookup"><span data-stu-id="d47c2-122">The following example uses multiple `from` clauses  to project each word from each string in a list of strings.</span></span>  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a><span data-ttu-id="d47c2-123">Select frente a SelectMany</span><span class="sxs-lookup"><span data-stu-id="d47c2-123">Select versus SelectMany</span></span>  
 <span data-ttu-id="d47c2-124">La función tanto de `Select()` como de `SelectMany()` consiste en generar un valor (o valores) de resultado a partir de valores de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-124">The work of both `Select()` and `SelectMany()` is to produce a result value (or values) from source values.</span></span> <span data-ttu-id="d47c2-125">`Select()` genera un valor de resultado para cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-125">`Select()` produces one result value for every source value.</span></span> <span data-ttu-id="d47c2-126">El resultado global, por tanto, es una colección que tiene el mismo número de elementos que la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-126">The overall result is therefore a collection that has the same number of elements as the source collection.</span></span> <span data-ttu-id="d47c2-127">En cambio, `SelectMany()` genera un resultado global único que contiene subcolecciones concatenadas procedentes de cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-127">In contrast, `SelectMany()` produces a single overall result that contains concatenated sub-collections from each source value.</span></span> <span data-ttu-id="d47c2-128">La función de transformación que se pasa como argumento a `SelectMany()` debe devolver una secuencia enumerable de valores para cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-128">The transform function that is passed as an argument to `SelectMany()` must return an enumerable sequence of values for each source value.</span></span> <span data-ttu-id="d47c2-129">Luego, `SelectMany()` concatena estas secuencias enumerables para crear una secuencia de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="d47c2-129">These enumerable sequences are then concatenated by `SelectMany()` to create one large sequence.</span></span>  
  
 <span data-ttu-id="d47c2-130">Las dos ilustraciones siguientes muestran la diferencia conceptual entre las acciones de estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="d47c2-130">The following two illustrations show the conceptual difference between the actions of these two methods.</span></span> <span data-ttu-id="d47c2-131">En cada caso, se supone que la función de selector (transformación) selecciona la matriz de flores de cada valor de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-131">In each case, assume that the selector (transform) function selects the array of flowers from each source value.</span></span>  
  
 <span data-ttu-id="d47c2-132">En esta ilustración se muestra cómo `Select()` devuelve una colección que tiene el mismo número de elementos que la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-132">This illustration depicts how `Select()` returns a collection that has the same number of elements as the source collection.</span></span>  
  
 ![Gráfico en el que se muestra la acción Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 <span data-ttu-id="d47c2-134">En esta ilustración se muestra cómo `SelectMany()` concatena la secuencia intermedia de matrices en un valor de resultado final que contiene cada uno de los valores de todas las matrices intermedias.</span><span class="sxs-lookup"><span data-stu-id="d47c2-134">This illustration depicts how `SelectMany()` concatenates the intermediate sequence of arrays into one final result value that contains each value from each intermediate array.</span></span>  
  
 ![Gráfico en el que se muestra la acción SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a><span data-ttu-id="d47c2-136">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="d47c2-136">Code Example</span></span>  
 <span data-ttu-id="d47c2-137">En el ejemplo siguiente se compara el comportamiento de `Select()` y `SelectMany()`.</span><span class="sxs-lookup"><span data-stu-id="d47c2-137">The following example compares the behavior of `Select()` and `SelectMany()`.</span></span> <span data-ttu-id="d47c2-138">El código crea un "ramo" de flores tomando los dos primeros elementos de cada lista de nombres de flores de la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="d47c2-138">The code creates a "bouquet" of flowers by taking the first two items from each list of flower names in the source collection.</span></span> <span data-ttu-id="d47c2-139">En este ejemplo, el "valor único" que la función de transformación <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> usa es una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="d47c2-139">In this example, the "single value" that the transform function <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> uses is itself a collection of values.</span></span> <span data-ttu-id="d47c2-140">Para ello, se requiere el bucle adicional `foreach` a fin de enumerar cada una de las cadenas de cada subsecuencia.</span><span class="sxs-lookup"><span data-stu-id="d47c2-140">This requires the extra `foreach` loop in order to enumerate each string in each sub-sequence.</span></span>  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********              
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d47c2-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="d47c2-141">See also</span></span>

- <xref:System.Linq>
- <span data-ttu-id="d47c2-142">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="d47c2-142">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="d47c2-143">select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="d47c2-143">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
- [<span data-ttu-id="d47c2-144">Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d47c2-144">How to populate object collections from multiple sources (LINQ) (C#)</span></span>](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [<span data-ttu-id="d47c2-145">Procedimiento para dividir un archivo en muchos mediante grupos (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="d47c2-145">How to split a file into many files by using groups (LINQ) (C#)</span></span>](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
