---
title: 'Palabra clave base: Referencia de C#'
ms.custom: seodec18
description: Obtenga información sobre la palabra clave base, que se usa para acceder a los miembros de la clase base desde una clase derivada en C#.
ms.date: 07/20/2015
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
ms.openlocfilehash: 513e28debe5fdccc4cc7e4e41d212b976c4a4595
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237888"
---
# <a name="base-c-reference"></a>base (Referencia de C#)

La palabra clave `base` se usa para acceder a los miembros de la clase base desde una clase derivada:

- Llamar a un método en la clase base que haya sido reemplazado por otro método.

- Especificar a qué constructor de clase base se debe llamar cuando se crean instancias de la clase derivada.

Solo se permite el acceso a una clase base en un constructor, un método de instancia o un descriptor de acceso de propiedad de instancia.

Usar la palabra clave `base` desde dentro de un método estático constituye un error.

La clase base a la que se obtiene acceso es la especificada en la declaración de clase. Por ejemplo, si especifica `class ClassB : ClassA`, se obtiene acceso a los miembros de ClassA desde ClassB, independientemente de la clase base de ClassA.

## <a name="example"></a>Ejemplo

En este ejemplo, la clase base, `Person`, y la clase derivada, `Employee`, tienen un método denominado `Getinfo`. Mediante el uso de la palabra clave `base`, es posible llamar al método `Getinfo` en la clase base desde la clase derivada.

[!code-csharp[csrefKeywordsAccess#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#1)]

Para ver más ejemplos, consulte [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) y [override](../../../csharp/language-reference/keywords/override.md).

## <a name="example"></a>Ejemplo

En este ejemplo se muestra cómo especificar el constructor de clase base al que se llama al crear instancias de una clase derivada.

[!code-csharp[csrefKeywordsAccess#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#2)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [this](../../../csharp/language-reference/keywords/this.md)