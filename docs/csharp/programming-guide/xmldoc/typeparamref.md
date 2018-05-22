---
title: '&lt;typeparamref&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 36e5a8998018839214da00287a2bf8dc2c5925a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="ef3a0-102">&lt;typeparamref&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ef3a0-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ef3a0-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef3a0-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef3a0-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef3a0-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ef3a0-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="ef3a0-105">The name of the type parameter.</span></span> <span data-ttu-id="ef3a0-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ef3a0-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef3a0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef3a0-107">Remarks</span></span>  
 <span data-ttu-id="ef3a0-108">Para obtener más información sobre los parámetros de tipo en métodos y tipos genéricos, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="ef3a0-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="ef3a0-109">Use esta etiqueta para permitir que los consumidores del archivo de documentación den formato a la palabra de alguna manera distinta, por ejemplo en cursiva.</span><span class="sxs-lookup"><span data-stu-id="ef3a0-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="ef3a0-110">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="ef3a0-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef3a0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef3a0-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ef3a0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef3a0-112">See Also</span></span>  
 [<span data-ttu-id="ef3a0-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ef3a0-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ef3a0-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ef3a0-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
