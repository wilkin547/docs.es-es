---
title: Operador =&gt; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 45d4753724ed094408e8cbc5353998a67071b0e4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="afab0-102">Operador =&gt; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="afab0-102">=&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="afab0-103">El token `=>` se denomina operador lambda.</span><span class="sxs-lookup"><span data-stu-id="afab0-103">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="afab0-104">Se usa en *expresiones lambda* para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho.</span><span class="sxs-lookup"><span data-stu-id="afab0-104">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="afab0-105">Las expresiones lambda son expresiones insertadas similares a los métodos anónimos, pero más flexibles. Se usan ampliamente en las consultas LINQ que se expresan en la sintaxis de método.</span><span class="sxs-lookup"><span data-stu-id="afab0-105">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="afab0-106">Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="afab0-106">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="afab0-107">En el ejemplo siguiente se muestran dos maneras de buscar y mostrar la longitud de la cadena más corta en una matriz de cadenas.</span><span class="sxs-lookup"><span data-stu-id="afab0-107">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="afab0-108">La primera parte del ejemplo aplica una expresión lambda (`w => w.Length`) a cada elemento de la matriz `words` y, después, usa el método <xref:System.Linq.Enumerable.Min%2A> para buscar la longitud menor.</span><span class="sxs-lookup"><span data-stu-id="afab0-108">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="afab0-109">Para comparar, la segunda parte del ejemplo muestra una solución más larga que usa la sintaxis de consulta para hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="afab0-109">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="afab0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="afab0-110">Remarks</span></span>  
 <span data-ttu-id="afab0-111">El operador `=>` tiene la misma prioridad que el operador de asignación (`=`) y es asociativo a la derecha.</span><span class="sxs-lookup"><span data-stu-id="afab0-111">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="afab0-112">Puede especificar explícitamente el tipo de la variable de entrada o dejar que el compilador la deduzca. En cualquier caso, la variable está fuertemente tipada en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="afab0-112">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="afab0-113">Cuando especifique un tipo, debe incluir el nombre de tipo y el nombre de variable entre paréntesis, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="afab0-113">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a><span data-ttu-id="afab0-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afab0-114">Example</span></span>  
 <span data-ttu-id="afab0-115">En el ejemplo siguiente se muestra cómo escribir una expresión lambda para la sobrecarga del operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> que toma dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="afab0-115">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> that takes two arguments.</span></span> <span data-ttu-id="afab0-116">Dado que la expresión lambda tiene más de un parámetro, los parámetros deben ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="afab0-116">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="afab0-117">El segundo parámetro, `index`, representa el índice del elemento actual de la colección.</span><span class="sxs-lookup"><span data-stu-id="afab0-117">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="afab0-118">La expresión `Where` devuelve todas las cadenas cuyas longitudes son inferiores a sus posiciones de índice en la matriz.</span><span class="sxs-lookup"><span data-stu-id="afab0-118">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afab0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="afab0-119">See Also</span></span>  
 <span data-ttu-id="afab0-120">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="afab0-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="afab0-121">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="afab0-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="afab0-122">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="afab0-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

