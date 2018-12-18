---
title: '&lt;seealso&gt;: Guía de programación de C#'
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
ms.openlocfilehash: eec4a0c2041d7d10b5887950bfec03ec8847c82b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244796"
---
# <a name="ltseealsogt-c-programming-guide"></a><span data-ttu-id="375a1-102">&lt;seealso&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="375a1-102">&lt;seealso&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="375a1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="375a1-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="375a1-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="375a1-104">Parameters</span></span>  
 <span data-ttu-id="375a1-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="375a1-105">cref = " `member`"</span></span>  
 <span data-ttu-id="375a1-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="375a1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="375a1-107">El compilador comprueba si el elemento de código dado existe y pasa `member` al nombre de elemento en el resultado XML.`member`</span><span class="sxs-lookup"><span data-stu-id="375a1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="375a1-108">debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="375a1-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="375a1-109">Para obtener información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="375a1-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="375a1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="375a1-110">Remarks</span></span>  
 <span data-ttu-id="375a1-111">La etiqueta \<seealso> le permite especificar el texto que quiere que aparezca en una sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="375a1-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="375a1-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) para especificar un vínculo desde dentro del texto.</span><span class="sxs-lookup"><span data-stu-id="375a1-112">Use [\<see>](../../../csharp/programming-guide/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="375a1-113">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="375a1-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="375a1-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="375a1-114">Example</span></span>  
 <span data-ttu-id="375a1-115">Vea [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para obtener un ejemplo del uso de \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="375a1-115">See [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="375a1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="375a1-116">See Also</span></span>

- [<span data-ttu-id="375a1-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="375a1-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="375a1-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="375a1-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
