---
title: <paramref> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <paramref>. Esta etiqueta ofrece una manera de indicar que una palabra del código es un parámetro.
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: e559a899aad7806bb7ccef32be49954fabed6a32
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477875"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="39025-104">\<paramref> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="39025-104">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="39025-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39025-105">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="39025-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39025-106">Parameters</span></span>

- `name`

  <span data-ttu-id="39025-107">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="39025-107">The name of the parameter to refer to.</span></span> <span data-ttu-id="39025-108">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="39025-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="39025-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39025-109">Remarks</span></span>

<span data-ttu-id="39025-110">La etiqueta `<paramref>` ofrece una manera de indicar que una palabra en los comentarios del código (por ejemplo, en un bloque `<summary>` o `<remarks>`) hace referencia a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="39025-110">The `<paramref>` tag gives you a way to indicate that a word in the code comments, for example in a `<summary>` or `<remarks>` block refers to a parameter.</span></span> <span data-ttu-id="39025-111">El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, por ejemplo, con una fuente en negrita o cursiva.</span><span class="sxs-lookup"><span data-stu-id="39025-111">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="39025-112">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="39025-112">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="39025-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39025-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="39025-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="39025-114">See also</span></span>

- [<span data-ttu-id="39025-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="39025-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="39025-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="39025-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
