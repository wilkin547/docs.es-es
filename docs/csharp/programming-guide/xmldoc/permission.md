---
title: <permission> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <permission> . Esta etiqueta le permite documentar el acceso de un miembro, mientras que la clase PermissionSet permite especificar el acceso a un miembro.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 379d3fda06c50e9e988784e671061d604e6e5b36
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477854"
---
# <a name="permission-c-programming-guide"></a>\<permission> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a>Parámetros

- cref = "`member`"

  Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual. El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML. *member* debe aparecer entre comillas dobles (" ").

  Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [Atributo cref](./cref-attribute.md).

- `description`

  Descripción del acceso al miembro.

## <a name="remarks"></a>Comentarios

La etiqueta `<permission>` le permite documentar el acceso de un miembro. La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
