---
title: <para> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: b2740370106ce5b2812acbea212354ebea1f0e34
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793421"
---
# <a name="para-c-programming-guide"></a>\<para> (Guía de programación de C#)

## <a name="syntax"></a>Sintaxis

```xml
<para>content</para>
```

## <a name="parameters"></a>Parámetros

- `content`

  El texto del párrafo.

## <a name="remarks"></a>Comentarios

La etiqueta \<para> se usa dentro de otra etiqueta, como [\<summary>](./summary.md), [\<remarks>](./remarks.md) o [\<returns>](./returns.md), y permite dar una estructura al texto.

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

Vea [\<summary>](./summary.md) para obtener un ejemplo del uso de \<para>.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
