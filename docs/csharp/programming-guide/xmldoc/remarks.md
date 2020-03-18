---
title: <remarks> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793371"
---
# <a name="remarks-c-programming-guide"></a>\<remarks> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a>Parámetros

- `Description`

  Descripción del miembro.

## <a name="remarks"></a>Comentarios

La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](./summary.md). Esta información se muestra en la ventana Examinador de objetos.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
