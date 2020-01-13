---
title: '<typeparamref>: Guía de programación de C#'
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 3e96d55d7cf60b2a9085cf065ef3b8193b173c5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711680"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="db873-102">\<typeparamref> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="db873-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="db873-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db873-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="db873-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db873-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="db873-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="db873-105">The name of the type parameter.</span></span> <span data-ttu-id="db873-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="db873-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db873-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db873-107">Remarks</span></span>  
 <span data-ttu-id="db873-108">Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="db873-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="db873-109">Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.</span><span class="sxs-lookup"><span data-stu-id="db873-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="db873-110">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="db873-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db873-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db873-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="db873-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="db873-112">See also</span></span>

- [<span data-ttu-id="db873-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="db873-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="db873-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="db873-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
