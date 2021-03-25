---
title: <exception> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <exception>. Esta etiqueta le permite especificar qué excepciones se pueden iniciar, y se puede aplicar a métodos, propiedades, eventos e indexadores.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 37d119e3cde115104d149d8f35b8937efddd70d4
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103479116"
---
# <a name="exception-c-programming-guide"></a>\<exception> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a>Parámetros

- cref = "`member`"

  Una referencia a una excepción que está disponible desde el entorno de compilación actual. El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML. `member` debe aparecer entre comillas dobles (" ").

  Para más información sobre cómo dar formato a `member` para hacer referencia a un tipo genérico, consulte [Procesar el archivo XML](processing-the-xml-file.md).

- `description`

  Descripción de la excepción.

## <a name="remarks"></a>Comentarios

La etiqueta `<exception>` le permite especificar qué excepciones se pueden producir. Esta etiqueta se puede aplicar a definiciones de métodos, propiedades, eventos e indizadores.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

Para más información sobre el control de excepciones, vea [Excepciones y control de excepciones](../exceptions/index.md).

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](recommended-tags-for-documentation-comments.md)
