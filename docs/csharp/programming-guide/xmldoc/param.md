---
title: <param> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <param> . Esta etiqueta se usa en el comentario de una declaración de método para describir uno de los parámetros del método.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 1385365b2cdf18563686fdf4a5a1b17b89feafcd
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477997"
---
# <a name="param-c-programming-guide"></a>\<param> (guía de programación de C#)

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

La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método. Para documentar varios parámetros, use varias etiquetas `<param>`.

El texto de la etiqueta `<param>` se muestra en IntelliSense, el examinador de objetos y el informe web de comentario de código.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
