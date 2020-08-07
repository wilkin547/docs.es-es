---
title: <returns> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <returns> . Esta etiqueta se usa en el comentario de una declaración de método para describir el valor devuelto.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381403"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="b7c42-105">\<returns> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b7c42-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b7c42-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7c42-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="b7c42-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7c42-107">Parameters</span></span>

- `description`

  <span data-ttu-id="b7c42-108">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b7c42-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7c42-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7c42-109">Remarks</span></span>

<span data-ttu-id="b7c42-110">La etiqueta `<returns>` debe usarse en el comentario de una declaración de método para describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b7c42-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="b7c42-111">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="b7c42-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b7c42-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7c42-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="b7c42-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7c42-113">See also</span></span>

- [<span data-ttu-id="b7c42-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b7c42-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b7c42-115">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="b7c42-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
