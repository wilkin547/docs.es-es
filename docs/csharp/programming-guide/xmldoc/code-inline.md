---
title: <c> - Guía de programación de C#
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
ms.openlocfilehash: a09bcd069e2f85f4a21736cb218c42c0e481d70b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287472"
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

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
