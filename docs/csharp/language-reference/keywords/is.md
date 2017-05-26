---
title: is (Referencia de C#) | Microsoft Docs
keywords: Palabra clave is (C#), is (C#)
ms.date: 2017-02-17
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- is_CSharpKeyword
- is
dev_langs:
- CSharp
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c0d300dbb47e64d2425f8af3bc6a819b145786fa
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="is-c-reference"></a>is (Referencia de C#) #

Comprueba si un objeto es compatible con un tipo determinado o, a partir de C# 7, comprueba una expresión con un patrón.

## <a name="testing-for-type-compatibility"></a>Probar la compatibilidad de tipos ##

La palabra clave `is` evalúa la compatibilidad de tipos en tiempo de ejecución. Determina si una instancia de objeto o el resultado de una expresión se puede convertir en un tipo especificado. Tiene la sintaxis

```csharp
   expr is type
```

en la que *expr* es una expresión que se evalúa como una instancia de un tipo y *type* es el nombre del tipo en el que se va a convertir el resultado de *expr*. La instrucción `is` es `true` si *expr* no es NULL y el objeto resultado de la evaluación de la expresión se pueden convertir en *type*. En caso contrario, devuelve `false`.

Por ejemplo, el código siguiente determina si `obj` se puede convertir en una instancia del tipo `Person`:

[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

La instrucción `is` es verdadera si:

- *expr* es una instancia del mismo tipo que *type*.

- *expr* es una instancia de un tipo que deriva de *type*. En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.

- *expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*. El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración. El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.

- *expr* es una instancia de un tipo que implementa la interfaz *type*.

En el ejemplo siguiente se muestra que la expresión `is` se evalúa como `true` para cada una de estas conversiones.

[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

La palabra clave `is` genera una advertencia en tiempo de compilación si se sabe que la expresión es siempre `true` o `false`. Solo considera las conversiones de referencias, las conversiones boxing y las conversiones unboxing. No tiene en cuenta las conversiones definidas por el usuario o las conversiones definidas por los operadores [implicit](implicit.md) y [explicit](explicit.md) de un tipo. En el ejemplo siguiente se generan advertencias porque el resultado de la conversión se conoce en tiempo de compilación. Tenga en cuenta que la expresión `is` para conversiones de `int` en `long` y `double` devuelve false, ya que estas conversiones se controlan mediante el operador [implicit](implicit.md).

[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

`expr` puede ser cualquier expresión que devuelva un valor, a excepción de métodos anónimos y expresiones lambda. En el ejemplo siguiente se usa `is` para evaluar el valor devuelto de una llamada de método.   
[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

A partir de C# 7, puede usar la coincidencia de patrones con el [patrón de tipo](#type) para escribir código más conciso que use la instrucción `is`.

## <a name="pattern-matching-with-is"></a>Coincidencia de patrones con `is` ##

A partir de C# 7, las instrucciones `is` y [switch](../../../csharp/language-reference/keywords/switch.md) admiten la coincidencia de patrones. La palabra clave `is` admite los patrones siguientes:

- [Patrón de tipo](#type), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.

- [Patrón de constante](#constant), que comprueba si una expresión se evalúa como un valor constante especificado.

- [Patrón var](#var), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva. 

### <a name="type" /> Patrón de tipo </a>

Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo. Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa. La forma general del patrón de tipos `is` es:

```csharp
   expr is type varname 
```

donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`. 

La expresión `is` es `true` si se cumple alguna de las siguientes condiciones:

- *expr* es una instancia del mismo tipo que *type*.

- *expr* es una instancia de un tipo que deriva de *type*. En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.

- *expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*. El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración. El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.

- *expr* es una instancia de un tipo que implementa la interfaz *type*.

Si *exp* es `true` e `is` se usa con una instrucción `if`, *varname* se asigna y tiene ámbito local solo dentro de la instrucción `if`.

En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación del método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> de un tipo.

[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

Sin coincidencia de patrones, este código podría escribirse del modo siguiente. El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.  

[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor. En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada. 

[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.

[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><a name="constant" /> Patrón de constante ###

Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada. En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante. A partir de C# 7, la instrucción `is` también lo admite. Su sintaxis es:

```csharp
   expr is constant
```

donde *expr* es la expresión que se va a evaluar y *constant* es el valor que se va a comprobar. *constant* puede ser cualquiera de las expresiones de constante siguientes: 

- Un valor literal.

- El nombre de una variable `const` declarada.

- Una constante de enumeración.

La expresión de constante se evalúa de la siguiente forma:

- Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).

- De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).  

En el ejemplo siguiente se combinan los patrones de tipo y de constante para probar si un objeto es una instancia de `Dice` y, si es así, para determinar si el valor de una tirada de dados es 6.

[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]
 
### <a name="var" /> Patrón var </a>

Una coincidencia de patrones con el patrón de var siempre se realiza correctamente. Su sintaxis es

```csharp 
   expr is var varname
```

donde el valor de *expr* siempre se asigna a una variable local denominada *varname*. *varname* es una variable estática del mismo tipo que *expr*. En el ejemplo siguiente se usa el patrón var para asignar una expresión a una variable denominada `obj`. Después, se muestra el valor y el tipo de `obj`.

[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

Observe que si *expr* es `null`, la expresión `is` sigue siendo true y asigna `null` a *varname*. 

# <a name="c-language-specification"></a>Especificación del lenguaje C#
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [typeof](../../../csharp/language-reference/keywords/typeof.md)   
 [as](../../../csharp/language-reference/keywords/as.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)

