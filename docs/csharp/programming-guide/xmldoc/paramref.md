---
title: <paramref> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <paramref>. Esta etiqueta ofrece una manera de indicar que una palabra del código es un parámetro.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e559a899aad7806bb7ccef32be49954fabed6a32
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477875"
---
# <a name="paramref-c-programming-guide"></a>\<paramref> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<paramref name="name"/>
```

## <a name="parameters"></a>Parámetros

- `name`

  Nombre del parámetro al que se hace referencia. Ponga el nombre entre comillas dobles (" ").

## <a name="remarks"></a>Comentarios

La etiqueta `<paramref>` ofrece una manera de indicar que una palabra en los comentarios del código (por ejemplo, en un bloque `<summary>` o `<remarks>`) hace referencia a un parámetro. El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, por ejemplo, con una fuente en negrita o cursiva.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
