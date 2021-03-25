---
title: <see> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <see>. Esta etiqueta le permite especificar un vínculo desde dentro del texto, por ejemplo, mediante un atributo cref.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 154feca5e7e4f4d3f5313c4ae05cd991e69e298f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477773"
---
# <a name="see-c-programming-guide"></a>\<see> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Parámetros

- cref = "`member`"

  Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML. Agregue *member* entre comillas dobles (" ").

## <a name="remarks"></a>Comentarios

La etiqueta `<see>` permite especificar un vínculo desde el texto. Use [\<seealso>](./seealso.md) para indicar que el texto debe colocarse en una sección Vea también. Use el [atributo cref](./cref-attribute.md) para crear hipervínculos internos a las páginas de documentación de los elementos de código. Además, ``href`` es un atributo válido que actúa como un hipervínculo.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

En el ejemplo siguiente, se muestra una etiqueta `<see>` dentro de una sección de resumen.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
