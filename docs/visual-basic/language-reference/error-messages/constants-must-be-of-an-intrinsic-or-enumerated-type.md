---
description: 'Más información sobre: BC30424: las constantes deben ser de tipo intrínseco o enumerado, no una clase, una estructura, un parámetro de tipo o un tipo de matriz'
title: Las constantes deben ser de tipo intrínseco o enumerado; no pueden ser de tipo clase, estructura, parámetro de tipo ni matriz
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: e9765d78ff671d6b99f47242509b1c3b4560c029
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796735"
---
# <a name="bc30424-constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a><span data-ttu-id="1def9-103">BC30424: las constantes deben ser de un tipo intrínseco o enumerado, no una clase, una estructura, un parámetro de tipo o un tipo de matriz</span><span class="sxs-lookup"><span data-stu-id="1def9-103">BC30424: Constants must be of an intrinsic or enumerated type, not a class, structure, type parameter, or array type</span></span>

<span data-ttu-id="1def9-104">Ha intentado declarar una constante como una clase, una estructura o un tipo de matriz, o como un parámetro de tipo definido por un tipo genérico contenedor.</span><span class="sxs-lookup"><span data-stu-id="1def9-104">You have attempted to declare a constant as a class, structure, or array type, or as a type parameter defined by a containing generic type.</span></span>

 <span data-ttu-id="1def9-105">Las constantes deben ser de un tipo intrínseco ( `Boolean` , `Byte` , `Date` , `Decimal` , `Double` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` o `UShort` ) o un `Enum` tipo basado en uno de los tipos enteros.</span><span class="sxs-lookup"><span data-stu-id="1def9-105">Constants must be of an intrinsic type (`Boolean`, `Byte`, `Date`, `Decimal`, `Double`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, or `UShort`), or an `Enum` type based on one of the integral types.</span></span>

 <span data-ttu-id="1def9-106">**Identificador de error:** BC30424</span><span class="sxs-lookup"><span data-stu-id="1def9-106">**Error ID:** BC30424</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1def9-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1def9-107">To correct this error</span></span>

1. <span data-ttu-id="1def9-108">Declare la constante como un tipo o intrínseco `Enum` .</span><span class="sxs-lookup"><span data-stu-id="1def9-108">Declare the constant as an intrinsic or `Enum` type.</span></span>

2. <span data-ttu-id="1def9-109">Una constante también puede ser un valor especial, como `True` , `False` o `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="1def9-109">A constant can also be a special value such as `True`, `False`, or `Nothing`.</span></span> <span data-ttu-id="1def9-110">El compilador considera que estos valores predefinidos son del tipo intrínseco adecuado.</span><span class="sxs-lookup"><span data-stu-id="1def9-110">The compiler considers these predefined values to be of the appropriate intrinsic type.</span></span>

## <a name="see-also"></a><span data-ttu-id="1def9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1def9-111">See also</span></span>

- [<span data-ttu-id="1def9-112">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1def9-112">Constants and Enumerations</span></span>](../constants-and-enumerations.md)
- [<span data-ttu-id="1def9-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1def9-113">Data Types</span></span>](../../programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="1def9-114">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="1def9-114">Data Types</span></span>](../data-types/index.md)
