---
title: <example> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <example> . Esta etiqueta le permite especificar un ejemplo de cómo usar un método u otro miembro de la biblioteca.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: 8f9b4fa4ac447b853008576a46be9beeb583b018
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103479117"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="2d6fc-105">\<example> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2d6fc-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="2d6fc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d6fc-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="2d6fc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d6fc-107">Parameters</span></span>

- `description`

  <span data-ttu-id="2d6fc-108">Una descripción del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="2d6fc-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="2d6fc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d6fc-109">Remarks</span></span>

<span data-ttu-id="2d6fc-110">La etiqueta `<example>` le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2d6fc-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="2d6fc-111">Esto normalmente implica el uso de la etiqueta [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="2d6fc-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="2d6fc-112">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="2d6fc-112">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="2d6fc-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2d6fc-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="2d6fc-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d6fc-114">See also</span></span>

- [<span data-ttu-id="2d6fc-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2d6fc-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2d6fc-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="2d6fc-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
