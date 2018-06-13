---
title: Desbordamiento (Error en tiempo de ejecución de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 9db79071c4895d49680352bde2d0824a3756d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594180"
---
# <a name="overflow-visual-basic-run-time-error"></a>Desbordamiento (Error en tiempo de ejecución de Visual Basic)
Se produce un desbordamiento cuando intenta una asignación que supera los límites del destino de la asignación.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que los resultados de tipo de datos, cálculos y asignaciones de conversiones no son demasiado grande para representarlo dentro del intervalo de variables permitido para ese tipo de valor y asigne el valor a una variable de un tipo que pueden contener un mayor intervalo de valores , si es necesario.  
  
2.  Asegúrese de que las asignaciones de propiedades ajustan al intervalo de la propiedad a la que se realizan.  
  
3.  Asegúrese de que números que se usan en los cálculos que se convierten en enteros no tienen resultados más largos que los enteros.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)
