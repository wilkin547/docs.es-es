---
title: <c> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <c>. Esta etiqueta marca el texto de una sola línea en una descripción como código, mientras que <code> indicates multiple lines..
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: fc445c7245287c3835543e4bbe4b3b46ec46fd35
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478691"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="0a384-104">\<c> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0a384-104">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0a384-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a384-105">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="0a384-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a384-106">Parameters</span></span>

- `text`

  <span data-ttu-id="0a384-107">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="0a384-107">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a384-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0a384-108">Remarks</span></span>

<span data-ttu-id="0a384-109">La etiqueta `<c>` le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="0a384-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="0a384-110">Use [\<code>](./code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="0a384-110">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="0a384-111">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="0a384-111">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="0a384-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a384-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="0a384-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a384-113">See also</span></span>

- [<span data-ttu-id="0a384-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0a384-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="0a384-115">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="0a384-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
