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
ms.openlocfilehash: 6a098208a51ca31fe2278b7c696deb15a13f8e1e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477810"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="7ec38-105">\<returns> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7ec38-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7ec38-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ec38-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="7ec38-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ec38-107">Parameters</span></span>

- `description`

  <span data-ttu-id="7ec38-108">Descripción del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="7ec38-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ec38-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ec38-109">Remarks</span></span>

<span data-ttu-id="7ec38-110">La etiqueta `<returns>` debe usarse en el comentario de una declaración de método para describir el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="7ec38-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="7ec38-111">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="7ec38-111">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="7ec38-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ec38-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="7ec38-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec38-113">See also</span></span>

- [<span data-ttu-id="7ec38-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7ec38-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7ec38-115">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="7ec38-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
