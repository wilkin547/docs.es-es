---
title: <param> - Guía de programación de C#
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 396ed716c246091a674268020261069f36dd2be8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287329"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="360b9-102">\<param> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="360b9-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="360b9-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="360b9-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="360b9-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="360b9-104">Parameters</span></span>

- `name`

  <span data-ttu-id="360b9-105">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="360b9-105">The name of a method parameter.</span></span> <span data-ttu-id="360b9-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="360b9-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="360b9-107">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="360b9-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="360b9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="360b9-108">Remarks</span></span>

<span data-ttu-id="360b9-109">La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="360b9-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="360b9-110">Para documentar varios parámetros, use varias etiquetas `<param>`.</span><span class="sxs-lookup"><span data-stu-id="360b9-110">To document multiple parameters, use multiple `<param>` tags.</span></span>

<span data-ttu-id="360b9-111">El texto de la etiqueta `<param>` se muestra en IntelliSense, el examinador de objetos y el informe web de comentario de código.</span><span class="sxs-lookup"><span data-stu-id="360b9-111">The text for the `<param>` tag is displayed in IntelliSense, the Object Browser, and the Code Comment Web Report.</span></span>

<span data-ttu-id="360b9-112">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="360b9-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="360b9-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="360b9-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="360b9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="360b9-114">See also</span></span>

- [<span data-ttu-id="360b9-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="360b9-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="360b9-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="360b9-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
