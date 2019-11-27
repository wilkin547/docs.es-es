---
title: Tipo de datos booleano
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 5d05514207c5d07e81aab897f40f728570f6bd87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347846"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean (Tipo de datos, Visual Basic)

Contiene valores que solo pueden ser `True` o `False`. Las palabras clave `True` y `False` corresponden a los dos Estados de las variables `Boolean`.  
  
## <a name="remarks"></a>Comentarios  

 Utilice el [tipo de datos booleano (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) para contener valores de dos Estados como true/false, yes/no o ON/OFF.  
  
 El valor predeterminado de `Boolean` es `False`.  
  
 `Boolean` valores no se almacenan como números y los valores almacenados no están diseñados para ser equivalentes a números. Nunca debe escribir código que se base en valores numéricos equivalentes para `True` y `False`. Siempre que sea posible, debe restringir el uso de `Boolean` variables a los valores lógicos para los que están diseñadas.  
  
## <a name="type-conversions"></a>Conversiones de tipos  

 Cuando Visual Basic convierte valores de tipos de datos numéricos en `Boolean`, 0 se convierte en `False` y todos los demás valores se `True`. Cuando Visual Basic convierte `Boolean` valores en tipos numéricos, `False` se convierte en 0 y `True` se convierte en-1.  
  
 Al convertir entre `Boolean` valores y tipos de datos numéricos, tenga en cuenta que los métodos de conversión .NET Framework no siempre producen los mismos resultados que las palabras clave de conversión Visual Basic. Esto se debe a que la conversión de Visual Basic conserva el comportamiento compatible con versiones anteriores. Para obtener más información, vea el tema sobre el tipo Boolean no se convierte a un tipo numérico con precisión en los [tipos de datos de solución de problemas](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
- **Números negativos.** `Boolean` no es un tipo numérico y no puede representar un valor negativo. En cualquier caso, no debe utilizar `Boolean` para contener valores numéricos.  
  
- **Caracteres de tipo.** `Boolean` no tiene un carácter de tipo literal o un carácter de tipo de identificador.  
  
- **Tipo de marco.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, `runningVB` es una variable de `Boolean`, que almacena un valor de sí/no simple.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Boolean?displayProperty=nameWithType>
- [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Solución de problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)
