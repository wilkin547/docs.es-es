---
description: 'Más información acerca de: tipo de datos único (Visual Basic)'
title: Tipo de datos Single
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: f30e21d3b2d2960a040609a9422ec71cc029f5be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792133"
---
# <a name="single-data-type-visual-basic"></a>Single (Tipo de datos, Visual Basic)

Contiene números de punto flotante de precisión sencilla (4 bytes) de IEEE 32 bits con signo que van en el valor de-3.4028235 E + 38 a-401298e E-45 para los valores negativos y desde 401298e E-45 hasta 3.4028235 E + 38 para los valores positivos. Los números de precisión sencilla almacenan una aproximación de un número real.  
  
## <a name="remarks"></a>Observaciones  

 Utilice el `Single` tipo de datos para contener valores de punto flotante que no requieran el ancho completo de los datos de `Double` . En algunos casos, es posible que el Common Language Runtime pueda empaquetar las `Single` variables en estrecha colaboración y ahorrar consumo de memoria.  
  
 El valor predeterminado de `Single` es 0.  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
- **Precisión.** Al trabajar con números de punto flotante, tenga en cuenta que no siempre tienen una representación precisa en la memoria. Esto podría dar lugar a resultados inesperados de ciertas operaciones, como la comparación de valores y el `Mod` operador. Para obtener más información, vea [solución de problemas de tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
- **Ampliación.** El `Single` tipo de datos se amplía a `Double` . Esto significa que puede convertir `Single` en `Double` sin que se produzca un <xref:System.OverflowException?displayProperty=nameWithType> error.  
  
- **Ceros a la derecha.** Los tipos de datos de punto flotante no tienen ninguna representación interna de 0 caracteres finales. Por ejemplo, no distinguen entre 4,2000 y 4,2. Por lo tanto, los caracteres 0 finales no aparecen al mostrar o imprimir valores de punto flotante.  
  
- **Caracteres de tipo.** Al agregar el carácter de tipo literal `F` a un literal, el tipo de datos se convierte forzosamente en el tipo de datos `Single`. Si se agrega el carácter de tipo identificador `!` a cualquier identificador, se convierte forzosamente al tipo `Single`.  
  
- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Single?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Single?displayProperty=nameWithType>
- [Tipo de datos](index.md)
- [Tipo de datos Decimal](decimal-data-type.md)
- [Tipo de datos Double](double-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Solución de problemas de los tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
