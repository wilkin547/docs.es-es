---
title: Cadena de patrón no válida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 3fa42632ad6d69642d7b8ec36bf2880bc10a5024
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732484"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="2ad40-102">Cadena de patrón no válida</span><span class="sxs-lookup"><span data-stu-id="2ad40-102">Invalid pattern string</span></span>
<span data-ttu-id="2ad40-103">La cadena de patrón especificada en la operación `Like` de una búsqueda no es válida.</span><span class="sxs-lookup"><span data-stu-id="2ad40-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ad40-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2ad40-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="2ad40-105">Revise los caracteres válidos para las expresiones de lista.</span><span class="sxs-lookup"><span data-stu-id="2ad40-105">Review the valid characters for list expressions.</span></span>  
  
2.  <span data-ttu-id="2ad40-106">En el intervalo de patrones, asegúrese de que el carácter inicial del intervalo es menor que el carácter final del intervalo, como en `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="2ad40-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3.  <span data-ttu-id="2ad40-107">En el intervalo de patrones, asegúrese de que no hay varios guiones uno junto a otro, como en `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="2ad40-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4.  <span data-ttu-id="2ad40-108">Finalice los intervalos de patrones con un corchete de cierre.</span><span class="sxs-lookup"><span data-stu-id="2ad40-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad40-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ad40-109">See also</span></span>
- [<span data-ttu-id="2ad40-110">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="2ad40-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
