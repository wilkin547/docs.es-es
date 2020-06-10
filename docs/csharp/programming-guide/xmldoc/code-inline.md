---
title: <c> - Guía de programación de C#
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
ms.openlocfilehash: a09bcd069e2f85f4a21736cb218c42c0e481d70b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287472"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="9defc-102">\<c> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9defc-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="9defc-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9defc-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="9defc-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9defc-104">Parameters</span></span>

- `text`

  <span data-ttu-id="9defc-105">El texto que le gustaría indicar como código.</span><span class="sxs-lookup"><span data-stu-id="9defc-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9defc-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9defc-106">Remarks</span></span>

<span data-ttu-id="9defc-107">La etiqueta `<c>` le proporciona una manera de indicar que el texto dentro de una descripción debe marcarse como código.</span><span class="sxs-lookup"><span data-stu-id="9defc-107">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="9defc-108">Use [\<code>](./code.md) para indicar varias líneas como código.</span><span class="sxs-lookup"><span data-stu-id="9defc-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="9defc-109">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="9defc-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="9defc-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9defc-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="9defc-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="9defc-111">See also</span></span>

- [<span data-ttu-id="9defc-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9defc-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="9defc-113">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="9defc-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
