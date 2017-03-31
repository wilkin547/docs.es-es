---
title: Operador =&gt; (Referencia de C#) | Microsoft Docs
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a75967e61d2c674e87e321de1fb6e4062cca4f19
ms.lasthandoff: 03/13/2017

---
# <a name="gt-operator-c-reference"></a>Operador =&gt; (Referencia de C#)
El token `=>` se denomina operador lambda. Se usa en *expresiones lambda* para separar las variables de entrada del lado izquierdo y el cuerpo lambda del lado derecho. Las expresiones lambda son expresiones insertadas similares a los métodos anónimos, pero más flexibles. Se usan ampliamente en las consultas LINQ que se expresan en la sintaxis de método. Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 En el ejemplo siguiente se muestran dos maneras de buscar y mostrar la longitud de la cadena más corta en una matriz de cadenas. La primera parte del ejemplo aplica una expresión lambda (`w => w.Length`) a cada elemento de la matriz `words` y, después, usa el método <xref:System.Linq.Enumerable.Min%2A> para buscar la longitud menor. Para comparar, la segunda parte del ejemplo muestra una solución más larga que usa la sintaxis de consulta para hacer lo mismo.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="remarks"></a>Comentarios  
 El operador `=>` tiene la misma prioridad que el operador de asignación (`=`) y es asociativo a la derecha.  
  
 Puede especificar explícitamente el tipo de la variable de entrada o dejar que el compilador la deduzca. En cualquier caso, la variable está fuertemente tipada en tiempo de compilación. Cuando especifique un tipo, debe incluir el nombre de tipo y el nombre de variable entre paréntesis, como se muestra en el ejemplo siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo escribir una expresión lambda para la sobrecarga del operador de consulta estándar <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> que toma dos argumentos. Dado que la expresión lambda tiene más de un parámetro, los parámetros deben ir entre paréntesis. El segundo parámetro, `index`, representa el índice del elemento actual de la colección. La expresión `Where` devuelve todas las cadenas cuyas longitudes son inferiores a sus posiciones de índice en la matriz.  
  
```cs  
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
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
