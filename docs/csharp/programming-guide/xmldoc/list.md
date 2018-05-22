---
title: '&lt;list&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 768490424403f1235873a681ffba3367e3f128b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="eedf0-102">&lt;list&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="eedf0-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="eedf0-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eedf0-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eedf0-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eedf0-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="eedf0-105">Término que se define en `description`.</span><span class="sxs-lookup"><span data-stu-id="eedf0-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="eedf0-106">Elemento de una lista numerada o con viñetas, o definición de un `term`.</span><span class="sxs-lookup"><span data-stu-id="eedf0-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eedf0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eedf0-107">Remarks</span></span>  
 <span data-ttu-id="eedf0-108">El bloque \<listheader> se usa para definir la fila de encabezado de una tabla o de una lista de definiciones.</span><span class="sxs-lookup"><span data-stu-id="eedf0-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="eedf0-109">Cuando se define una tabla, solo es necesario suministrar una entrada para un término en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="eedf0-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="eedf0-110">Cada elemento de la lista se especifica con un bloque \<item>.</span><span class="sxs-lookup"><span data-stu-id="eedf0-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="eedf0-111">Cuando se crea una lista de definiciones, se deberán especificar tanto `term` como `description`.</span><span class="sxs-lookup"><span data-stu-id="eedf0-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="eedf0-112">En cambio, para una tabla, lista con viñetas o lista numerada, solo es necesario suministrar una entrada para `description`.</span><span class="sxs-lookup"><span data-stu-id="eedf0-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="eedf0-113">Una lista o una tabla pueden tener tantos bloques \<item> como sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="eedf0-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="eedf0-114">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="eedf0-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eedf0-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eedf0-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="eedf0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="eedf0-116">See Also</span></span>  
 [<span data-ttu-id="eedf0-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="eedf0-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="eedf0-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="eedf0-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
