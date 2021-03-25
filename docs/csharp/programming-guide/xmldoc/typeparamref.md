---
title: <typeparamref> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <typeparamref>. Esta etiqueta permite que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo, en cursiva.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 1bb9a73f4122f3b9d521565a7172a9b8f75f7a98
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477670"
---
# <a name="typeparamref-c-programming-guide"></a>\<typeparamref> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a>Parámetros

- `name`

  El nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").

## <a name="remarks"></a>Comentarios

Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../generics/index.md).

Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
