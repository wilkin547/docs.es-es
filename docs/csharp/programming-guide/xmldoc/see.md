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
ms.openlocfilehash: 1cc4982d1ebe9d6896404218a6d200b10cc6503f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381936"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="1a2ea-104">\<see> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1a2ea-104">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1a2ea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a2ea-105">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="1a2ea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a2ea-106">Parameters</span></span>

- <span data-ttu-id="1a2ea-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="1a2ea-107">cref = "`member`"</span></span>

  <span data-ttu-id="1a2ea-108">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-108">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="1a2ea-109">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-109">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="1a2ea-110">Agregue *member* entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="1a2ea-110">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="1a2ea-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1a2ea-111">Remarks</span></span>

<span data-ttu-id="1a2ea-112">La etiqueta `<see>` permite especificar un vínculo desde el texto.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-112">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="1a2ea-113">Use [\<seealso>](./seealso.md) para indicar que el texto debe colocarse en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-113">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="1a2ea-114">Use el [atributo cref](./cref-attribute.md) para crear hipervínculos internos a las páginas de documentación de los elementos de código.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-114">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="1a2ea-115">Además, ``href`` es un atributo válido que actúa como un hipervínculo.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-115">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="1a2ea-116">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="1a2ea-117">En el ejemplo siguiente, se muestra una etiqueta `<see>` dentro de una sección de resumen.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-117">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="1a2ea-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a2ea-118">See also</span></span>

- [<span data-ttu-id="1a2ea-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1a2ea-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="1a2ea-120">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="1a2ea-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
