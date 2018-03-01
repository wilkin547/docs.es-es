---
title: Operador =&gt; (Referencia de C#)
ms.date: 10/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
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
# <a name="gt-operator-c-reference"></a>Operador =&gt; (Referencia de C#)

El `=>` operador se puede usar de dos maneras en C#:

- Como el [operador lambda](#lamba-operator) en un [expresión lambda](../../lambda-expressions.md), separa las variables de entrada desde el cuerpo de la expresión lambda.
 
- En un [definición de cuerpo de la expresión](#expression-body-definition), separa un nombre de miembro de la implementación de un miembro. 

## <a name="lambda-operator"></a>Lambda (operador)

El token `=>` se denomina operador lambda. Se usa en *expresiones lambda* para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho. Las expresiones lambda son expresiones insertadas similares a los métodos anónimos, pero más flexibles. Se usan ampliamente en las consultas LINQ que se expresan en la sintaxis de método. Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 En el ejemplo siguiente se muestran dos maneras de buscar y mostrar la longitud de la cadena más corta en una matriz de cadenas. La primera parte del ejemplo aplica una expresión lambda (`w => w.Length`) a cada elemento de la matriz `words` y, después, usa el método <xref:System.Linq.Enumerable.Min%2A> para buscar la longitud menor. Para comparar, la segunda parte del ejemplo muestra una solución más larga que usa la sintaxis de consulta para hacer lo mismo.  
  
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
  
### <a name="remarks"></a>Comentarios  
 El operador `=>` tiene la misma prioridad que el operador de asignación (`=`) y es asociativo a la derecha.  
  
 Puede especificar explícitamente el tipo de la variable de entrada o dejar que el compilador la deduzca. En cualquier caso, la variable está fuertemente tipada en tiempo de compilación. Cuando especifique un tipo, debe incluir el nombre de tipo y el nombre de variable entre paréntesis, como se muestra en el ejemplo siguiente.  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo escribir una expresión lambda para la sobrecarga del operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> que toma dos argumentos. Dado que la expresión lambda tiene más de un parámetro, los parámetros deben ir entre paréntesis. El segundo parámetro, `index`, representa el índice del elemento actual de la colección. La expresión `Where` devuelve todas las cadenas cuyas longitudes son inferiores a sus posiciones de índice en la matriz.  
  
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
## <a name="expression-body-definition"></a>Definición de cuerpo de la expresión

Una definición de cuerpo de expresión proporciona implementación de un miembro en un formulario muy comprimido y legible. Tiene la siguiente sintaxis:

```csharp
member => expression;
```
donde *expresión* es una expresión válida. Tenga en cuenta que *expresión* puede ser un *expresión de instrucción* sólo si el valor devuelto del miembro del tipo es `void`, o si el miembro es un constructor o un finalizador.

Se admiten las definiciones de cuerpos de expresión para los métodos y las instrucciones get de propiedad a partir de C# 6. Las definiciones de cuerpos de expresión para constructores, finalizadores, instrucciones set de propiedad y los indizadores se admiten a partir de C# 7.

La siguiente es una definición de cuerpo de expresión para un `Person.ToString` método:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Es una versión abreviada de la definición de método siguiente:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Para obtener más información sobre las definiciones de cuerpos de expresión, vea [miembros en el cuerpo expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="see-also"></a>Vea también  
[Referencia de C#](../../../csharp/language-reference/index.md)   
[Guía de programación de C#](../../../csharp/programming-guide/index.md)   
[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[Los miembros en el cuerpo expresión](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).