---
title: Operador =&gt; - Referencia de C#
ms.custom: seodec18
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: 8641757d9252c88cf30595cec06d27b964e4d95c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415291"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="0728c-102">Operador =&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0728c-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="0728c-103">El operador `=>` se puede usar de dos maneras en C#:</span><span class="sxs-lookup"><span data-stu-id="0728c-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="0728c-104">Como [operador lambda](#lambda-operator) en una [expresión lambda](../../lambda-expressions.md), para separar las variables de entrada del cuerpo de lambda.</span><span class="sxs-lookup"><span data-stu-id="0728c-104">As the [lambda operator](#lambda-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="0728c-105">En una [definición de cuerpo de expresiones](#expression-body-definition), para separar un nombre de miembro de la implementación de miembro.</span><span class="sxs-lookup"><span data-stu-id="0728c-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="0728c-106">Operador lambda</span><span class="sxs-lookup"><span data-stu-id="0728c-106">Lambda operator</span></span>

<span data-ttu-id="0728c-107">El token `=>` se denomina operador lambda.</span><span class="sxs-lookup"><span data-stu-id="0728c-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="0728c-108">Se usa en *expresiones lambda* para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="0728c-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="0728c-109">Las expresiones lambda son expresiones insertadas similares a los métodos anónimos, pero más flexibles. Se usan ampliamente en las consultas LINQ que se expresan en la sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="0728c-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="0728c-110">Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0728c-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="0728c-111">En el ejemplo siguiente se muestran dos maneras de buscar y mostrar la longitud de la cadena más corta en una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="0728c-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="0728c-112">La primera parte del ejemplo aplica una expresión lambda (`w => w.Length`) a cada elemento de la matriz `words` y, después, usa el método <xref:System.Linq.Enumerable.Min%2A> para buscar la longitud menor.</span><span class="sxs-lookup"><span data-stu-id="0728c-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="0728c-113">Para comparar, la segunda parte del ejemplo muestra una solución más larga que usa la sintaxis de consulta para hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="0728c-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
### <a name="remarks"></a><span data-ttu-id="0728c-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0728c-114">Remarks</span></span>  
 <span data-ttu-id="0728c-115">El operador `=>` tiene la misma prioridad que el operador de asignación (`=`) y es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="0728c-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="0728c-116">Puede especificar explícitamente el tipo de la variable de entrada o dejar que el compilador la deduzca. En cualquier caso, la variable está fuertemente tipada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0728c-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="0728c-117">Cuando especifique un tipo, debe incluir el nombre de tipo y el nombre de variable entre paréntesis, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0728c-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="0728c-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0728c-118">Example</span></span>  
 <span data-ttu-id="0728c-119">En el ejemplo siguiente se muestra cómo escribir una expresión lambda para la sobrecarga del operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> que toma dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="0728c-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="0728c-120">Dado que la expresión lambda tiene más de un parámetro, los parámetros deben ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="0728c-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="0728c-121">El segundo parámetro, `index`, representa el índice del elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="0728c-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="0728c-122">La expresión `Where` devuelve todas las cadenas cuyas longitudes son inferiores a sus posiciones de índice en la matriz.</span><span class="sxs-lookup"><span data-stu-id="0728c-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
## <a name="expression-body-definition"></a><span data-ttu-id="0728c-123">Definición de cuerpo de expresiones</span><span class="sxs-lookup"><span data-stu-id="0728c-123">Expression body definition</span></span>

<span data-ttu-id="0728c-124">Una definición de cuerpo de expresiones proporciona la implementación de un miembro de una forma muy concisa y legible.</span><span class="sxs-lookup"><span data-stu-id="0728c-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="0728c-125">Presenta la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="0728c-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="0728c-126">donde *expresión* es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="0728c-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="0728c-127">Cabe mencionar que *expression* puede ser una *expresión de instrucción* únicamente si el tipo de valor devuelto del miembro es `void` o si el miembro es un constructor o un finalizador.</span><span class="sxs-lookup"><span data-stu-id="0728c-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="0728c-128">Desde C# 6, se admite el uso de definiciones de cuerpos de expresiones en métodos e instrucciones de propiedad get.</span><span class="sxs-lookup"><span data-stu-id="0728c-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="0728c-129">Desde C# 7, se admite el uso de definiciones de cuerpos de expresiones en constructores, finalizadores, instrucciones propiedad set e indizadores.</span><span class="sxs-lookup"><span data-stu-id="0728c-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="0728c-130">Esta es una definición de cuerpo de expresiones de un método `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="0728c-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="0728c-131">Se trata de una versión abreviada de la siguiente definición de método:</span><span class="sxs-lookup"><span data-stu-id="0728c-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="0728c-132">Para más información sobre las definiciones de cuerpos de expresiones, vea [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) (Miembros con cuerpos de expresiones).</span><span class="sxs-lookup"><span data-stu-id="0728c-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0728c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="0728c-133">See Also</span></span>

- [<span data-ttu-id="0728c-134">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0728c-134">C# Reference</span></span>](../../../csharp/language-reference/index.md)   
- [<span data-ttu-id="0728c-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0728c-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)   
- [<span data-ttu-id="0728c-136">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="0728c-136">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
- <span data-ttu-id="0728c-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) (Miembros con cuerpos de expresiones).</span><span class="sxs-lookup"><span data-stu-id="0728c-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>
