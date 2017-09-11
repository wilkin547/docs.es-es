---
title: "&lt;typeparamref&gt; (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparamref
dev_langs:
- CSharp
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
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
ms.openlocfilehash: ce2aba7a14047066decf85675233a48a08bfd605
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="ae69e-102">&lt;typeparamref&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ae69e-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ae69e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae69e-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae69e-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae69e-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ae69e-105">Nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="ae69e-105">The name of the type parameter.</span></span> <span data-ttu-id="ae69e-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ae69e-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae69e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae69e-107">Remarks</span></span>  
 <span data-ttu-id="ae69e-108">Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="ae69e-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="ae69e-109">Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.</span><span class="sxs-lookup"><span data-stu-id="ae69e-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="ae69e-110">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="ae69e-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae69e-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae69e-111">Example</span></span>  
 <span data-ttu-id="ae69e-112">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ae69e-112">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae69e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae69e-113">See Also</span></span>  
 <span data-ttu-id="ae69e-114">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae69e-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ae69e-115">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ae69e-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

