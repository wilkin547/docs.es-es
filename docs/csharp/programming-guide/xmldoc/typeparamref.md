---
title: <typeparamref> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <typeparamref>. Esta etiqueta permite que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo, en cursiva.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 1bb9a73f4122f3b9d521565a7172a9b8f75f7a98
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477670"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="af3ed-104">\<typeparamref> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="af3ed-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="af3ed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af3ed-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="af3ed-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="af3ed-106">Parameters</span></span>

- `name`

  <span data-ttu-id="af3ed-107">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="af3ed-107">The name of the type parameter.</span></span> <span data-ttu-id="af3ed-108">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="af3ed-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="af3ed-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af3ed-109">Remarks</span></span>

<span data-ttu-id="af3ed-110">Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="af3ed-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="af3ed-111">Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.</span><span class="sxs-lookup"><span data-stu-id="af3ed-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="af3ed-112">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="af3ed-112">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="af3ed-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af3ed-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="af3ed-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="af3ed-114">See also</span></span>

- [<span data-ttu-id="af3ed-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="af3ed-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="af3ed-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="af3ed-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
