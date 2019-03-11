---
title: '<paramref>: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- paramref
- <paramref>
helpviewer_keywords:
- <paramref> C# XML tag
- paramref C# XML tag
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
ms.openlocfilehash: 9612fb61151953e0d3b70a4803aafeb571aec7dd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477949"
---
# <a name="paramref-c-programming-guide"></a><span data-ttu-id="34016-102">\<paramref> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="34016-102">\<paramref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="34016-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34016-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="34016-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="34016-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="34016-105">Nombre del parámetro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="34016-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="34016-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="34016-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34016-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34016-107">Remarks</span></span>  
 <span data-ttu-id="34016-108">La etiqueta \<paramref> ofrece una manera de indicar que una palabra en los comentarios del código (por ejemplo, en un bloque \<summary> o \<comments>) hace referencia a un parámetro.</span><span class="sxs-lookup"><span data-stu-id="34016-108">The \<paramref> tag gives you a way to indicate that a word in the code comments, for example in a \<summary> or \<remarks> block refers to a parameter.</span></span> <span data-ttu-id="34016-109">El archivo XML se puede procesar para dar formato a esta palabra de alguna manera distinta, por ejemplo, con una fuente en negrita o cursiva.</span><span class="sxs-lookup"><span data-stu-id="34016-109">The XML file can be processed to format this word in some distinct way, such as with a bold or italic font.</span></span>  
  
 <span data-ttu-id="34016-110">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="34016-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34016-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34016-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#7)]  
  
## <a name="see-also"></a><span data-ttu-id="34016-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="34016-112">See also</span></span>

- [<span data-ttu-id="34016-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="34016-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="34016-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="34016-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
