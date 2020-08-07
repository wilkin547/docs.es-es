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
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380792"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="608a0-105">\<typeparam> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="608a0-105">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="608a0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="608a0-106">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="608a0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="608a0-107">Parameters</span></span>

- `name`

  <span data-ttu-id="608a0-108">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="608a0-108">The name of the type parameter.</span></span> <span data-ttu-id="608a0-109">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="608a0-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="608a0-110">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="608a0-110">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="608a0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="608a0-111">Remarks</span></span>

<span data-ttu-id="608a0-112">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="608a0-112">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="608a0-113">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="608a0-113">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="608a0-114">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="608a0-114">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="608a0-115">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).</span><span class="sxs-lookup"><span data-stu-id="608a0-115">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="608a0-116">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="608a0-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="608a0-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="608a0-117">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="608a0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="608a0-118">See also</span></span>

- [<span data-ttu-id="608a0-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="608a0-119">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="608a0-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="608a0-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="608a0-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="608a0-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
