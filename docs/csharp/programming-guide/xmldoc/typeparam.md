---
title: "&lt;typeparam&gt; (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e1b8800e39b1ee5eeac8c5d3e4390ed3226b33a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="97fb9-102">&lt;typeparam&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="97fb9-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="97fb9-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97fb9-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97fb9-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97fb9-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="97fb9-105">El nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="97fb9-105">The name of the type parameter.</span></span> <span data-ttu-id="97fb9-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="97fb9-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="97fb9-107">Una descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="97fb9-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97fb9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97fb9-108">Remarks</span></span>  
 <span data-ttu-id="97fb9-109">La etiqueta `<typeparam>` debe usarse en el comentario de una declaración de método o tipo genérico para describir un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="97fb9-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="97fb9-110">Agregue una etiqueta para cada parámetro de tipo del tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="97fb9-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="97fb9-111">Para más información, vea [Genéricos](../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="97fb9-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="97fb9-112">El texto de la etiqueta `<typeparam>` se mostrará en IntelliSense, el informe web de comentario de código de la [Ventana Examinador de objetos](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).</span><span class="sxs-lookup"><span data-stu-id="97fb9-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="97fb9-113">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="97fb9-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97fb9-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97fb9-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="97fb9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="97fb9-115">See Also</span></span>  
 [<span data-ttu-id="97fb9-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="97fb9-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="97fb9-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="97fb9-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="97fb9-118">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="97fb9-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
