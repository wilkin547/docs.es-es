---
title: <typeparamref> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789657"
---
# <a name="typeparamref-c-programming-guide"></a>\<typeparamref> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a>Parámetros

- `name`

  Nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").

## <a name="remarks"></a>Comentarios

Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../generics/index.md).

Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
