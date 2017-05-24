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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 737a0902a0cb010a74b59560abe43f5cfb6550db
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

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
 [Procedimientos recomendados para el uso de cadenas en .NET Framework](../../../standard/base-types/best-practices-strings.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Reference Types](../../../csharp/language-reference/keywords/reference-types.md)  (Tipos de referencia [Referencia de C#])  
 [Value Types](../../../csharp/language-reference/keywords/value-types.md)  (Tipos de valor [Referencia de C#])  
 [Operaciones básicas de cadenas](../../../standard/base-types/basic-string-operations.md)   
 [Creación de nuevas cadenas](../../../standard/base-types/creating-new.md)   
 [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)

