---
title: Desbordamiento (Error en tiempo de ejecución de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 47e9106b7355db6ae02ee263dbea82d41a69ed5e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816985"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="4d2a7-102">Desbordamiento (Error en tiempo de ejecución de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d2a7-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="4d2a7-103">Se produce un desbordamiento al intentar una asignación que supera los límites del destino de la asignación.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d2a7-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4d2a7-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="4d2a7-105">Asegúrese de que los resultados de tipo de datos, cálculos y las asignaciones de las conversiones no están demasiado grande para representarlo dentro del intervalo de variables permitido para ese tipo de valor y asignación el valor a una variable de un tipo que pueden contener un mayor intervalo de valores , si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="4d2a7-106">Asegúrese de que las asignaciones de propiedades están dentro del intervalo de la propiedad a la que se realizan.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="4d2a7-107">Asegúrese de que números que se usan en los cálculos que se convierten en enteros no tienen resultados más largos que los enteros.</span><span class="sxs-lookup"><span data-stu-id="4d2a7-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2a7-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d2a7-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="4d2a7-109">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="4d2a7-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="4d2a7-110">Tipos de error</span><span class="sxs-lookup"><span data-stu-id="4d2a7-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
