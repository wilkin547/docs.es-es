---
title: <param> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 3f1099da6a43ed7f48389a16e3be6a3b6b98a148
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271582"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="f53da-102">\<param> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f53da-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="f53da-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f53da-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f53da-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f53da-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f53da-105">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="f53da-105">The name of a method parameter.</span></span> <span data-ttu-id="f53da-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="f53da-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f53da-107">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="f53da-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f53da-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f53da-108">Remarks</span></span>  
 <span data-ttu-id="f53da-109">La etiqueta \<param> debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="f53da-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="f53da-110">Para documentar varios parámetros, use varias etiquetas \<param>.</span><span class="sxs-lookup"><span data-stu-id="f53da-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="f53da-111">El texto de la etiqueta \<param> se mostrará en IntelliSense, el Examinador de objetos y en el informe web de comentario de código.</span><span class="sxs-lookup"><span data-stu-id="f53da-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="f53da-112">Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="f53da-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f53da-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f53da-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f53da-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53da-114">See also</span></span>

- [<span data-ttu-id="f53da-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f53da-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f53da-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="f53da-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
