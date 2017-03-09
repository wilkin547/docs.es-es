---
title: "enum (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "enum"
  - "enum_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "enum (palabra clave) [C#]"
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
caps.latest.revision: 36
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 36
---
# enum (Referencia de C#)
La palabra clave `enum` se utiliza para declarar una enumeración, un tipo distinto que consiste en un conjunto de constantes con nombre denominado lista de enumeradores.  
  
 Normalmente suele ser recomendable definir una enumeración directamente dentro de un espacio de nombres para que todas las clases de dicho espacio puedan tener acceso a esta con la misma facilidad. Sin embargo, una enumeración también puede anidarse dentro de una clase o estructura.  
  
 De manera predeterminada, el primer enumerador tiene el valor 0 y el valor de cada enumerador sucesivo se incrementa en 1. Por ejemplo, en la siguiente enumeración, `Sat` es `0`, `Sun` es `1`, `Mon` es `2`, y así sucesivamente.  
  
```  
  
enum Days {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 Los enumeradores pueden usar inicializadores para invalidar los valores predeterminados, como se muestra en el ejemplo siguiente.  
  
```  
  
enum Days {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 En esta enumeración, la secuencia de elementos debe iniciarse a partir de `1` en lugar de `0`. Sin embargo, se recomienda incluir una constante con el valor 0. Para obtener más información, consulta [Tipos de enumeración](../../../csharp/programming-guide/enumeration-types.md).  
  
 Cada tipo de enumeración tiene un tipo subyacente, que puede ser cualquier tipo integral excepto [char](../../../csharp/language-reference/keywords/char.md). El tipo subyacente predeterminado de los elementos de la enumeración es [int](../../../csharp/language-reference/keywords/int.md). Para declarar una enumeración de otro tipo entero, como [byte](../../../csharp/language-reference/keywords/byte.md), use el carácter de dos puntos después del identificador y escriba a continuación el tipo, como se muestra en el ejemplo siguiente.  
  
```  
  
enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 Los tipos admitidos para una enumeración son `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
 A una variable de tipo `Days` se le puede asignar cualquier valor en el intervalo del tipo subyacente; los valores no se limitan a las constantes con nombre.  
  
 El valor predeterminado de `enum E` es el valor que produce la expresión `(E)0`.  
  
> [!NOTE]
>  Un enumerador no puede contener espacios en blanco en su nombre.  
  
 El tipo subyacente especifica la cantidad de almacenamiento asignado a cada enumerador. No obstante, se necesita una conversión explícita para convertir un tipo `enum` a un tipo entero. Por ejemplo, la siguiente instrucción asigna el enumerador `Sun` a una variable de tipo [int](../../../csharp/language-reference/keywords/int.md) utilizando una conversión de tipos para convertir de `enum` a `int`.  
  
```  
  
int x = (int)Days.Sun;  
```  
  
 Cuando se aplica <xref:System.FlagsAttribute?displayProperty=fullName> a una enumeración que contiene algunos elementos que se pueden combinar con una operación `OR` bit a bit, se observará que el atributo afecta al comportamiento de `enum` cuando se utiliza con algunas herramientas. Se pueden observar estos cambios al utilizar herramientas tales como los métodos de la clase <xref:System.Console> y el Evaluador de expresiones. \(Vea el tercer ejemplo.\)  
  
## Programación sólida  
 Como ocurre con cualquier constante, todas las referencias a los valores individuales de una enumeración se convierten en literales numéricos en tiempo de compilación. Esto puede crear posibles problemas de versiones como se describe en [Constantes](../../../csharp/programming-guide/classes-and-structs/constants.md).  
  
 La asignación de valores adicionales a nuevas versiones de enumeraciones o el cambio de los valores de los miembros de enumeración en una nueva versión puede producir problemas para el código fuente dependiente. Los valores enum se utilizan a menudo en instrucciones [switch](../../../csharp/language-reference/keywords/switch.md). Si los elementos adicionales se han agregado al tipo `enum`, la sección predeterminada de la instrucción switch se puede seleccionar de forma inesperada.  
  
 Si otros desarrolladores utilizan su código, debería proporcionar instrucciones sobre cómo debería reaccionar el código de ellos al agregar nuevos elementos a cualquier tipo `enum`.  
  
## Ejemplo  
 En el ejemplo siguiente, se declara una enumeración, `Days`. Dos enumeradores se convierten explícitamente en un número entero y se asignan a variables de número entero.  
  
 [!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/csharp/enum_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente, la opción de tipo base se utiliza para declarar un `enum` cuyos miembros son del tipo `long`. Observe que a pesar de que el tipo subyacente de la enumeración es `long`, los miembros de la enumeración todavía deben convertirse explícitamente al tipo `long` mediante una conversión de tipos.  
  
 [!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/csharp/enum_2.cs)]  
  
## Ejemplo  
 En el ejemplo de código siguiente se ilustra el uso y efecto del atributo <xref:System.FlagsAttribute?displayProperty=fullName> en una declaración `enum`.  
  
 [!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/csharp/enum_3.cs)]  
  
## Comentarios  
 Si quita `Flags`, el ejemplo muestra los siguientes valores:  
  
 `5`  
  
 `5`  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Tipos de enumeración](../../../csharp/programming-guide/enumeration-types.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Tabla de tipos enteros](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [Tabla de conversiones numéricas implícitas](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [Tabla de conversiones numéricas explícitas](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)