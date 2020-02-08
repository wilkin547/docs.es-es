---
title: <value> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 120805346672738e614743ab8c98388b8dbac0f7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793344"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="9a2ca-102">\<value> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9a2ca-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="9a2ca-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a2ca-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="9a2ca-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a2ca-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="9a2ca-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a2ca-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a2ca-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9a2ca-106">Remarks</span></span>

<span data-ttu-id="9a2ca-107">La etiqueta \<value> le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a2ca-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="9a2ca-108">Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](./summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a2ca-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="9a2ca-109">Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a2ca-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>

<span data-ttu-id="9a2ca-110">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="9a2ca-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="9a2ca-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a2ca-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="9a2ca-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a2ca-112">See also</span></span>

- [<span data-ttu-id="9a2ca-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9a2ca-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="9a2ca-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="9a2ca-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
