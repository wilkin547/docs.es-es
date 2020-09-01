---
description: 'Modificador new: Referencia de C#'
title: 'Modificador new: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 2da0a360868250169fb16380c80bf32c4b335d7a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139416"
---
# <a name="new-modifier-c-reference"></a>new (Modificador, Referencia de C#)

Cuando se utiliza como modificador de una declaración, la palabra clave `new` oculta explícitamente un miembro heredado de una clase base. Cuando se oculta un miembro heredado, la versión derivada del miembro reemplaza a la versión de la clase base. Aunque los miembros se pueden ocultar sin utilizar el modificador `new`, obtendrá una advertencia del compilador. Si utiliza `new` explícitamente para ocultar un miembro, se suprime esta advertencia.

También puede usar la palabra clave `new` para [crear una instancia de un tipo](../operators/new-operator.md) o como una [restricción de tipo genérico](./new-constraint.md).

Para ocultar un miembro heredado, declárelo en la clase derivada con el mismo nombre de miembro y modifíquelo con la palabra clave `new`. Por ejemplo:

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

En este ejemplo, `BaseC.Invoke` oculta `DerivedC.Invoke`. El campo `x` no se ve afectado porque no lo oculta un nombre similar.

La ocultación de nombres por medio de la herencia toma una de las siguientes formas:

- Normalmente, una constante, un campo, una propiedad o un tipo que se muestran en una clase o struct ocultan a todos los miembros de la clase base que comparten su nombre. Hay casos especiales. Por ejemplo, si declara un nuevo campo con el nombre `N` para tener un tipo que no es invocable y un tipo base declara `N` como método, el nuevo campo no oculta la declaración base en la sintaxis de invocación. Para obtener más información, vea la sección [Búsqueda de miembros](~/_csharplang/spec/expressions.md#member-lookup) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

- Un método introducido en una clase o struct oculta las propiedades, los campos y los tipos que comparten el nombre en la clase base. También oculta todos los métodos de la clase base que tienen la misma signatura.

- Un indizador introducido en una clase o struct oculta todos los indizadores de la clase base que tienen la misma signatura.

Es un error usar `new` y [override](override.md) en el mismo miembro, porque los dos modificadores tienen significados mutuamente excluyentes. El modificador `new` crea un nuevo miembro con el mismo nombre y oculta el miembro original. El modificador `override` amplía la implementación de un miembro heredado.

Si se utiliza el modificador `new` en una declaración que no oculta un miembro heredado, se genera una advertencia.

## <a name="example"></a>Ejemplo

En este ejemplo, una clase base, `BaseC`, y una clase derivada, `DerivedC`, utilizan el mismo nombre de campo `x`, lo que oculta el valor del campo heredado. El ejemplo muestra el uso del modificador `new`. También muestra cómo obtener acceso a los miembros ocultos de la clase base mediante sus nombres completos.

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a>Ejemplo

En este ejemplo, una clase anidada oculta una clase que tiene el mismo nombre en la clase base. El ejemplo muestra cómo utilizar el modificador `new` para eliminar el mensaje de advertencia y cómo obtener acceso a los miembros de la clase oculta mediante sus nombres completos.

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

Si quita el modificador `new`, el programa seguirá compilándose y ejecutándose, pero aparecerá la siguiente advertencia:

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [El modificador new](~/_csharplang/spec/classes.md#the-new-modifier) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores](index.md)
- [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [Saber cuándo utilizar las palabras clave Override y New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
