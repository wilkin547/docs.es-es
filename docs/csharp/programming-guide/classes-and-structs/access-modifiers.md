---
title: 'Modificadores de acceso: Guía de programación de C#'
description: Todos los tipos y miembros de tipo de C# tienen un nivel de accesibilidad que controla si se pueden usar desde otro código. Revise esta lista de modificadores de acceso.
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 557f5d9f302b08d32896b462e86ce1d96710ff36
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474532"
---
# <a name="access-modifiers-c-programming-guide"></a>Modificadores de acceso (Guía de programación de C#)

Todos los tipos y miembros de tipo tienen un nivel de accesibilidad. El nivel de accesibilidad controla si se pueden usar desde otro código del ensamblado u otros ensamblados. Use los modificadores de acceso siguientes para especificar la accesibilidad de un tipo o miembro cuando lo declare:

- [public](../../language-reference/keywords/public.md): Puede obtener acceso al tipo o miembro cualquier otro código del mismo ensamblado o de otro ensamblado que haga referencia a éste.
- [private](../../language-reference/keywords/private.md): solamente el código de la misma `class` o `struct` puede acceder al tipo o miembro.
- [protected](../../language-reference/keywords/protected.md): solamente el código de la misma `class`, o bien de una `class` derivada de esa `class`, puede acceder al tipo o miembro.
- [internal](../../language-reference/keywords/internal.md): Puede obtener acceso al tipo o miembro cualquier código del mismo ensamblado, pero no de un ensamblado distinto.
- [protected internal](../../language-reference/keywords/protected-internal.md): cualquier código del ensamblado en el que se ha declarado, o desde una `class` derivada de otro ensamblado, puede acceder al tipo o miembro.
- [private protected](../../language-reference/keywords/private-protected.md): el código de la misma `class`, o de un tipo derivado de esa `class`, puede acceder al tipo o miembro solo dentro de su ensamblado de declaración.

En los ejemplos siguientes se muestra cómo especificar modificadores de acceso en un tipo y miembro:

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

No todos los modificadores de acceso son válidos para todos los tipos o miembros de todos los contextos. En algunos casos, la accesibilidad de un miembro de tipo está restringida por la accesibilidad de su tipo contenedor.

## <a name="class-and-struct-accessibility"></a>Accesibilidad de clases y estructuras  

Las clases y estructuras que se declaran directamente en un espacio de nombres (es decir, que no están anidadas en otras clases o estructuras) pueden ser `public` o `internal`. Si no se especifica ningún modificador de acceso, el valor predeterminado es `Internal`.  

Los miembros de estructura, incluidas las clases y las estructuras anidadas, se pueden declarar como `public`, `internal` o `private`. Los miembros de clase, incluidas las clases y las estructuras anidadas, pueden ser `public`, `protected internal`, `protected`, `internal`, `private protected` o `private`. Los miembros de clase y de estructura, incluidas las clases y estructuras anidadas, tienen acceso `private` de forma predeterminada. Los tipos anidados privados no son accesibles desde fuera del tipo contenedor.

Las clases derivadas no pueden tener mayor accesibilidad que sus tipos base. No se puede declarar una clase pública `B` que derive de una clase interna `A`. Si se permitiera, convertiría `A` en público, porque todos los miembros `protected` o `internal` de `A` son accesibles desde la clase derivada.

Puede habilitar otros ensamblados concretos para acceder a los tipos internos mediante `InternalsVisibleToAttribute`. Para más información, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).

## <a name="class-and-struct-member-accessibility"></a>Accesibilidad de miembros de clase y estructura  

Los miembros de clase (incluidas las clases y las estructuras anidadas) se pueden declarar con cualquiera de los seis tipos de acceso. Los miembros de estructura no se pueden declarar como `protected`, `protected internal` o `private protected` porque las estructuras no admiten la herencia.

Normalmente, la accesibilidad de un miembro no es mayor que la del tipo que lo contiene. Pero un miembro `public` de una clase interna podría ser accesible desde fuera del ensamblado si el miembro implementa los métodos de interfaz o invalida los métodos virtuales definidos en una clase base pública.

El tipo de cualquier miembro que sea un campo, propiedad o evento debe ser al menos tan accesible como el propio miembro. Del mismo modo, el tipo devuelto y los tipos de parámetro de cualquier método, indizador o delegado deben ser al menos tan accesibles como el propio miembro. Por ejemplo, no puede tener un método `public` `M` que devuelva una clase `C` a menos que `C` también sea `public`. Del mismo modo, no puede tener una propiedad `protected` de tipo `A` si `A` se declara como `private`.

Los operadores definidos por el usuario siempre se deben declarar como `public` y `static`. Para obtener más información, vea [Sobrecarga de operadores](../../language-reference/operators/operator-overloading.md).

Los finalizadores no pueden tener modificadores de accesibilidad.

Para establecer el nivel de acceso de un miembro de `class` o `struct`, agregue la palabra clave adecuada a la declaración de miembro, como se muestra en el ejemplo siguiente.

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a>Otros tipos

Las interfaces declaradas directamente en un espacio de nombres pueden ser `public` o `internal` y, al igual que las clases y las estructuras, su valor predeterminado es el acceso `internal`. Los miembros de interfaz son `public` de manera predeterminada porque el propósito de una interfaz es permitir que otros tipos accedan a una clase o estructura. Las declaraciones de miembros de interfaz pueden incluir cualquier modificador de acceso. Esto es muy útil para que los métodos estáticos proporcionen implementaciones comunes necesarias para todos los implementadores de una clase.

Los miembros de enumeración siempre son `public` y no se les puede aplicar ningún modificador de acceso.

Los delegados se comportan como las clases y las estructuras. De forma predeterminada, tienen acceso `internal` cuando se declaran directamente en un espacio de nombres y acceso `private` cuando están anidados.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Interfaces](../interfaces/index.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)
- [internal](../../language-reference/keywords/internal.md)
- [protected](../../language-reference/keywords/protected.md)
- [protected internal](../../language-reference/keywords/protected-internal.md)
- [private protected](../../language-reference/keywords/private-protected.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [interface](../../language-reference/keywords/interface.md)
