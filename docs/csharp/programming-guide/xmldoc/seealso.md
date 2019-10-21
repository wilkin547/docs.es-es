---
title: <seealso> - Guía de programación de C#
ms.custom: seodec18
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
ms.openlocfilehash: 430270c170f2829d9bf9b90d258c948176b9c086
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523326"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="5fd6b-102">\<seealso> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5fd6b-102">\<seealso> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5fd6b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fd6b-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fd6b-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fd6b-104">Parameters</span></span>  
 <span data-ttu-id="5fd6b-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="5fd6b-105">cref = " `member`"</span></span>  
 <span data-ttu-id="5fd6b-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="5fd6b-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5fd6b-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member`</span><span class="sxs-lookup"><span data-stu-id="5fd6b-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="5fd6b-108">debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="5fd6b-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="5fd6b-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="5fd6b-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fd6b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fd6b-110">Remarks</span></span>  
 <span data-ttu-id="5fd6b-111">La etiqueta \<seealso> le permite especificar el texto que quiere que aparezca en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="5fd6b-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="5fd6b-112">Use [\<see>](./see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="5fd6b-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="5fd6b-113">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="5fd6b-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fd6b-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5fd6b-114">Example</span></span>  
 <span data-ttu-id="5fd6b-115">Vea [\<summary>](./summary.md) para obtener un ejemplo del uso de \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="5fd6b-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd6b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fd6b-116">See also</span></span>

- [<span data-ttu-id="5fd6b-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5fd6b-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5fd6b-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="5fd6b-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
