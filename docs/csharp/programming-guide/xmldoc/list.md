---
title: "&lt;list&gt; (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- list
- <list>
dev_langs:
- CSharp
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b9d3dfa60530734a142295c8a8f2c32c4ecd9a47
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="bd1dc-102">&lt;list&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="bd1dc-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="bd1dc-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd1dc-103">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="bd1dc-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd1dc-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="bd1dc-105">Término que se define en `description`.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="bd1dc-106">Elemento de una lista numerada o con viñetas, o definición de un `term`.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd1dc-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd1dc-107">Remarks</span></span>  
 <span data-ttu-id="bd1dc-108">El bloque \<listheader> se usa para definir la fila de encabezado de una tabla o de una lista de definiciones.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="bd1dc-109">Cuando se define una tabla, solo es necesario suministrar una entrada para un término en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="bd1dc-110">Cada elemento de la lista se especifica con un bloque \<item>.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="bd1dc-111">Cuando se crea una lista de definiciones, se deberán especificar tanto `term` como `description`.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="bd1dc-112">En cambio, para una tabla, lista con viñetas o lista numerada, solo es necesario suministrar una entrada para `description`.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="bd1dc-113">Una lista o una tabla pueden tener tantos bloques \<item> como sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="bd1dc-114">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="bd1dc-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd1dc-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd1dc-115">Example</span></span>  
 <span data-ttu-id="bd1dc-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bd1dc-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1dc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd1dc-117">See Also</span></span>  
 <span data-ttu-id="bd1dc-118">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bd1dc-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="bd1dc-119">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="bd1dc-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

