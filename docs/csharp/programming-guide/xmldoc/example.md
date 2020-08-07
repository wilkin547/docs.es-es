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
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381533"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="47275-105">\<example> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="47275-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="47275-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47275-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="47275-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47275-107">Parameters</span></span>

- `description`

  <span data-ttu-id="47275-108">Una descripción del ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="47275-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="47275-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47275-109">Remarks</span></span>

<span data-ttu-id="47275-110">La etiqueta `<example>` le permite especificar un ejemplo de cómo usar un método u otro miembro de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="47275-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="47275-111">Esto normalmente implica el uso de la etiqueta [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="47275-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="47275-112">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="47275-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="47275-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47275-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="47275-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47275-114">See also</span></span>

- [<span data-ttu-id="47275-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="47275-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="47275-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="47275-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
