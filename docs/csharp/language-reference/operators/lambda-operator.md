---
title: Operador =&gt; (Referencia de C#)
ms.date: 10/02/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="51b86-102">Operador =&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="51b86-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="51b86-103">El `=>` operador se puede usar de dos maneras en C#:</span><span class="sxs-lookup"><span data-stu-id="51b86-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="51b86-104">Como el [operador lambda](#lamba-operator) en un [expresión lambda](../../lambda-expressions.md), separa las variables de entrada desde el cuerpo de la expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="51b86-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="51b86-105">En un [definición de cuerpo de la expresión](#expression-body-definition), separa un nombre de miembro de la implementación de un miembro.</span><span class="sxs-lookup"><span data-stu-id="51b86-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="51b86-106">Lambda (operador)</span><span class="sxs-lookup"><span data-stu-id="51b86-106">Lambda operator</span></span>

<span data-ttu-id="51b86-107">El token `=>` se denomina operador lambda.</span><span class="sxs-lookup"><span data-stu-id="51b86-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="51b86-108">Se usa en *expresiones lambda* para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="51b86-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="51b86-109">Las expresiones lambda son expresiones insertadas similares a los métodos anónimos, pero más flexibles. Se usan ampliamente en las consultas LINQ que se expresan en la sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="51b86-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="51b86-110">Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="51b86-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="51b86-111">En el ejemplo siguiente se muestran dos maneras de buscar y mostrar la longitud de la cadena más corta en una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="51b86-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="51b86-112">La primera parte del ejemplo aplica una expresión lambda (`w => w.Length`) a cada elemento de la matriz `words` y, después, usa el método <xref:System.Linq.Enumerable.Min%2A> para buscar la longitud menor.</span><span class="sxs-lookup"><span data-stu-id="51b86-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="51b86-113">Para comparar, la segunda parte del ejemplo muestra una solución más larga que usa la sintaxis de consulta para hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="51b86-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
### <a name="remarks"></a><span data-ttu-id="51b86-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51b86-114">Remarks</span></span>  
 <span data-ttu-id="51b86-115">El operador `=>` tiene la misma prioridad que el operador de asignación (`=`) y es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="51b86-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="51b86-116">Puede especificar explícitamente el tipo de la variable de entrada o dejar que el compilador la deduzca. En cualquier caso, la variable está fuertemente tipada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="51b86-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="51b86-117">Cuando especifique un tipo, debe incluir el nombre de tipo y el nombre de variable entre paréntesis, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="51b86-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="51b86-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51b86-118">Example</span></span>  
 <span data-ttu-id="51b86-119">En el ejemplo siguiente se muestra cómo escribir una expresión lambda para la sobrecarga del operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> que toma dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="51b86-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="51b86-120">Dado que la expresión lambda tiene más de un parámetro, los parámetros deben ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="51b86-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="51b86-121">El segundo parámetro, `index`, representa el índice del elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="51b86-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="51b86-122">La expresión `Where` devuelve todas las cadenas cuyas longitudes son inferiores a sus posiciones de índice en la matriz.</span><span class="sxs-lookup"><span data-stu-id="51b86-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
## <a name="expression-body-definition"></a><span data-ttu-id="51b86-123">Definición de cuerpo de la expresión</span><span class="sxs-lookup"><span data-stu-id="51b86-123">Expression body definition</span></span>

<span data-ttu-id="51b86-124">Una definición de cuerpo de expresión proporciona implementación de un miembro en un formulario muy comprimido y legible.</span><span class="sxs-lookup"><span data-stu-id="51b86-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="51b86-125">Tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="51b86-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="51b86-126">donde *expresión* es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="51b86-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="51b86-127">Tenga en cuenta que *expresión* puede ser un *expresión de instrucción* sólo si el valor devuelto del miembro del tipo es `void`, o si el miembro es un constructor o un finalizador.</span><span class="sxs-lookup"><span data-stu-id="51b86-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="51b86-128">Se admiten las definiciones de cuerpos de expresión para los métodos y las instrucciones get de propiedad a partir de C# 6.</span><span class="sxs-lookup"><span data-stu-id="51b86-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="51b86-129">Las definiciones de cuerpos de expresión para constructores, finalizadores, instrucciones set de propiedad y los indizadores se admiten a partir de C# 7.</span><span class="sxs-lookup"><span data-stu-id="51b86-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="51b86-130">La siguiente es una definición de cuerpo de expresión para un `Person.ToString` método:</span><span class="sxs-lookup"><span data-stu-id="51b86-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="51b86-131">Es una versión abreviada de la definición de método siguiente:</span><span class="sxs-lookup"><span data-stu-id="51b86-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="51b86-132">Para obtener más información sobre las definiciones de cuerpos de expresión, vea [miembros en el cuerpo expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="51b86-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="51b86-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="51b86-133">See Also</span></span>  
<span data-ttu-id="51b86-134">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="51b86-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="51b86-135">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="51b86-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
<span data-ttu-id="51b86-136">[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="51b86-136">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
<span data-ttu-id="51b86-137">[Los miembros en el cuerpo expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="51b86-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>