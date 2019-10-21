---
title: '<typeparamref>: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 451f101a3002a9590bdf616b01c6c8bab27efd69
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523314"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="9fa9f-102">\<typeparamref> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9fa9f-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="9fa9f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fa9f-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fa9f-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fa9f-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9fa9f-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="9fa9f-105">The name of the type parameter.</span></span> <span data-ttu-id="9fa9f-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="9fa9f-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fa9f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9fa9f-107">Remarks</span></span>  
 <span data-ttu-id="9fa9f-108">Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="9fa9f-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="9fa9f-109">Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.</span><span class="sxs-lookup"><span data-stu-id="9fa9f-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="9fa9f-110">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="9fa9f-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fa9f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fa9f-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="9fa9f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fa9f-112">See also</span></span>

- [<span data-ttu-id="9fa9f-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9fa9f-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9fa9f-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="9fa9f-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
