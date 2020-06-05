---
title: Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: 9e36b84252c3d8762308e95323b8e284977df8c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409769"
---
# <a name="constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="f3537-102">Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz</span><span class="sxs-lookup"><span data-stu-id="f3537-102">Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>
<span data-ttu-id="f3537-103">Ha intentado declarar una constante como una clase, una estructura o un tipo de matriz, o como un parámetro de tipo definido por un tipo genérico contenedor.</span><span class="sxs-lookup"><span data-stu-id="f3537-103">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>  
  
 <span data-ttu-id="f3537-104">Las constantes deben ser de un tipo intrínseco ( `Boolean` , `Byte` , `Date` , `Decimal` , `Double` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` o `UShort` ) o un `Enum` tipo basado en uno de los tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="f3537-104">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>  
  
 <span data-ttu-id="f3537-105">**Identificador de error:** BC30424</span><span class="sxs-lookup"><span data-stu-id="f3537-105">**Error ID:** BC30424</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f3537-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f3537-106">To correct this error</span></span>  
  
1. <span data-ttu-id="f3537-107">Declare la constante como un tipo o intrínseco `Enum` .</span><span class="sxs-lookup"><span data-stu-id="f3537-107">Declare the constant as an intrinsic or `Enum` type.</span></span>  
  
2. <span data-ttu-id="f3537-108">Una constante también puede ser un valor especial, como `True` , `False` o `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="f3537-108">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="f3537-109">El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.</span><span class="sxs-lookup"><span data-stu-id="f3537-109">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3537-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3537-110">See also</span></span>

- [<span data-ttu-id="f3537-111">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="f3537-111">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="f3537-112">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f3537-112">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="f3537-113">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="f3537-113">Data Types</span></span>](../data-types/index.md)
