---
title: Desbordamiento (Error en tiempo de ejecución de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 5606ae8188c12142800adef46819791b732ff73c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387275"
---
# <a name="overflow-visual-basic-run-time-error"></a>Desbordamiento (Error en tiempo de ejecución de Visual Basic)
Se produce un desbordamiento al intentar una asignación que supera los límites del destino de la asignación.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que los resultados de las asignaciones, los cálculos y las conversiones de tipos de datos no son demasiado grandes para representarse dentro del intervalo de variables permitido para ese tipo de valor y asignar el valor a una variable de un tipo que puede contener un intervalo mayor de valores, si es necesario.  
  
2. Asegúrese de que las asignaciones a propiedades se ajustan al intervalo de la propiedad en la que se realizan.  
  
3. Asegúrese de que los números que se usan en los cálculos convertidos en enteros no tienen resultados mayores que los enteros.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Tipos de datos](../data-types/index.md)
- [Tipos de error](../../programming-guide/language-features/error-types.md)
