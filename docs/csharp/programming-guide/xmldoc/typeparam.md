---
title: <typeparam> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <typeparam> . Esta etiqueta se usa en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 1b9d5d30c1a507e3bb7938ee0c036cdac3ef2f90
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477679"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="22af2-105">\<typeparam> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="22af2-105">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="22af2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22af2-106">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="22af2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22af2-107">Parameters</span></span>

- `name`

  <span data-ttu-id="22af2-108">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="22af2-108">The name of the type parameter.</span></span> <span data-ttu-id="22af2-109">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="22af2-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="22af2-110">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="22af2-110">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="22af2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22af2-111">Remarks</span></span>

<span data-ttu-id="22af2-112">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="22af2-112">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="22af2-113">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="22af2-113">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="22af2-114">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="22af2-114">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="22af2-115">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).</span><span class="sxs-lookup"><span data-stu-id="22af2-115">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="22af2-116">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="22af2-116">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="22af2-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22af2-117">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="22af2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="22af2-118">See also</span></span>

- [<span data-ttu-id="22af2-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="22af2-119">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="22af2-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="22af2-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="22af2-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="22af2-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
