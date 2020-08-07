---
title: <example> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <example> . Esta etiqueta le permite especificar un ejemplo de cómo usar un método u otro miembro de la biblioteca.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381533"
---
# <a name="example-c-programming-guide"></a>\<example> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<example>description</example>
```

## <a name="parameters"></a>Parámetros

- `description`

  Una descripción del ejemplo de código.

## <a name="remarks"></a>Comentarios

La etiqueta `<example>` le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca. Esto normalmente implica el uso de la etiqueta [\<code>](./code.md).

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Consulte también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
