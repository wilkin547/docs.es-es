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
ms.openlocfilehash: a9e3b2e86528afcbe1330788e248f0143efb5c1b
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381559"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="1f2d0-105">\<param> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1f2d0-105">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1f2d0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f2d0-106">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="1f2d0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f2d0-107">Parameters</span></span>

- `name`

  <span data-ttu-id="1f2d0-108">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="1f2d0-108">The name of a method parameter.</span></span> <span data-ttu-id="1f2d0-109">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="1f2d0-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="1f2d0-110">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1f2d0-110">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f2d0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f2d0-111">Remarks</span></span>

<span data-ttu-id="1f2d0-112">La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="1f2d0-112">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="1f2d0-113">Para documentar varios parámetros, use varias etiquetas `<param>`.</span><span class="sxs-lookup"><span data-stu-id="1f2d0-113">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="1f2d0-114">El texto de la etiqueta `<param>` se muestra en IntelliSense, el examinador de objetos y el informe web de comentario de código.</span><span class="sxs-lookup"><span data-stu-id="1f2d0-114">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="1f2d0-115">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="1f2d0-115">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="1f2d0-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f2d0-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="1f2d0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f2d0-117">See also</span></span>

- [<span data-ttu-id="1f2d0-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1f2d0-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="1f2d0-119">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="1f2d0-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
