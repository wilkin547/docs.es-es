---
title: <value> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <value> . Esta etiqueta le permite describir el valor que representa una propiedad.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: c910a60a50e95621c1e3ad773000cbac0d43bb10
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477643"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="f2480-105">\<value> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f2480-105">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="f2480-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2480-106">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="f2480-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2480-107">Parameters</span></span>

- `property-description`

  <span data-ttu-id="f2480-108">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="f2480-108">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2480-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2480-109">Remarks</span></span>

<span data-ttu-id="f2480-110">La etiqueta `<value>` le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="f2480-110">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="f2480-111">Cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](./summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="f2480-111">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="f2480-112">Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="f2480-112">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="f2480-113">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="f2480-113">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="f2480-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f2480-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="f2480-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2480-115">See also</span></span>

- [<span data-ttu-id="f2480-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f2480-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="f2480-117">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="f2480-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
