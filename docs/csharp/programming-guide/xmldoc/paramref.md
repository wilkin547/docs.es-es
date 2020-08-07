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
ms.openlocfilehash: 133f43abfaf349806404d6d37fb472e3145c51b7
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381845"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="3c110-104">\<paramref> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3c110-104">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="3c110-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c110-105">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="3c110-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c110-106">Parameters</span></span>

- `name`

  <span data-ttu-id="3c110-107">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="3c110-107">The name of the parameter to refer to.</span></span> <span data-ttu-id="3c110-108">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="3c110-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="3c110-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c110-109">Remarks</span></span>

<span data-ttu-id="3c110-110">La etiqueta `<paramref>` ofrece una manera de indicar que una palabra en los comentarios del código (por ejemplo, en un bloque `<summary>` o `<remarks>`) hace referencia a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="3c110-110">The `<paramref>` tag gives you a way to indicate that a word in the code comments, for example in a `<summary>` or `<remarks>` block refers to a parameter.</span></span> <span data-ttu-id="3c110-111">El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, por ejemplo, con una fuente en negrita o cursiva.</span><span class="sxs-lookup"><span data-stu-id="3c110-111">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="3c110-112">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="3c110-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="3c110-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c110-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="3c110-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c110-114">See also</span></span>

- [<span data-ttu-id="3c110-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3c110-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3c110-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="3c110-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
