---
title: <value> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: bd6630a8d5894fda39ad289c8dd584f6d84e5490
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287199"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="8162b-102">\<value> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8162b-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="8162b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8162b-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="8162b-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8162b-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="8162b-105">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8162b-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="8162b-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8162b-106">Remarks</span></span>

<span data-ttu-id="8162b-107">La etiqueta `<value>` le permite describir el valor que representa una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8162b-107">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="8162b-108">Cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](./summary.md) para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="8162b-108">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="8162b-109">Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.</span><span class="sxs-lookup"><span data-stu-id="8162b-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="8162b-110">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="8162b-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="8162b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8162b-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="8162b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8162b-112">See also</span></span>

- [<span data-ttu-id="8162b-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8162b-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="8162b-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="8162b-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
