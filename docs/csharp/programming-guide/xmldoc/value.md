---
title: <value> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <value> . Esta etiqueta le permite describir el valor que representa una propiedad.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: c910a60a50e95621c1e3ad773000cbac0d43bb10
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477643"
---
# <a name="value-c-programming-guide"></a>\<value> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<value>property-description</value>
```

## <a name="parameters"></a>Parámetros

- `property-description`

  Una descripción de la propiedad.

## <a name="remarks"></a>Comentarios

La etiqueta `<value>` le permite describir el valor que representa una propiedad. Cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](./summary.md) para la nueva propiedad. Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
