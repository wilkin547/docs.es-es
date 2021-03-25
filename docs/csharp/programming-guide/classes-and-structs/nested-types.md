---
title: 'Tipos anidados: Guía de programación de C#'
description: Un tipo definido en una clase, estructura o interfaz se denomina tipo anidado en C#.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 853138beed6ad9ddffa789f0080ca1fd2ba9d700
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511923"
---
# <a name="nested-types-c-programming-guide"></a>Tipos anidados (Guía de programación de C#)

Un tipo definido en una [clase](../../language-reference/keywords/class.md), [estructura](../../language-reference/builtin-types/struct.md) o [interfaz](../../language-reference/keywords/interface.md) se denomina tipo anidado. Por ejemplo

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

Con independencia de si el tipo externo es una clase, una interfaz o una estructura, los tipos anidados se establecen de manera predeterminada en [private](../../language-reference/keywords/private.md); solo son accesibles desde su tipo contenedor. En el ejemplo anterior, la clase `Nested` es inaccesible a los tipos externos.

También puede especificar un [modificador de acceso](../../language-reference/keywords/access-modifiers.md) para definir la accesibilidad de un tipo anidado, de la manera siguiente:

- Los tipos anidados de una **clase** pueden ser [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) o [private protected](../../language-reference/keywords/private-protected.md).

   En cambio, al definir una clase anidada `protected`, `protected internal` o `private protected` dentro de una [clase sellada](../../language-reference/keywords/sealed.md), se genera una advertencia del compilador [CS0628](../../misc/cs0628.md), "Nuevo miembro protegido declarado en la clase sealed".

   Tenga en cuenta también que la creación de un tipo anidado externamente visible infringe la regla de calidad del código [CA1034](../../../fundamentals/code-analysis/quality-rules/ca1034.md) "Los tipos anidados no deben ser visibles".

- Los tipos anidados de un **struct** pueden ser [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) o [private](../../language-reference/keywords/private.md).

En el ejemplo siguiente se convierte la clase `Nested` en public:

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

El tipo anidado o interno puede tener acceso al tipo contenedor o externo. Para tener acceso al tipo contenedor, páselo como un argumento al constructor del tipo anidado. Por ejemplo:

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

Un tipo anidado tiene acceso a todos los miembros que estén accesibles para el tipo contenedor. Puede tener acceso a los miembros privados y protegidos del tipo contenedor, incluidos los miembros protegidos heredados.

En la declaración anterior, el nombre completo de la clase `Nested` es `Container.Nested`. Este es el nombre que se utiliza para crear una instancia nueva de la clase anidada, de la siguiente manera:

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Modificadores de acceso](./access-modifiers.md)
- [Constructores](./constructors.md)
- [Regla CA1034](../../../fundamentals/code-analysis/quality-rules/ca1034.md)
