---
title: Cadenas interpoladas (C#)
ms.date: 2017-02-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
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
ms.openlocfilehash: 29790cadd30e9aca56d7ba4c8d7a945b4f891f35
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="interpolated-strings-c-reference"></a>Cadenas interpoladas (Referencia de C#)

Se utiliza para construir cadenas.  Una cadena interpolada es similar a una cadena de plantilla que contiene *expresiones interpoladas*.  Una cadena interpolada devuelve una cadena que reemplaza a las expresiones interpoladas que contiene por sus representaciones de cadena.  

Los argumentos de una cadena interpolada son más fáciles de entender que una [cadena de formato compuesto](../../../standard/base-types/composite-formatting.md#composite-format-string).  Por ejemplo, la cadena interpolada  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}"); 
```  
contiene dos expresiones interpoladas, "{name}" y "{hours:hh}". La cadena de formato compuesto equivalente es esta:

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours);  
```  

La estructura de una cadena interpolada es la siguiente:  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

donde: 

- *field-width* es un entero con signo que indica el número de caracteres del campo. Si es positivo, el campo está alineado a la derecha. Si es negativo, está alineado a la izquierda. 

- *format-string* es una cadena de formato adecuada para el tipo de objeto al que se da formato. Por ejemplo, para un valor @System.DateTime, podría ser una cadena de formato estándar de fecha y hora, como "D" o "d".

 Puede utilizar una cadena interpolada en cualquier lugar que pueda utilizar un literal de cadena.  La cadena interpolada se evalúa cada vez que se ejecuta el código con la cadena interpolada. Esto le permite separar la definición y la evaluación de una cadena interpolada.  
  
 Para incluir una llave ("{" o "}") en una cadena interpolada, use dos llaves, "{{" o "}}".  Consulte la sección Conversiones implícitas para obtener más detalles.  

Si la cadena interpolada contiene otros caracteres con un significado especial en una cadena interpolada, como comillas dobles ("), dos puntos (:) o coma (,), deben incluirse entre caracteres de escape si aparecen en texto literal, o bien deben incluirse en una expresión delimitada por paréntesis si son elementos del lenguaje incluidos en una expresión interpolada. En el ejemplo siguiente las comillas se escriben entre caracteres de escape para incluirlas en la cadena de resultado y se usan paréntesis para delimitar la expresión `(age == 1 ? "" : "s")` de modo que el carácter de dos puntos no se interprete como el principio de una cadena de formato.

[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

## <a name="implicit-conversions"></a>Conversiones implícitas  

Hay tres conversiones de tipo implícito de una cadena interpolada:  

1. Conversión de una cadena interpolada a @System.String. En el ejemplo siguiente se devuelve una cadena cuyas expresiones de cadena interpolada se han reemplazado por las representaciones de cadena. Por ejemplo:

   [!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   Este es el resultado final de una interpretación de cadena. Todas las apariciones de llaves dobles ("{{" y "}}") se convierten en una única llave. 

2. Conversión de una cadena interpolada a una variable <xref:System.IFormattable> que permite crear varias cadenas de resultado con contenido específico de la referencia cultural de una sola instancia <xref:System.IFormattable>. Esto resulta útil para incluir elementos como los formatos numéricos y de fecha correctos para cada referencia cultural.  Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato a la cadena mediante una llamada implícita o explícita al método @System.Object.ToString.  Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.  

   En el ejemplo siguiente se usa la reflexión para mostrar los miembros y los valores de propiedad y campo de una variable <xref:System.IFormattable> que se crea a partir de una cadena interpolada. También se pasa la variable <xref:System.IFormattable> al método @System.Console(System.String).

   [!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   Tenga en cuenta que la cadena interpolada solo se puede inspeccionar mediante reflexión. Si se pasa a un método de formato de cadena, como @System.Console.WriteLine(System.String), sus elementos de formato se resuelven y se devuelve la cadena de resultado. 

3. Conversión de una cadena interpolada a una variable <xref:System.FormattableString> que representa una cadena de formato compuesto. El hecho de inspeccionar la cadena de formato compuesto y la manera en que se presenta como cadena de resultado podría ayudarle a protegerse frente a un ataque por inyección si estuviese compilando una consulta.  <xref:System.FormattableString> también incluye sobrecargas <xref:System.FormattableString.ToString> que le permiten generar cadenas de resultado para @System.Globalization.InvariantCulture y @System.Globalization.CurrentCulture.  Todas las apariciones de llaves dobles ("{{" y "}}") permanecen como llaves dobles hasta que dé formato.  Todas las expresiones de interpolación incluidas se convierten en {0}, \{1\} y así sucesivamente.  

   [!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a>Especificación del lenguaje  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IFormattable?displayProperty=fullName>   
 <xref:System.FormattableString?displayProperty=fullName>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)

