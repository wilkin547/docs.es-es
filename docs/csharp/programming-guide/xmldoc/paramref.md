---
title: <paramref> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 12df257271369dc7f0a5c066b712a8d8e6c38761
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793399"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="cab7d-102">\<paramref> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cab7d-102">\<paramref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="cab7d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cab7d-103">Syntax</span></span>

```xml
<paramref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="cab7d-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cab7d-104">Parameters</span></span>

- `name`

  <span data-ttu-id="cab7d-105">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="cab7d-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="cab7d-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="cab7d-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="cab7d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cab7d-107">Remarks</span></span>

<span data-ttu-id="cab7d-108">La etiqueta \<paramref> ofrece una manera de indicar que una palabra en los comentarios del código (por ejemplo, en un bloque \<summary> o \<comments>) hace referencia a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="cab7d-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="cab7d-109">El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, por ejemplo, con una fuente en negrita o cursiva.</span><span class="sxs-lookup"><span data-stu-id="cab7d-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>

<span data-ttu-id="cab7d-110">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="cab7d-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="cab7d-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cab7d-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]

## <a name="see-also"></a><span data-ttu-id="cab7d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cab7d-112">See also</span></span>

- [<span data-ttu-id="cab7d-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cab7d-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cab7d-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="cab7d-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
