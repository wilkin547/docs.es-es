---
title: <returns> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 7bc950a8d89a3ac2b5c3b7a68e05c7778e97f85c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287238"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="f81d8-102">\<returns> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f81d8-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="f81d8-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f81d8-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="f81d8-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f81d8-104">Parameters</span></span>

- `description`

  <span data-ttu-id="f81d8-105">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f81d8-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="f81d8-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f81d8-106">Remarks</span></span>

<span data-ttu-id="f81d8-107">La etiqueta `<returns>` debe usarse en el comentario de una declaración de método para describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="f81d8-107">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="f81d8-108">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="f81d8-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="f81d8-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f81d8-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="f81d8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f81d8-110">See also</span></span>

- [<span data-ttu-id="f81d8-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f81d8-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="f81d8-112">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="f81d8-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
