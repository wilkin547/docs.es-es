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
# <a name="overflow-visual-basic-run-time-error"></a>Desbordamiento (Error en tiempo de ejecución de Visual Basic)

Se produce un desbordamiento al intentar una asignación que supera los límites del destino de la asignación.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que los resultados de las asignaciones, los cálculos y las conversiones de tipos de datos no son demasiado grandes para representarse dentro del intervalo de variables permitido para ese tipo de valor y asignar el valor a una variable de un tipo que puede contener un intervalo mayor de valores, si es necesario.  
  
2. Asegúrese de que las asignaciones a propiedades se ajustan al intervalo de la propiedad en la que se realizan.  
  
3. Asegúrese de que los números que se usan en los cálculos convertidos en enteros no tienen resultados mayores que los enteros.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Tipo de datos](../data-types/index.md)
- [Tipos de errores](../../programming-guide/language-features/error-types.md)
