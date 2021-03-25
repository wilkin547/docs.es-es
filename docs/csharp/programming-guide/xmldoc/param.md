---
title: <param> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <param> . Esta etiqueta se usa en el comentario de una declaración de método para describir uno de los parámetros del método.
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 1385365b2cdf18563686fdf4a5a1b17b89feafcd
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477997"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="40c32-105">\<param> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="40c32-105">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="40c32-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40c32-106">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="40c32-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40c32-107">Parameters</span></span>

- `name`

  <span data-ttu-id="40c32-108">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="40c32-108">The name of a method parameter.</span></span> <span data-ttu-id="40c32-109">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="40c32-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="40c32-110">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="40c32-110">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="40c32-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40c32-111">Remarks</span></span>

<span data-ttu-id="40c32-112">La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="40c32-112">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="40c32-113">Para documentar varios parámetros, use varias etiquetas `<param>`.</span><span class="sxs-lookup"><span data-stu-id="40c32-113">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="40c32-114">El texto de la etiqueta `<param>` se muestra en IntelliSense, el examinador de objetos y el informe web de comentario de código.</span><span class="sxs-lookup"><span data-stu-id="40c32-114">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="40c32-115">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="40c32-115">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="40c32-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40c32-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="40c32-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c32-117">See also</span></span>

- [<span data-ttu-id="40c32-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="40c32-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="40c32-119">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="40c32-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
