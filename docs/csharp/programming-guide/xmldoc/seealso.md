---
title: <seealso> - Guía de programación de C#
description: Aprenda a utilizar el XML. <seealso> . Esta etiqueta le permite especificar el texto que quiere que aparezca en una sección "Consulte también".
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: c5baefbfca3a94095a90eb43c2bf13eb924c8cdc
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477760"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="245bc-105">\<seealso> (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="245bc-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="245bc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="245bc-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="245bc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="245bc-107">Parameters</span></span>

- <span data-ttu-id="245bc-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="245bc-108">cref = " `member`"</span></span>

  <span data-ttu-id="245bc-109">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="245bc-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="245bc-110">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member`</span><span class="sxs-lookup"><span data-stu-id="245bc-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="245bc-111">debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="245bc-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="245bc-112">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [Atributo cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="245bc-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="245bc-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="245bc-113">Remarks</span></span>

<span data-ttu-id="245bc-114">La etiqueta `<seealso>` le permite especificar el texto que quiere que aparezca en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="245bc-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="245bc-115">Use [\<see>](./see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="245bc-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="245bc-116">Realice la compilación con [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="245bc-116">Compile with [**DocumentationFile**](../../language-reference/compiler-options/output.md#documentationfile) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="245bc-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="245bc-117">Example</span></span>

<span data-ttu-id="245bc-118">Vea [\<summary>](./summary.md) para obtener un ejemplo en el que se usa \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="245bc-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="245bc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="245bc-119">See also</span></span>

- [<span data-ttu-id="245bc-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="245bc-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="245bc-121">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="245bc-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
