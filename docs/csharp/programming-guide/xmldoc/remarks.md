---
title: <remarks> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: b2e91b868c35773033418c796b7c43b08e87a28b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480382"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="32865-102">\<remarks> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="32865-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="32865-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32865-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="32865-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32865-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="32865-105">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="32865-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="32865-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32865-106">Remarks</span></span>  
 <span data-ttu-id="32865-107">La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span><span class="sxs-lookup"><span data-stu-id="32865-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="32865-108">Esta información se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="32865-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="32865-109">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="32865-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32865-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32865-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="32865-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="32865-111">See also</span></span>

- [<span data-ttu-id="32865-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="32865-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="32865-113">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="32865-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
