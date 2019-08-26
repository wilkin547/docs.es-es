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
ms.openlocfilehash: 822ca8feafe48402f8217c10ef37fcdb1576c27a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587750"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="ac90e-102">\<remarks> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ac90e-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ac90e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac90e-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac90e-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac90e-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="ac90e-105">Descripción del miembro.</span><span class="sxs-lookup"><span data-stu-id="ac90e-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac90e-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac90e-106">Remarks</span></span>  
 <span data-ttu-id="ac90e-107">La etiqueta \<remarks> se usa para agregar información sobre un tipo y complementa la información especificada con [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="ac90e-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="ac90e-108">Esta información se muestra en la ventana Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="ac90e-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="ac90e-109">Compile con el parámetro [/doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="ac90e-109">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac90e-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ac90e-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="ac90e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac90e-111">See also</span></span>

- [<span data-ttu-id="ac90e-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ac90e-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ac90e-113">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ac90e-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
