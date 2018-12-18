---
title: '&lt;remarks&gt;: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 75324cbe380b577481b5e8e03f486aa3ef0d5996
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243795"
---
# <a name="ltremarksgt-c-programming-guide"></a><span data-ttu-id="5d705-102">&lt;remarks&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5d705-102">&lt;remarks&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5d705-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d705-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d705-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d705-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="5d705-105">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="5d705-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d705-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d705-106">Remarks</span></span>  
 <span data-ttu-id="5d705-107">La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="5d705-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="5d705-108">Esta información se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="5d705-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="5d705-109">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="5d705-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d705-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d705-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="5d705-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d705-111">See Also</span></span>

- [<span data-ttu-id="5d705-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5d705-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="5d705-113">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="5d705-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
