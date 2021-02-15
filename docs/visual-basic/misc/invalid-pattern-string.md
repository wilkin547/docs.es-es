---
description: 'Más información acerca de: cadena de patrón no válida'
title: Cadena de patrón no válida
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 4fbf16dd43ac4ae44e1a99d85caae4a7baf99109
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462066"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="71bd3-103">Cadena de patrón no válida</span><span class="sxs-lookup"><span data-stu-id="71bd3-103">Invalid pattern string</span></span>

<span data-ttu-id="71bd3-104">La cadena de patrón especificada en la operación `Like` de una búsqueda no es válida.</span><span class="sxs-lookup"><span data-stu-id="71bd3-104">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="71bd3-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="71bd3-105">To correct this error</span></span>  
  
1. <span data-ttu-id="71bd3-106">Revise los caracteres válidos para las expresiones de lista.</span><span class="sxs-lookup"><span data-stu-id="71bd3-106">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="71bd3-107">En el intervalo de patrones, asegúrese de que el carácter inicial del intervalo es menor que el carácter final del intervalo, como en `[a-z]`.</span><span class="sxs-lookup"><span data-stu-id="71bd3-107">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="71bd3-108">En el intervalo de patrones, asegúrese de que no hay varios guiones uno junto a otro, como en `[a--z]`.</span><span class="sxs-lookup"><span data-stu-id="71bd3-108">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="71bd3-109">Finalice los intervalos de patrones con un corchete de cierre.</span><span class="sxs-lookup"><span data-stu-id="71bd3-109">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bd3-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71bd3-110">See also</span></span>

- [<span data-ttu-id="71bd3-111">Like (Operador)</span><span class="sxs-lookup"><span data-stu-id="71bd3-111">Like Operator</span></span>](../language-reference/operators/like-operator.md)
