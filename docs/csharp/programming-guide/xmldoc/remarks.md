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
ms.openlocfilehash: faeb1b07d4778f56ae854d5ece93588cbe5848f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536053"
---
# <a name="ltremarksgt-c-programming-guide"></a><span data-ttu-id="100db-102">&lt;remarks&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="100db-102">&lt;remarks&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="100db-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="100db-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="100db-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="100db-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="100db-105">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="100db-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="100db-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="100db-106">Remarks</span></span>  
 <span data-ttu-id="100db-107">La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="100db-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="100db-108">Esta información se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="100db-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="100db-109">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="100db-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="100db-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="100db-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="100db-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="100db-111">See also</span></span>

- [<span data-ttu-id="100db-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="100db-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="100db-113">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="100db-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
