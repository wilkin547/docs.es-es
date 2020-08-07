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
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381858"
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

Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.

## <a name="example"></a>Ejemplo

Vea [\<summary>](./summary.md) para obtener un ejemplo en el que se usa `<para>`.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Etiquetas recomendadas para los comentarios de documentación](./recommended-tags-for-documentation-comments.md)
