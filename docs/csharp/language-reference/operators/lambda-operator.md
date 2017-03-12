---
title: "=&gt; (operador) (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "=>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lambda (operador) [C#]"
  - "=> (operador) [C#]"
  - "expresiones lambda [C#], => operador"
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# =&gt; (operador) (Referencia de C#)
El token `=>` se denomina operador lambda.  Se utiliza en *expresiones lambda* para separar las variables de entrada del lado izquierdo del cuerpo lambda del lado derecho.  Las expresiones lambda son expresiones insertadas similares a los métodos anónimos, pero más flexibles; se utilizan mucho en las consultas de LINQ que se expresan en la sintaxis del método.  Para obtener más información, vea [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 El ejemplo siguiente muestra dos maneras de buscar y mostrar la longitud de la cadena más corta de una matriz de cadenas.  La primera parte del ejemplo aplica una expresión lambda \(`w => w.Length`\) a cada elemento de la matriz de `words` y utilice el método de <xref:System.Linq.Enumerable.Min%2A> para encontrar la longitud menor.  Para la comparación, la segunda parte muestra a solución más larga que utiliza sintaxis de consulta para lograr el mismo resultado.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## Comentarios  
 El operador `=>` tiene la misma prioridad que el operador de asignación \(`=`\) y es asociativo por la derecha.  
  
 Puede especificar el tipo de la variable de entrada explícitamente o deja el compilador deducirlo; en cualquier caso, la variable está fuertemente tipada en tiempo de compilación.  Cuando se especifica un tipo, debe agregar el nombre del tipo y el nombre de variable entre paréntesis, como se muestra en el ejemplo siguiente.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Ejemplo  
 El ejemplo siguiente se muestra cómo escribir una expresión lambda para la sobrecarga de <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> de operador de consulta estándar que toma dos argumentos.  Dado que la expresión lambda tiene más de un parámetro, se debe agregar entre paréntesis.  El segundo parámetro, `index`, representa el índice del elemento actual en la colección.  La expresión de `Where` devuelve todas las cadenas cuya longitud sea menor que sus posiciones de índice de la matriz.  
  
```c#  
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
  
    // Compare the following code, which arrives at the same list of short  
    // digits but takes more work to get there.  
    Console.WriteLine("\nExample that uses a for loop:");  
    List<string> shortDigits2 = new List<string>();  
    for (var i = 0; i < digits.Length; i++)  
    {  
        if (digits[i].Length < i)  
            shortDigits2.Add(digits[i]);  
    }  
  
    foreach (var d in shortDigits2)  
    {  
        Console.WriteLine(d);  
    }  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
  
    // Example that uses a for loop:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Expresiones lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)