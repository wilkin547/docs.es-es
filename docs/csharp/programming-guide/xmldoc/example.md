---
title: <example> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: 615eccbc427b6a5bbbed061acd0c8b0b9be7f46c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789813"
---
# <a name="example-c-programming-guide"></a>\<example> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<example>description</example>
```

## <a name="parameters"></a>Parámetros

- `description`

  Una descripción del ejemplo de código.

## <a name="remarks"></a>Comentarios

La etiqueta \<example> le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](./code.md).

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
