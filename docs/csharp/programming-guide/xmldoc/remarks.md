---
title: <remarks> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <remarks> . Esta etiqueta se usa para agregar información sobre un tipo y complementa la información especificada con <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381507"
---
# <a name="remarks-c-programming-guide"></a>\<remarks> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Parámetros

- `Description`

  Descripción del miembro.

## <a name="remarks"></a>Comentarios

La etiqueta `<remarks>` se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](./summary.md). Esta información se muestra en la ventana Examinador de objetos.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
