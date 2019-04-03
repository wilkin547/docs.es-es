---
title: Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: f82a548c820aec7d2ae13c30a67d778fc167a8b6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813116"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="5efa0-102">Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz</span><span class="sxs-lookup"><span data-stu-id="5efa0-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="5efa0-103">Ha intentado declarar una constante como una clase, estructura o tipo de matriz, o como un parámetro de tipo definido por un tipo genérico contenedor.</span><span class="sxs-lookup"><span data-stu-id="5efa0-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="5efa0-104">Las constantes deben ser de un tipo intrínseco (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, o `UShort`), o un `Enum` tipo basado en uno de los tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="5efa0-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="5efa0-105">**Identificador de error:** BC30424</span><span class="sxs-lookup"><span data-stu-id="5efa0-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5efa0-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5efa0-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="5efa0-107">Declare la constante como intrínseco o `Enum` tipo.</span><span class="sxs-lookup"><span data-stu-id="5efa0-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2.  <span data-ttu-id="5efa0-108">Una constante puede ser también un valor especial como `True`, `False`, o `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5efa0-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="5efa0-109">El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.</span><span class="sxs-lookup"><span data-stu-id="5efa0-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5efa0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5efa0-110">See also</span></span>

- [<span data-ttu-id="5efa0-111">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="5efa0-111">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="5efa0-112">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5efa0-112">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="5efa0-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5efa0-113">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
