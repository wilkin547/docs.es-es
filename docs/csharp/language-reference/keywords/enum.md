---
title: 'Palabra clave enum: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 57043963640f3c384b1e1a9aa7aeb65114689e9f
ms.sourcegitcommit: 4a3c95e91289d16c38979575a245a4f76b0da147
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2019
ms.locfileid: "67569535"
---
# <a name="enum-c-reference"></a>enum (Referencia de C#)

La palabra clave `enum` se utiliza para declarar una enumeración, un tipo distinto que consiste en un conjunto de constantes con nombre denominado lista de enumeradores.

Normalmente suele ser recomendable definir una enumeración directamente dentro de un espacio de nombres para que todas las clases de dicho espacio puedan tener acceso a esta con la misma facilidad. Sin embargo, una enumeración también puede anidarse dentro de una clase o estructura.

De manera predeterminada, el primer enumerador tiene el valor 0 y el valor de cada enumerador sucesivo se incrementa en 1. Por ejemplo, en la siguiente enumeración, `Sat` es `0`, `Sun` es `1`, `Mon` es `2`, y así sucesivamente.

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

Los enumeradores pueden usar inicializadores para invalidar los valores predeterminados, como se muestra en el ejemplo siguiente.

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

En esta enumeración, la secuencia de elementos debe iniciarse a partir de `1` en lugar de `0`. Sin embargo, se recomienda incluir una constante con el valor 0. Para obtener más información, vea [Tipos de enumeración](../../programming-guide/enumeration-types.md).

Cada tipo de enumeración tiene un tipo subyacente, que puede ser cualquier [tipo numérico entero](../builtin-types/integral-numeric-types.md). El tipo [char](char.md) no puede ser un tipo subyacente de una enumeración. El tipo subyacente predeterminado de los elementos de la enumeración es [int](../builtin-types/integral-numeric-types.md). Para declarar una enumeración de otro tipo entero, como [byte](../builtin-types/integral-numeric-types.md), use el carácter de dos puntos después del identificador y escriba a continuación el tipo, como se muestra en el ejemplo siguiente.

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

A una variable de un tipo de enumeración se le puede asignar cualquier valor en el intervalo del tipo subyacente; los valores no se limitan a las constantes con nombre.

El valor predeterminado de `enum E` es el valor que produce la expresión `(E)0`.

> [!NOTE]
> Un enumerador no puede contener espacios en blanco en su nombre.

El tipo subyacente especifica la cantidad de almacenamiento asignado a cada enumerador. No obstante, se necesita una conversión explícita para convertir un tipo `enum` a un tipo entero. Por ejemplo, la siguiente instrucción asigna el enumerador `Sun` a una variable de tipo [int](../builtin-types/integral-numeric-types.md) utilizando una conversión de tipos para convertir de `enum` a `int`.

```csharp
int x = (int)Day.Sun;
```

Cuando se aplica <xref:System.FlagsAttribute?displayProperty=nameWithType> a una enumeración que contiene algunos elementos que se pueden combinar con una operación `OR` bit a bit, se observará que el atributo afecta al comportamiento de `enum` cuando se utiliza con algunas herramientas. Se pueden observar estos cambios al utilizar herramientas tales como los métodos de la clase <xref:System.Console> y el Evaluador de expresiones. (Vea el tercer ejemplo.)

## <a name="robust-programming"></a>Programación sólida

Como ocurre con cualquier constante, todas las referencias a los valores individuales de una enumeración se convierten en literales numéricos en tiempo de compilación. Esto puede crear posibles problemas de versiones como se describe en [Constantes](../../programming-guide/classes-and-structs/constants.md).

La asignación de valores adicionales a nuevas versiones de enumeraciones o el cambio de los valores de los miembros de enumeración en una nueva versión puede producir problemas para el código fuente dependiente. Los valores enum se utilizan a menudo en instrucciones [switch](switch.md) . Si los elementos adicionales se han agregado al tipo `enum` , la sección predeterminada de la instrucción switch se puede seleccionar de forma inesperada.

Si otros desarrolladores utilizan su código, debería proporcionar instrucciones sobre cómo debería reaccionar el código de ellos al agregar nuevos elementos a cualquier tipo `enum` .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se declara una enumeración, `Day`. Dos enumeradores se convierten explícitamente en un número entero y se asignan a variables de número entero.

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, la opción de tipo base se utiliza para declarar un `enum` cuyos miembros son del tipo `long`. Observe que a pesar de que el tipo subyacente de la enumeración es `long`, los miembros de la enumeración todavía deben convertirse explícitamente al tipo `long` mediante una conversión de tipos.

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se ilustra el uso y efecto del atributo <xref:System.FlagsAttribute?displayProperty=nameWithType> en una declaración `enum` .

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a>Comentarios

Si quita `Flags`, el ejemplo muestra los siguientes valores:

`5`

`5`

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Tipos de enumeración](../../programming-guide/enumeration-types.md)
- [Palabras clave de C#](index.md)
- [Tipos enteros](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [Tabla de tipos integrados](built-in-types-table.md)
- [Tabla de conversiones numéricas implícitas](implicit-numeric-conversions-table.md)
- [Tabla de conversiones numéricas explícitas](explicit-numeric-conversions-table.md)
- [Convenciones de nomenclatura de enum](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
