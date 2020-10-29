---
description: 'Modificador override: Referencia de C#'
title: 'Modificador override: Referencia de C#'
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434884"
---
# <a name="override-c-reference"></a>override (Referencia de C#)

El modificador `override` es necesario para ampliar o modificar la implementación abstracta o virtual de un método, propiedad, indexador o evento heredado.

En el siguiente ejemplo, la clase `Square` debe proporcionar una implementación invalidada de `GetArea`, ya que `GetArea` se hereda de la clase abstracta `Shape`:

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

Un método `override` proporciona una nueva implementación de un método heredado de una clase base. El método invalidado por una declaración `override` se conoce como método base invalidado. Un método `override` debe tener la misma signatura que el método base invalidado. A partir de C# 9.0, los métodos `override` admiten tipos de valor devuelto covariantes. En concreto, el tipo de valor devuelto de un método `override` puede derivar del tipo de valor devuelto del método base correspondiente. En C# 8.0 y versiones anteriores, los tipos de valor devuelto de un método `override` y el método base invalidado deben ser iguales.

No se puede invalidar un método estático o no virtual. El método base invalidado debe ser `virtual`, `abstract` o `override`.

Una declaración `override` no puede cambiar la accesibilidad del método `virtual`. El método `override` y el método `virtual` deben tener el mismo [modificador de nivel de acceso](access-modifiers.md).

No se pueden usar los modificadores `new`, `static` o `virtual` para modificar un método `override`.

Una declaración de propiedad de invalidación debe especificar exactamente el mismo modificador de acceso, tipo y nombre que la propiedad heredada,. A partir de C# 9.0, las propiedades de invalidación de solo lectura admiten tipos de valor devuelto covariantes. La propiedad invalidada debe ser `virtual`, `abstract` u `override`.

Para obtener más información sobre cómo usar la palabra clave `override`, vea [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md). Para obtener información sobre la herencia, vea [Herencia](../../programming-guide/classes-and-structs/inheritance.md).

## <a name="example"></a>Ejemplo

En este ejemplo se define una clase base denominada `Employee` y una clase derivada denominada `SalesEmployee`. La clase `SalesEmployee` incluye un campo adicional, `salesbonus`, e invalida el método `CalculatePay` para tenerlo en cuenta.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Métodos de invalidación](~/_csharplang/spec/classes.md#override-methods) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).

Para obtener más información sobre tipos de valor devuelto covariantes, vea la [nota de propuesta de características](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Herencia](../../programming-guide/classes-and-structs/inheritance.md)
- [Palabras clave de C#](index.md)
- [Modificadores](index.md)
- [abstract](abstract.md)
- [virtual](virtual.md)
- [new (modificador)](new-modifier.md)
- [Polimorfismo](../../programming-guide/classes-and-structs/polymorphism.md)
