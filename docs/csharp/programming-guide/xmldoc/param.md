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
ms.openlocfilehash: e2e9bd4478ceaf2f491aba0aa3db8bae7857f28d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587923"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="1baee-102">\<param> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1baee-102">\<param> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="1baee-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1baee-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1baee-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1baee-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="1baee-105">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="1baee-105">The name of a method parameter.</span></span> <span data-ttu-id="1baee-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="1baee-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="1baee-107">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1baee-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1baee-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1baee-108">Remarks</span></span>  
 <span data-ttu-id="1baee-109">La etiqueta \<param> debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="1baee-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="1baee-110">Para documentar varios parámetros, use varias etiquetas \<param>.</span><span class="sxs-lookup"><span data-stu-id="1baee-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="1baee-111">El texto de la etiqueta \<param> se mostrará en IntelliSense, el Examinador de objetos y en el informe web de comentario de código.</span><span class="sxs-lookup"><span data-stu-id="1baee-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="1baee-112">Compile con [/doc](../../language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="1baee-112">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1baee-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1baee-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1baee-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1baee-114">See also</span></span>

- [<span data-ttu-id="1baee-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1baee-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1baee-116">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="1baee-116">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
