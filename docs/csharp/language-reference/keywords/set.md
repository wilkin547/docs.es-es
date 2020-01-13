---
title: 'set keyword: Referencia de C#'
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: 97b0dbf8716edc4cd465eb5ac693efa0ecaa498b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713084"
---
# <a name="set-c-reference"></a>set (Referencia de C#)

La palabra clave `set` define un método de *descriptor de acceso* en una propiedad o indexador que asigna el valor de la propiedad o del elemento del indexador. Para obtener más información y ejemplos, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md), [Propiedades autoimplementadas](../../programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../programming-guide/indexers/index.md).

En el ejemplo siguiente se definen unos descriptores de acceso `get` y `set` para una propiedad denominada `Seconds`. Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

A menudo, el descriptor de acceso `set` consta de una única instrucción que asigna un valor, como en el ejemplo anterior. A partir de C# 7.0, se puede implementar el descriptor de acceso `set` como un miembro con forma de expresión. En el ejemplo siguiente se implementan los descriptores de acceso `get` y `set` como miembros con forma de expresión.

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
En los casos sencillos en los que los descriptores de acceso `get` y `set` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente. En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente. 

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Propiedades](../../programming-guide/classes-and-structs/properties.md)
