---
title: 'is: Referencia de C#'
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398308"
---
# <a name="is-c-reference"></a>is (Referencia de C#)

El operador `is` comprueba si el resultado de una expresión es compatible con un tipo determinado o, a partir de C# 7.0, prueba una expresión en un patrón. Para obtener información sobre el operador de prueba de tipos `is`, consulte la sección [operador is](../operators/type-testing-and-cast.md#is-operator) del artículo [Operadores de conversión y prueba de tipos](../operators/type-testing-and-cast.md).

## <a name="pattern-matching-with-is"></a>Coincidencia de patrones con `is`

A partir de C# 7.0, las instrucciones `is` y [switch](switch.md) admiten la coincidencia de patrones. La palabra clave `is` admite los patrones siguientes:

- [Patrón de tipo](#type-pattern), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.

- [Patrón de constante](#constant-pattern), que comprueba si una expresión se evalúa como un valor constante especificado.

- [Patrón var](#var-pattern), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva.

### <a name="type-pattern"></a>Patrón de tipo

Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo. Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa. La forma general del patrón de tipos `is` es:

```csharp
   expr is type varname
```

Donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`.

La expresión `is` es `true` si *expr* no es `null` y se cumple alguna de las siguientes condiciones:

- *expr* es una instancia del mismo tipo que *type*.

- *expr* es una instancia de un tipo que deriva de *type*. En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.

- *expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*. El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración. El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.

- *type* es una instancia de un tipo que implementa la interfaz *type*.

A partir de C# 7.1, *expr* puede tener un tipo de tiempo de compilación definido por un parámetro y sus restricciones.

Si *expr* es `true` y `is` se usa con una instrucción `if`, solo se asigna *varname* dentro de la instrucción `if`. El ámbito de *varname* abarca de la expresión `is` al final del bloque que incluye la instrucción `if`. El uso de *varname* en cualquier otra ubicación genera un error en tiempo de compilación por el uso de una variable que no se ha asignado.

En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación de un método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> de tipo.

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

Sin coincidencia de patrones, este código podría escribirse del modo siguiente. El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor. En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada.

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a>Patrón de constante

Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada. En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante. A partir de C# 7.0, la instrucción `is` también lo admite. Su sintaxis es:

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

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

La búsqueda de `null` puede realizarse con el patrón de constante. La palabra clave `null` es compatible con la instrucción `is`. Su sintaxis es:

```csharp
   expr is null
```

En el ejemplo siguiente se muestra una comparación de comprobaciones `null`:

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a>Patrón var

Una coincidencia de patrones con el patrón `var` siempre se realiza correctamente. Su sintaxis es:

```csharp
   expr is var varname
```

Donde el valor de *expr* siempre se asigna a una variable local denominada *varname*. *varname* es una variable del mismo tipo que el tipo en tiempo de compilación de *expr*.

Si *expr* se evalúa como `null`, la expresión de `is` produce `true` y asigna `null` a *varname*. El patrón var es uno de los pocos usos de `is` que produce `true` con un valor `null`.

El patrón `var` se puede usar para crear una variable temporal dentro de una expresión booleana, como se muestra en el ejemplo siguiente:

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

En el ejemplo anterior, la variable temporal se usa para almacenar el resultado de una operación costosa. Tras ello, la variable se puede usar varias veces.

## <a name="c-language-specification"></a>Especificación del lenguaje C#
  
Para más información, consulte la sección del [operador is](~/_csharplang/spec/expressions.md#the-is-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y las siguientes propuestas del lenguaje C#:

- [Coincidencia de patrones](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [Coincidencia de patrones con genéricos](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Palabras clave de C#](index.md)
- [Operadores de conversión y prueba de tipos](../operators/type-testing-and-cast.md)
