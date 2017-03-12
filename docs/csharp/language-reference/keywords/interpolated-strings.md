---
title: "Cadenas interpoladas (referencia de C# y Visual Basic) | Microsoft Docs"
ms.date: "2017-02-03"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Cadenas interpoladas (referencia de C# y Visual Basic)
Se utiliza para construir cadenas.  Una expresión de cadena interpolada es similar a una cadena de plantilla que contiene expresiones.  Una expresión de cadena interpolada crea una cadena reemplazando las expresiones incluidas por las representaciones ToString de los resultados de las expresiones.  Una cadena interpolada es más fácil de entender con respecto a los argumentos que el [Formatos compuestos](../Topic/Composite%20Formatting.md).  Este es un ejemplo de una cadena interpolada:  
  
```c#  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")  
```  
  
 La estructura de una cadena interpolada es la siguiente:  
  
```  
$ " <text> { <interpolation-expression> <optional-comma-field-width> <optional-colon-format> } <text> ... } "  
```  
  
 Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.  Al ejecutarse, su programa ejecutaría el código con el literal de cadena interpolada, el código calcula un nuevo literal de cadena evaluando las expresiones de interpolación.  Este cálculo se produce cada vez que se ejecuta el código con la cadena interpolada.  
  
 Para incluir una llave \("{" o "}"\) en una cadena interpolada, use dos llaves, "{{" o "}}".  Consulte la sección Conversiones implícitas para obtener más detalles.  
  
## Conversiones implícitas  
 Hay conversiones de tipo implícito de una cadena interpolada:  
  
```c#  
var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}"  
  
```  
  
 El primer ejemplo genera un valor de `string` donde se hayan calculado todos los valores de interpolación de cadena.  Es el resultado final y es de tipo cadena.  Todas las apariciones de llaves dobles \("{{" y "}}"\) se convierten en una única llave.  
  
 El segundo ejemplo genera una variable <xref:System.IFormattable> que le permite convertir la cadena con contexto invariable.  Esto es útil para obtener formatos de numéricos y de datos correctos en diferentes idiomas.  Todas las apariciones de llaves dobles \("{{" y "}}"\) permanecen como llaves dobles hasta que dé formato a la cadena mediante ToString.  Todas las expresiones de interpolación incluidas se convierten en {0}, \\{1\\} y así sucesivamente.  
  
```c#  
s.ToString(null, System.Globalization.CultureInfo.InvariantCulture);  
```  
  
 El tercer ejemplo genera un <xref:System.FormattableString>, que le permite inspeccionar los objetos que se generen a partir de los cálculos de interpolación.  Inspeccionar los objetos y cómo se presentan como cadenas podría, por ejemplo, ayudarle a protegerse frente a un ataque de inyección si estuviese compilando una consulta.  Con <xref:System.FormattableString> dispone de operaciones de conveniencia para generar los resultados de cadena InvariantCulture y CurrentCulture.  Todas las apariciones de llaves dobles \("{{" y "}}"\) permanecen como llaves dobles hasta que dé formato.  Todas las expresiones de interpolación incluidas se convierten en {0}, \\{1\\} y así sucesivamente.  
  
## Ejemplos  
  
```c#  
$"Name = {name}, hours = {hours:hh}" var s = $"hello, {name}" System.IFormattable s = $"Hello, {name}" System.FormattableString s = $"Hello, {name}" $"{person.Name, 20} is {person.Age:D3} year {(p.Age == 1 ? "" : "s")} old."  
  
```  
  
 No es necesario entrecomillar los caracteres de comillas dentro de las expresiones de interpolación incluidas porque las expresiones de cadenas interpoladas comienzan por $ y el compilador examina las expresiones de interpolación incluidas como texto equilibrado hasta que encuentre una coma, dos puntos o una llave de cierre.  Por las mismas razones, el último ejemplo utiliza paréntesis para permitir que la expresión condicional \(`p.Age == 1 ? "" : "s"`\) esté dentro de la expresión de interpolación sin que los dos puntos inicien una especificación de formato.  Fuera de la expresión de interpolación incluida \(pero aún dentro de la expresión de cadena interpolad\) escape los caracteres de comillas como lo haría normalmente.  
  
## Sintaxis  
  
```  
expression: interpolated-string-expression interpolated-string-expression: interpolated-string-start interpolations interpolated-string-end interpolations: single-interpolation single-interpolation interpolated-string-mid interpolations single-interpolation: interpolation-start interpolation-start : regular-string-literal interpolation-start: expression expression , expression  
  
```  
  
## Especificaciones del lenguaje  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
 Para obtener más información, vea [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md).  
  
## Vea también  
 <xref:System.IFormattable?displayProperty=fullName>   
 <xref:System.FormattableString?displayProperty=fullName>   
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)   
 [Guía de programación en Visual Basic](../../../visual-basic/programming-guide/index.md)