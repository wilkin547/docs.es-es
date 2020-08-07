---
title: <value> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML. <value> . Esta etiqueta le permite describir el valor que representa una propiedad.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380779"
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

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
