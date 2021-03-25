---
title: <c> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <c>. Esta etiqueta marca el texto de una sola línea en una descripción como código, mientras que <code> indicates multiple lines..
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: fc445c7245287c3835543e4bbe4b3b46ec46fd35
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478691"
---
# <a name="c-c-programming-guide"></a>\<c> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<c>text</c>
```

## <a name="parameters"></a>Parámetros

- `text`

  El texto que le gustaría indicar como código.

## <a name="remarks"></a>Comentarios

La etiqueta `<c>` le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código. Use [\<code>](./code.md) para indicar varias líneas como código.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
