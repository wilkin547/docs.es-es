---
title: <seealso> - Guía de programación de C#
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
ms.openlocfilehash: e24d5910ab21f01aebb5a32ce7646cf56886a81a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093466"
---
# <a name="seealso-c-programming-guide"></a>\<seealso> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a>Parámetros

- cref = "`member`"

  Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member` debe aparecer entre comillas dobles (" ").

  Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [Atributo cref](./cref-attribute.md).

## <a name="remarks"></a>Comentarios

La etiqueta \<seealso> le permite especificar el texto que quiere que aparezca en una sección Vea también. Use [\<see>](./see.md) para especificar un vínculo desde dentro del texto.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

Vea [\<summary>](./summary.md) para obtener un ejemplo del uso de \<seealso>.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
