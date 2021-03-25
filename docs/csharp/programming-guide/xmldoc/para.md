---
title: <para> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <para> . Esta etiqueta le permite agregar la estructura al texto de otra etiqueta, como <summary>, <remarks>o <returns>.
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 5cb1c22dceae7a45a47fcb8807303d11e1220935
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478010"
---
# <a name="para-c-programming-guide"></a>\<para> (guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<para>content</para>
```

## <a name="parameters"></a>Parámetros

- `content`

  El texto del párrafo.

## <a name="remarks"></a>Comentarios

La etiqueta `<para>` se usa dentro de otra etiqueta, como [\<summary>](./summary.md), [\<remarks>](./remarks.md) o [\<returns>](./returns.md), y permite dar una estructura al texto.

Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.

## <a name="example"></a>Ejemplo

Vea [\<summary>](./summary.md) para obtener un ejemplo en el que se usa `<para>`.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
