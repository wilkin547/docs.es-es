---
title: "&lt;param&gt; (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1a5325b91130623442c9cf5453e52418bb44cc34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="ddc22-102">&lt;param&gt; (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ddc22-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="ddc22-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddc22-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddc22-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ddc22-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ddc22-105">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="ddc22-105">The name of a method parameter.</span></span> <span data-ttu-id="ddc22-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="ddc22-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ddc22-107">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ddc22-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddc22-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ddc22-108">Remarks</span></span>  
 <span data-ttu-id="ddc22-109">La etiqueta \<param> debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="ddc22-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="ddc22-110">Para documentar varios parámetros, use varias etiquetas \<param>.</span><span class="sxs-lookup"><span data-stu-id="ddc22-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="ddc22-111">El texto de la etiqueta \<param> se mostrará en IntelliSense, el Examinador de objetos y en el informe web de comentario de código.</span><span class="sxs-lookup"><span data-stu-id="ddc22-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="ddc22-112">Compile con el parámetro [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="ddc22-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddc22-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddc22-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ddc22-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddc22-114">See Also</span></span>  
 [<span data-ttu-id="ddc22-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ddc22-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ddc22-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="ddc22-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
