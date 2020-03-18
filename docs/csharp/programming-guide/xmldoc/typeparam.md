---
title: <typeparam> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793362"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="a4474-102">\<typeparam> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a4474-102">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4474-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4474-103">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="a4474-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4474-104">Parameters</span></span>

- `name`

  <span data-ttu-id="a4474-105">Nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="a4474-105">The name of the type parameter.</span></span> <span data-ttu-id="a4474-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="a4474-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="a4474-107">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="a4474-107">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4474-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4474-108">Remarks</span></span>

<span data-ttu-id="a4474-109">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="a4474-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="a4474-110">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="a4474-110">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="a4474-111">Para más información, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="a4474-111">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="a4474-112">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser).</span><span class="sxs-lookup"><span data-stu-id="a4474-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="a4474-113">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="a4474-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="a4474-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4474-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="a4474-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4474-115">See also</span></span>

- [<span data-ttu-id="a4474-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a4474-116">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="a4474-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a4474-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a4474-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="a4474-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
