---
title: '&lt;typeparamref&gt;: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: cfee16ad1cdc1e019a4133259c1603f5a0a09ac8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536560"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="9dae4-102">&lt;typeparamref&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9dae4-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="9dae4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dae4-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dae4-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dae4-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="9dae4-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="9dae4-105">The name of the type parameter.</span></span> <span data-ttu-id="9dae4-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="9dae4-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dae4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dae4-107">Remarks</span></span>  
 <span data-ttu-id="9dae4-108">Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dae4-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="9dae4-109">Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.</span><span class="sxs-lookup"><span data-stu-id="9dae4-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="9dae4-110">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="9dae4-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dae4-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dae4-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9dae4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dae4-112">See also</span></span>

- [<span data-ttu-id="9dae4-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9dae4-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9dae4-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="9dae4-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
