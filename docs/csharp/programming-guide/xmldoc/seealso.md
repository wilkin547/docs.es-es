---
title: <seealso> - Guía de programación de C#
description: Aprenda a utilizar el XML. <seealso> . Esta etiqueta le permite especificar el texto que quiere que aparezca en una sección "Consulte también".
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: c5baefbfca3a94095a90eb43c2bf13eb924c8cdc
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477760"
---
# <a name="seealso-c-programming-guide"></a>\<seealso> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a>Parámetros

- cref = "`member`"

  Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member` debe aparecer entre comillas dobles (" ").

  Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [Atributo cref](./cref-attribute.md).

## <a name="remarks"></a>Comentarios

La etiqueta `<seealso>` le permite especificar el texto que quiere que aparezca en una sección Vea también. Use [\<see>](./see.md) para especificar un vínculo desde dentro del texto.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

Vea [\<summary>](./summary.md) para obtener un ejemplo en el que se usa \<seealso>.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
