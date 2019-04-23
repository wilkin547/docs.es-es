---
title: Desbordamiento (Error en tiempo de ejecución de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 63223a815e1c4ff8d4e0afbb6c732fff90aad465
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345552"
---
# <a name="overflow-visual-basic-run-time-error"></a>Desbordamiento (Error en tiempo de ejecución de Visual Basic)
Se produce un desbordamiento al intentar una asignación que supera los límites del destino de la asignación.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que los resultados de tipo de datos, cálculos y las asignaciones de las conversiones no están demasiado grande para representarlo dentro del intervalo de variables permitido para ese tipo de valor y asignación el valor a una variable de un tipo que pueden contener un mayor intervalo de valores , si es necesario.  
  
2. Asegúrese de que las asignaciones de propiedades están dentro del intervalo de la propiedad a la que se realizan.  
  
3. Asegúrese de que números que se usan en los cálculos que se convierten en enteros no tienen resultados más largos que los enteros.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)
