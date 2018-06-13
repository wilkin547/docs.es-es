---
title: '&lt;exception&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: eca61416077896c9fa7d5828bbab79b399ad69d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332665"
---
# <a name="ltexceptiongt-c-programming-guide"></a><span data-ttu-id="ea855-102">&lt;exception&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ea855-102">&lt;exception&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ea855-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea855-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea855-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea855-104">Parameters</span></span>  
 <span data-ttu-id="ea855-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="ea855-105">cref = " `member`"</span></span>  
 <span data-ttu-id="ea855-106">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="ea855-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="ea855-107">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="ea855-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="ea855-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ea855-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="ea855-109">Para más información sobre cómo crear una referencia cref a un tipo genérico, vea [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span><span class="sxs-lookup"><span data-stu-id="ea855-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="ea855-110">Descripción de la excepción.</span><span class="sxs-lookup"><span data-stu-id="ea855-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea855-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea855-111">Remarks</span></span>  
 <span data-ttu-id="ea855-112">La etiqueta \<exception> le permite especificar qué excepciones se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="ea855-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="ea855-113">Esta etiqueta se puede aplicar a definiciones de métodos, propiedades, eventos e indizadores.</span><span class="sxs-lookup"><span data-stu-id="ea855-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="ea855-114">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="ea855-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="ea855-115">Para más información sobre el control de excepciones, vea [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea855-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea855-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea855-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ea855-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea855-117">See Also</span></span>  
 [<span data-ttu-id="ea855-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ea855-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ea855-119">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ea855-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
