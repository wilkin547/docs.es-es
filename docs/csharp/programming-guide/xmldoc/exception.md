---
title: '<exception>: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 4e4204996c006ce6e943c9a09661001b0e0c2a14
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523473"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="10573-102">\<exception> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="10573-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="10573-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10573-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="10573-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10573-104">Parameters</span></span>  
 <span data-ttu-id="10573-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="10573-105">cref = " `member`"</span></span>  
 <span data-ttu-id="10573-106">Una referencia a una excepción que está disponible desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="10573-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="10573-107">El compilador comprueba si la excepción dada existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="10573-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="10573-108">`member` debe aparecer entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="10573-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="10573-109">Para más información sobre cómo dar formato a `member` para hacer referencia a un tipo genérico, consulte [Procesar el archivo XML](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="10573-109">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>
  
 `description`  
 <span data-ttu-id="10573-110">Descripción de la excepción.</span><span class="sxs-lookup"><span data-stu-id="10573-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10573-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10573-111">Remarks</span></span>  
 <span data-ttu-id="10573-112">La etiqueta \<exception> le permite especificar qué excepciones se pueden producir.</span><span class="sxs-lookup"><span data-stu-id="10573-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="10573-113">Esta etiqueta se puede aplicar a definiciones de métodos, propiedades, eventos e indizadores.</span><span class="sxs-lookup"><span data-stu-id="10573-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="10573-114">Compile con [-doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="10573-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="10573-115">Para más información sobre el control de excepciones, vea [Excepciones y control de excepciones](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="10573-115">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10573-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10573-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="10573-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="10573-117">See also</span></span>

- [<span data-ttu-id="10573-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="10573-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="10573-119">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="10573-119">Recommended Tags for Documentation Comments</span></span>](recommended-tags-for-documentation-comments.md)
