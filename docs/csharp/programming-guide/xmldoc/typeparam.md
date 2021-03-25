---
title: <typeparam> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <typeparam> . Esta etiqueta se usa en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 1b9d5d30c1a507e3bb7938ee0c036cdac3ef2f90
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477679"
---
# <a name="typeparam-c-programming-guide"></a>\<typeparam> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a>Parámetros

- `name`

  El nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").

- `description`

  Una descripción del parámetro de tipo.

## <a name="remarks"></a>Comentarios

La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo. Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.

Para más información, vea [Genéricos](../generics/index.md).

El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
