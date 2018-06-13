---
title: '&lt;typeparam&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 8c7fc1aba05af731d3df80e0b10c2981b5784197
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348783"
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="b168b-102">&lt;typeparam&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b168b-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b168b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b168b-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b168b-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b168b-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b168b-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="b168b-105">The name of the type parameter.</span></span> <span data-ttu-id="b168b-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="b168b-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="b168b-107">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="b168b-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b168b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b168b-108">Remarks</span></span>  
 <span data-ttu-id="b168b-109">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="b168b-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="b168b-110">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="b168b-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="b168b-111">Para más información, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="b168b-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="b168b-112">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).</span><span class="sxs-lookup"><span data-stu-id="b168b-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="b168b-113">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="b168b-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b168b-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b168b-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b168b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b168b-115">See Also</span></span>  
 [<span data-ttu-id="b168b-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b168b-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b168b-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b168b-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b168b-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="b168b-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
