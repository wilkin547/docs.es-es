---
title: Operador =&gt; (Referencia de C#)
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: d1565e262fbd3ebcee2d1576a2a0c8ed3ba8ce38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="gt-operator-c-reference"></a>Operador =&gt; (Referencia de C#)

El operador `=>` se puede usar de dos maneras en C#:

- Como [operador lambda](#lamba-operator) en una [expresión lambda](../../lambda-expressions.md), para separar las variables de entrada del cuerpo de lambda.
 
- En una [definición de cuerpo de expresiones](#expression-body-definition), para separar un nombre de miembro de la implementación de miembro. 

## <a name="lambda-operator"></a>Operador lambda

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
## <a name="expression-body-definition"></a>Definición de cuerpo de expresiones

Una definición de cuerpo de expresiones proporciona la implementación de un miembro de una forma muy concisa y legible. Presenta la siguiente sintaxis general:

```csharp
member => expression;
```
donde *expresión* es una expresión válida. Cabe mencionar que *expression* puede ser una *expresión de instrucción* únicamente si el tipo de valor devuelto del miembro es `void` o si el miembro es un constructor o un finalizador.

Desde C# 6, se admite el uso de definiciones de cuerpos de expresiones en métodos e instrucciones de propiedad get. Desde C# 7, se admite el uso de definiciones de cuerpos de expresiones en constructores, finalizadores, instrucciones propiedad set e indizadores.

Esta es una definición de cuerpo de expresiones de un método `Person.ToString`:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

Se trata de una versión abreviada de la siguiente definición de método:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Para más información sobre las definiciones de cuerpos de expresiones, vea [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) (Miembros con cuerpos de expresiones).

## <a name="see-also"></a>Vea también  
[Referencia de C#](../../../csharp/language-reference/index.md)   
[Guía de programación de C#](../../../csharp/programming-guide/index.md)   
[Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md) (Miembros con cuerpos de expresiones).