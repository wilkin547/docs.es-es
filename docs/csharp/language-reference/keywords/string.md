---
title: string (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
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
ms.openlocfilehash: a616808a8e6ff5e259c503c0143db4b8f73bdef2
ms.lasthandoff: 03/13/2017

---
# <a name="string-c-reference"></a>string (Referencia de C#)
El tipo `string` representa una secuencia de cero o más caracteres Unicode. `string` es un alias de <xref:System.String> en .NET Framework.  
  
 Aunque `string` es un tipo de referencia, se definen los operadores de igualdad (`==` y `!=`) para comparar los valores de los objetos `string`, no las referencias. Esto hace que las pruebas de igualdad entre cadenas sean más intuitivas. Por ejemplo:  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 Se muestra "True" y luego "False" porque el contenido de las cadenas es equivalente, pero `a` y `b` no hacen referencia a la misma instancia de cadena.  
  
 El operador + concatena cadenas:  
  
```csharp  
string a = "good " + "morning";  
```  
  
 Crea un objeto de cadena que contiene "good morning".  
  
 Las cadenas son *inmutables*: el contenido de un objeto de cadena no se puede modificar una vez creado el objeto, aunque la sintaxis parezca indicar que se puede hacer. Por ejemplo, al escribir este código, el compilador crea en realidad otro objeto de cadena para almacenar la nueva secuencia de caracteres, y este nuevo objeto se asigna a b. La cadena "h" pasa a ser apta para la recolección de elementos no utilizados.  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 El operador [] puede usarse para acceso de solo lectura a determinados caracteres de un objeto `string`:  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 Los literales de cadena son del tipo `string` y se pueden escribir de dos formas, entre comillas y @-quoted. Los literales de cadena se incluyen entre comillas dobles ("):  
  
```csharp  
"good morning"  // a string literal  
```  
  
 Los literales de cadena pueden contener cualquier literal de carácter. Se incluyen secuencias de escape. En el ejemplo siguiente se usa una secuencia de escape `\\` para la barra diagonal inversa, `\u0066` para la letra f y `\n` para la nueva línea.  
  
```  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  El código de escape `\`u`dddd` (donde `dddd` es un número de cuatro dígitos) representa el carácter Unicode U+`dddd`. También se reconocen los códigos de escape Unicode de 8 dígitos: `\Udddddddd`.  
  
 Los literales de cadena textual empiezan por @ y también se incluyen entre comillas dobles. Por ejemplo:  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 La ventaja de las cadenas textuales es que las secuencias de escape *no* se procesan, lo que facilita la escritura de, por ejemplo, un nombre de archivo completo:  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 Para incluir un signo de comillas dobles en una cadena @-quoted, duplíquelo:  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 Otro uso del símbolo @ se da con identificadores con referencia ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) que son palabras clave de C#.  
  
 Para obtener más información sobre las cadenas en C#, vea [Strings](../../../csharp/programming-guide/strings/index.md) (Cadenas [Guía de programación de C#]).  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Procedimientos recomendados para el uso de cadenas en .NET Framework](http://msdn.microsoft.com/library/b9f0bf53-e2de-4116-8ce9-d4f91a1df4f7)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Reference Types](../../../csharp/language-reference/keywords/reference-types.md)  (Tipos de referencia [Referencia de C#])  
 [Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])  
 [Operaciones básicas de cadenas](http://msdn.microsoft.com/library/8133d357-90b5-4b62-9927-43323d99b6b6)   
 [Creación de nuevas cadenas](http://msdn.microsoft.com/library/06fdf123-2fac-4459-8904-eb48ab908a30)   
 [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)

