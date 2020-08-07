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
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381403"
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

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
