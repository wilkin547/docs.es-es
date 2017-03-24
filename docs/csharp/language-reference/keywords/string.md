---
title: "string (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "string"
  - "string_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "cadenas [C#], referencia"
  - "@ (literal de cadena)"
  - "literales de cadena [C#]"
  - "string (palabra clave) [C#]"
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# string (Referencia de C#)
El tipo `string` representa una secuencia de cero o más caracteres Unicode.  `string` es un alias de <xref:System.String> en .NET Framework.  
  
 Aunque `string` es un tipo de referencia, los operadores de igualdad \(`==` y `!=`\) se definen para comparar los valores de objetos `string`, no las referencias.  De esta forma, es más intuitivo comprobar la igualdad entre cadenas.  Por ejemplo:  
  
```c#  
  
      string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 Esto presenta "True" y, después, "False" porque el contenido de las cadenas es equivalente, pero `a` y `b` no hacen referencia a la misma instancia de cadena.  
  
 El operador \+ concatena cadenas:  
  
```c#  
  
string a = "good " + "morning";  
```  
  
 Esto crea un objeto de tipo string que contiene "good morning".  
  
 Las cadenas son *inmutables*: no se puede cambiar el contenido de un objeto de tipo string una vez creado el objeto, aunque pudiera parecer por la sintaxis utilizada que es posible realizar esta operación.  Por ejemplo, al escribir este código, el compilador crea en realidad un nuevo objeto de tipo string para almacenar la nueva secuencia de caracteres, y el nuevo objeto se asigna a b.  La cadena "h" es elegible para la recolección de elementos no utilizados.  
  
```c#  
  
      string b = "h";  
b += "ello";  
```  
  
 El operador \[\] se puede utilizar para tener acceso de sólo lectura a caracteres individuales de un objeto `string`:  
  
```c#  
  
      string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 Los literales de cadena son objetos de tipo `string` que se pueden escribir de dos formas: entre comillas o entre comillas y precedidos de @.  Los literales de cadena se deben encerrar entre comillas \("\):  
  
```c#  
"good morning"  // a string literal  
```  
  
 Los literales de cadena pueden contener cualquier literal de carácter.  Se incluyen las secuencias de escape.  En el siguiente ejemplo, se usa la secuencia de escape `\\` para la barra diagonal inversa, `\u0066` para la letra f y `\n` para una nueva línea.  
  
```  
  
      string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  El código de escape `\`u`dddd` \(donde `dddd` es un número de cuatro dígitos\) representa el carácter Unicode U\+`dddd`.  También se reconocen los códigos de escape Unicode de 8 dígitos: `\Udddddddd`.  
  
 Los literales de cadena textuales empiezan con @ y se encierran entre comillas dobles.  Por ejemplo:  
  
```c#  
@"good morning"  // a string literal  
```  
  
 La ventaja de las cadenas textuales es que las secuencias de escape *no* se procesan, lo que facilita la escritura, por ejemplo, de un nombre de archivo completo:  
  
```c#  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 Para incluir comillas tipográficas en una cadena precedida del símbolo @, escriba las comillas dos veces:  
  
```c#  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 Otro uso del símbolo @ consiste en utilizar identificadores de referencia \([\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)\) que sean palabras clave de C\#.  
  
 Para obtener más información sobre las cadenas en C\#, vea [Cadenas](../../../csharp/programming-guide/strings/index.md).  
  
## Ejemplo  
 [!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Procedimientos recomendados para el uso de cadenas](../Topic/Best%20Practices%20for%20Using%20Strings%20in%20the%20.NET%20Framework.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md)   
 [Tipos de valor](../../../csharp/language-reference/keywords/value-types.md)   
 [Operaciones básicas de cadenas](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)   
 [Crear cadenas nuevas](../Topic/Creating%20New%20Strings%20in%20the%20.NET%20Framework.md)   
 [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)