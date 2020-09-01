---
description: 'Modificador override: Referencia de C#'
title: 'Modificador override: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 51ca806310214981b7ff24a796fe078d902dca4d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134465"
---
# <a name="override-c-reference"></a>override (Referencia de C#)

El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.

## <a name="example"></a>Ejemplo

En este ejemplo, la clase `Square` debe proporcionar una implementación de invalidación de `GetArea` porque `GetArea` se hereda de la clase abstracta `Shape`:

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

Un método `override` proporciona una nueva implementación de un miembro que se hereda de una clase base. El método invalidado por una declaración `override` se conoce como método base invalidado. El método base invalidado debe tener la misma firma que el método `override`. Para obtener información sobre la herencia, vea [Herencia](../../programming-guide/classes-and-structs/inheritance.md).

No se puede invalidar un método estático o no virtual. El método base invalidado debe ser `virtual`, `abstract` o `override`.

Una declaración `override` no puede cambiar la accesibilidad del método `virtual`. El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](access-modifiers.md).

No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.

Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada, y la propiedad invalidada debe ser `virtual`, `abstract` o `override`.

Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).

## <a name="example"></a>Ejemplo

En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`. La clase `SalesEmployee` incluye un campo adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Herencia](../../programming-guide/classes-and-structs/inheritance.md)
- [Palabras clave de C#](index.md)
- [Modificadores](index.md)
- [abstract](abstract.md)
- [virtual](virtual.md)
- [new (modificador)](new-modifier.md)
- [Polimorfismo](../../programming-guide/classes-and-structs/polymorphism.md)
