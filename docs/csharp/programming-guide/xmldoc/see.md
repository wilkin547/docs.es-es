---
title: <see> - Guía de programación de C#
description: Aprenda sobre la etiqueta XML <see>. Esta etiqueta le permite especificar un vínculo desde dentro del texto, por ejemplo, mediante un atributo cref.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 154feca5e7e4f4d3f5313c4ae05cd991e69e298f
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477773"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="881f3-104">\<see> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="881f3-104">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="881f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="881f3-105">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="881f3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="881f3-106">Parameters</span></span>

- <span data-ttu-id="881f3-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="881f3-107">cref = "`member`"</span></span>

  <span data-ttu-id="881f3-108">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="881f3-108">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="881f3-109">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="881f3-109">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="881f3-110">Agregue *member* entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="881f3-110">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="881f3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="881f3-111">Remarks</span></span>

<span data-ttu-id="881f3-112">La etiqueta `<see>` permite especificar un vínculo desde el texto.</span><span class="sxs-lookup"><span data-stu-id="881f3-112">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="881f3-113">Use [\<seealso>](./seealso.md) para indicar que el texto debe colocarse en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="881f3-113">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="881f3-114">Use el [atributo cref](./cref-attribute.md) para crear hipervínculos internos a las páginas de documentación de los elementos de código.</span><span class="sxs-lookup"><span data-stu-id="881f3-114">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="881f3-115">Además, ``href`` es un atributo válido que actúa como un hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="881f3-115">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="881f3-116">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="881f3-116">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

<span data-ttu-id="881f3-117">En el ejemplo siguiente, se muestra una etiqueta `<see>` dentro de una sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="881f3-117">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="881f3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="881f3-118">See also</span></span>

- [<span data-ttu-id="881f3-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="881f3-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="881f3-120">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="881f3-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
