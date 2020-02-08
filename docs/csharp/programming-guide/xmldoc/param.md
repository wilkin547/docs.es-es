---
title: <param> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789757"
---
# <a name="param-c-programming-guide"></a>\<param> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>Parámetros

- `name`

  Nombre de un parámetro de método. Ponga el nombre entre comillas dobles (" ").

- `description`

  Descripción del parámetro.

## <a name="remarks"></a>Comentarios

La etiqueta \<param> debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método. Para documentar varios parámetros, use varias etiquetas \<param>.

El texto de la etiqueta \<param> se mostrará en IntelliSense, el Examinador de objetos y en el informe web de comentario de código.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
