---
title: 'this keyword: Referencia de C#'
description: Palabra clave this (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: 2a2c487ad93e6fc75ecf95c541e859b8b60bb5b5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715103"
---
# <a name="this-c-reference"></a>this (Referencia de C#)

La palabra clave `this` hace referencia a la instancia actual de la clase y también se usa como modificador del primer parámetro de un método de extensión.

> [!NOTE]
> En este artículo se describe el uso de `this` con instancias de clase. Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../programming-guide/classes-and-structs/extension-methods.md).

A continuación se indican usos habituales de `this`:

- Para calificar a miembros ocultos por nombres similares, por ejemplo:

  [!code-csharp[csrefKeywordsAccess#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#4)]  

- Para pasar un objeto como parámetro a otros métodos, por ejemplo:

  ```csharp
  CalcTax(this);
  ```

- Para declarar indizadores, por ejemplo:

  [!code-csharp[csrefKeywordsAccess#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#5)]

Las funciones miembro estáticas no tienen un puntero `this`, debido a que existen en el nivel de clase y no como parte de un objeto. Es un error hacer referencia a `this` en un método estático.

## <a name="example"></a>Ejemplo

En este ejemplo, se usa `this` para calificar los miembros de la clase `Employee`, `name` y `alias`, que están ocultos por nombres similares. También se usa para pasar un objeto al método `CalcTax`, que pertenece a otra clase.

[!code-csharp[csrefKeywordsAccess#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsAccess/CS/csrefKeywordsAccess.cs#3)]

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [base](base.md)
- [Métodos](../../programming-guide/classes-and-structs/methods.md)
