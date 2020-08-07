---
title: <value> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML. <value> . Esta etiqueta le permite describir el valor que representa una propiedad.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380779"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="8ea5c-105">\<value> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8ea5c-105">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8ea5c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ea5c-106">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="8ea5c-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8ea5c-107">Parameters</span></span>

- `property-description`

  <span data-ttu-id="8ea5c-108">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ea5c-108">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ea5c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ea5c-109">Remarks</span></span>

<span data-ttu-id="8ea5c-110">La etiqueta `<value>` le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ea5c-110">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="8ea5c-111">Cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](./summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ea5c-111">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="8ea5c-112">Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ea5c-112">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="8ea5c-113">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="8ea5c-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8ea5c-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ea5c-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="8ea5c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ea5c-115">See also</span></span>

- [<span data-ttu-id="8ea5c-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8ea5c-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="8ea5c-117">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="8ea5c-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
