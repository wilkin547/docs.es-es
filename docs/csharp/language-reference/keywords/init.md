---
description: 'init (palabra clave): Referencia de C#'
title: 'init (palabra clave): Referencia de C#'
ms.date: 03/03/2021
f1_keywords:
- init
- init_CSharpKeyword
helpviewer_keywords:
- init keyword [C#]
ms.openlocfilehash: 2271b5332c8bfd3223d0c034a44eca4e2ca0ca54
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190446"
---
# <a name="init-c-reference"></a>init (Referencia de C#)

En C# 9 y versiones posteriores, la palabra clave `init` define un método de *descriptor de acceso* en una propiedad o un indizador. Un establecedor de solo inicio asigna un valor a la propiedad o al elemento de indizador únicamente durante la construcción del objeto. Para obtener más información y ejemplos, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md), [Propiedades autoimplementadas](../../programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../programming-guide/indexers/index.md).

En el ejemplo siguiente se definen los descriptores de acceso `get` y `init` para una propiedad denominada `Seconds`. Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.

[!code-csharp[init#1](snippets/InitExample1.cs)]

A menudo, el descriptor de acceso `init` consta de una única instrucción que asigna un valor, como en el ejemplo anterior. Puede implementar el descriptor de acceso `init` como un miembro con forma de expresión. En el ejemplo siguiente se implementan los descriptores de acceso `get` y `init` como miembros con forma de expresión.

[!code-csharp[init#3](snippets/InitExample3.cs)]
  
En los casos sencillos en los que los descriptores de acceso `get` y `init` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente. En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente.

[!code-csharp[init#2](snippets/InitExample2.cs)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Propiedades](../../programming-guide/classes-and-structs/properties.md)
