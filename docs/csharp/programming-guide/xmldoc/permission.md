---
title: <permission> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 4f76d28d5531c1b9f01fa950589407934cc1244a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093479"
---
# <a name="permission-c-programming-guide"></a>\<permission> (Guía de programación de C#)

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

La etiqueta \<permission> le permite documentar el acceso de un miembro. La clase <xref:System.Security.PermissionSet> le permite especificar el acceso a un miembro.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
