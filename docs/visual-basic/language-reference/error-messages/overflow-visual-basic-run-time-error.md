---
description: 'Más información acerca de: desbordamiento (Visual Basic Run-Time error)'
title: Desbordamiento (Error en tiempo de ejecución de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: a01a8916e09f9278dbdf6d594c5ef84d63b04c51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795461"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="7dee6-103">Desbordamiento (Error en tiempo de ejecución de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dee6-103">Overflow (Visual Basic Run-Time Error)</span></span>

<span data-ttu-id="7dee6-104">Se produce un desbordamiento al intentar una asignación que supera los límites del destino de la asignación.</span><span class="sxs-lookup"><span data-stu-id="7dee6-104">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7dee6-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7dee6-105">To correct this error</span></span>  
  
1. <span data-ttu-id="7dee6-106">Asegúrese de que los resultados de las asignaciones, los cálculos y las conversiones de tipos de datos no son demasiado grandes para representarse dentro del intervalo de variables permitido para ese tipo de valor y asignar el valor a una variable de un tipo que puede contener un intervalo mayor de valores, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="7dee6-106">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="7dee6-107">Asegúrese de que las asignaciones a propiedades se ajustan al intervalo de la propiedad en la que se realizan.</span><span class="sxs-lookup"><span data-stu-id="7dee6-107">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="7dee6-108">Asegúrese de que los números que se usan en los cálculos convertidos en enteros no tienen resultados mayores que los enteros.</span><span class="sxs-lookup"><span data-stu-id="7dee6-108">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dee6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dee6-109">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="7dee6-110">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7dee6-110">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="7dee6-111">Tipos de errores</span><span class="sxs-lookup"><span data-stu-id="7dee6-111">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
