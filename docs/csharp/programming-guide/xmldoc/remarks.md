---
title: <remarks> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <remarks> . Esta etiqueta se usa para agregar información sobre un tipo y complementa la información especificada con <summary>.
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: d38905d100e24158e7a1412f6be9f01a7ced2382
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381507"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="40f6b-106">\<remarks> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="40f6b-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="40f6b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40f6b-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="40f6b-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40f6b-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="40f6b-109">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="40f6b-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="40f6b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40f6b-110">Remarks</span></span>

<span data-ttu-id="40f6b-111">La etiqueta `<remarks>` se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="40f6b-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="40f6b-112">Esta información se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="40f6b-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="40f6b-113">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="40f6b-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="40f6b-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40f6b-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="40f6b-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40f6b-115">See also</span></span>

- [<span data-ttu-id="40f6b-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="40f6b-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="40f6b-117">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="40f6b-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
