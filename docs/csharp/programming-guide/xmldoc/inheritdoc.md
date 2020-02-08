---
title: '<inheritdoc>: Guía de programación de C#'
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d660cb1739733c4e98ae0b7939476fe74e6cf200
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794838"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="cfd8c-102">\<inheritdoc> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cfd8c-102">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="cfd8c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfd8c-103">Syntax</span></span>  
  
```xml  
<inheritdoc/> 
```  

## <a name="inheritdoc"></a><span data-ttu-id="cfd8c-104">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="cfd8c-104">InheritDoc</span></span>

<span data-ttu-id="cfd8c-105">Herede comentarios XML de clases base, interfaces y métodos similares.</span><span class="sxs-lookup"><span data-stu-id="cfd8c-105">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="cfd8c-106">Esto elimina la acción de copiar y pegar no deseada de comentarios XML duplicados y mantiene los comentarios XML sincronizados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="cfd8c-106">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="cfd8c-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfd8c-107">Remarks</span></span>  
<span data-ttu-id="cfd8c-108">Agregue sus comentarios XML en las clases base o las interfaces y deje que InheritDoc copie los comentarios en las clases en implementación.</span><span class="sxs-lookup"><span data-stu-id="cfd8c-108">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="cfd8c-109">Agregue sus comentarios XML a los métodos sincrónicos y deje que InheritDoc copie los comentarios en las versiones asincrónicas de los mismos métodos.</span><span class="sxs-lookup"><span data-stu-id="cfd8c-109">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="cfd8c-110">Si quiere copiar los comentarios de un miembro en concreto, puede utilizar el atributo `cref` para especificar el miembro.</span><span class="sxs-lookup"><span data-stu-id="cfd8c-110">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="cfd8c-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="cfd8c-111">Examples</span></span>
[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="cfd8c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfd8c-112">See also</span></span>

- [<span data-ttu-id="cfd8c-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cfd8c-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cfd8c-114">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="cfd8c-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
