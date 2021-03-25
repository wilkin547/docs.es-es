---
title: <returns> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <returns> . Esta etiqueta se usa en el comentario de una declaración de método para describir el valor devuelto.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 6a098208a51ca31fe2278b7c696deb15a13f8e1e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477810"
---
# <a name="returns-c-programming-guide"></a>\<returns> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<returns>description</returns>
```

## <a name="parameters"></a>Parámetros

- `description`

  Descripción del valor devuelto.

## <a name="remarks"></a>Comentarios

La etiqueta `<returns>` debe usarse en el comentario de una declaración de método para describir el valor devuelto.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
