---
title: <list> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <list> . Esta etiqueta se usa para crear tablas y definiciones, viñetas o listas numeradas mediante bloques "item".
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 39674e3c07444e454dfeeceff6c99e65f34bb02f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478385"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="7ef0d-105">\<list> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7ef0d-105">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7ef0d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ef0d-106">Syntax</span></span>

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a><span data-ttu-id="7ef0d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ef0d-107">Parameters</span></span>

- `term`

  <span data-ttu-id="7ef0d-108">Término que se define en `description`.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-108">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="7ef0d-109">Elemento de una lista numerada o con viñetas, o definición de un `term`.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-109">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="7ef0d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ef0d-110">Remarks</span></span>

<span data-ttu-id="7ef0d-111">El bloque `<listheader>` se usa para definir la fila de encabezado de una tabla o de una lista de definiciones.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-111">The `<listheader>` block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="7ef0d-112">Cuando se define una tabla, solo es necesario suministrar una entrada para un término en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-112">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="7ef0d-113">Cada elemento de la lista se especifica con un bloque `<item>`.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="7ef0d-114">Cuando se crea una lista de definiciones, se deberán especificar tanto `term` como `description`.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-114">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="7ef0d-115">En cambio, para una tabla, lista con viñetas o lista numerada, solo es necesario suministrar una entrada para `description`.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-115">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="7ef0d-116">Una lista o una tabla pueden tener tantos bloques `<item>` como sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-116">A list or table can have as many `<item>` blocks as needed.</span></span>

<span data-ttu-id="7ef0d-117">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="7ef0d-117">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="7ef0d-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ef0d-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="7ef0d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ef0d-119">See also</span></span>

- [<span data-ttu-id="7ef0d-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7ef0d-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7ef0d-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="7ef0d-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
