---
title: <seealso> - Guía de programación de C#
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
ms.openlocfilehash: ad22b423d085a152f47c4e34d7ee4247ef9836b8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789678"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="b6e54-102">\<seealso> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b6e54-102">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b6e54-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6e54-103">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="b6e54-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6e54-104">Parameters</span></span>

- <span data-ttu-id="b6e54-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="b6e54-105">cref = " `member`"</span></span>

  <span data-ttu-id="b6e54-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="b6e54-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b6e54-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member`</span><span class="sxs-lookup"><span data-stu-id="b6e54-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="b6e54-108">debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="b6e54-108">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="b6e54-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="b6e54-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="b6e54-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6e54-110">Remarks</span></span>

<span data-ttu-id="b6e54-111">La etiqueta \<seealso> le permite especificar el texto que quiere que aparezca en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="b6e54-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="b6e54-112">Use [\<see>](./see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="b6e54-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="b6e54-113">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="b6e54-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b6e54-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6e54-114">Example</span></span>

<span data-ttu-id="b6e54-115">Vea [\<summary>](./summary.md) para obtener un ejemplo del uso de \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="b6e54-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6e54-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6e54-116">See also</span></span>

- [<span data-ttu-id="b6e54-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b6e54-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b6e54-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="b6e54-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
