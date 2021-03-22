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
ms.openlocfilehash: 2227dd8bd4d81f5fda8cf529e18c7a613cca6b8e
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477829"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="63ca0-106">\<remarks> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="63ca0-106">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="63ca0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63ca0-107">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="63ca0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63ca0-108">Parameters</span></span>

- `Description`

  <span data-ttu-id="63ca0-109">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="63ca0-109">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="63ca0-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63ca0-110">Remarks</span></span>

<span data-ttu-id="63ca0-111">La etiqueta `<remarks>` se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="63ca0-111">The `<remarks>` tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="63ca0-112">Esta información se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="63ca0-112">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="63ca0-113">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="63ca0-113">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="63ca0-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63ca0-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="63ca0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ca0-115">See also</span></span>

- [<span data-ttu-id="63ca0-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="63ca0-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="63ca0-117">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="63ca0-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
