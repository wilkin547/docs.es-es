---
description: 'Más información acerca de: <inheritdoc> (Guía de programación de C#)'
title: '<inheritdoc>: Guía de programación de C#'
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 960bdfbcec1e3f6a89675273f63b6d398e44947e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719401"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="68e5f-103">\<inheritdoc> (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="68e5f-103">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="68e5f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68e5f-104">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="68e5f-105">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="68e5f-105">InheritDoc</span></span>

<span data-ttu-id="68e5f-106">Herede comentarios XML de clases base, interfaces y métodos similares.</span><span class="sxs-lookup"><span data-stu-id="68e5f-106">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="68e5f-107">Esto elimina la acción de copiar y pegar no deseada de comentarios XML duplicados y mantiene los comentarios XML sincronizados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="68e5f-107">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="68e5f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68e5f-108">Remarks</span></span>  

<span data-ttu-id="68e5f-109">Agregue sus comentarios XML en las clases base o las interfaces y deje que InheritDoc copie los comentarios en las clases en implementación.</span><span class="sxs-lookup"><span data-stu-id="68e5f-109">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="68e5f-110">Agregue sus comentarios XML a los métodos sincrónicos y deje que InheritDoc copie los comentarios en las versiones asincrónicas de los mismos métodos.</span><span class="sxs-lookup"><span data-stu-id="68e5f-110">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="68e5f-111">Si quiere copiar los comentarios de un miembro en concreto, puede utilizar el atributo `cref` para especificar el miembro.</span><span class="sxs-lookup"><span data-stu-id="68e5f-111">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="68e5f-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="68e5f-112">Examples</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="68e5f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="68e5f-113">See also</span></span>

- [<span data-ttu-id="68e5f-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="68e5f-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="68e5f-115">Etiquetas recomendadas para los comentarios de documentación</span><span class="sxs-lookup"><span data-stu-id="68e5f-115">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
