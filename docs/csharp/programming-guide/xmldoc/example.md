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
ms.openlocfilehash: 8f9b4fa4ac447b853008576a46be9beeb583b018
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103479117"
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

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
