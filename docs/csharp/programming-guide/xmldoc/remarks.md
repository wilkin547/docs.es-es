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
ms.openlocfilehash: 2227dd8bd4d81f5fda8cf529e18c7a613cca6b8e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477829"
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

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
