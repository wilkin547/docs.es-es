---
description: 'Más información acerca de: tipo de datos booleano (Visual Basic)'
title: Tipo de datos Boolean
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
ms.openlocfilehash: cdda6bc0571eb0a2a9ee6a079ffd276bfc89a9b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731414"
---
# <a name="boolean-data-type-visual-basic"></a>Boolean (Tipo de datos, Visual Basic)

Contiene valores que solo pueden ser `True` o `False` . Las palabras clave `True` y `False` se corresponden con los dos Estados de `Boolean` las variables.  
  
## <a name="remarks"></a>Observaciones  

 Utilice el [tipo de datos booleano (Visual Basic)](boolean-data-type.md) para contener valores de dos Estados como true/false, yes/no o ON/OFF.  
  
 El valor predeterminado de `Boolean` es `False`.  
  
 `Boolean` los valores no se almacenan como números y los valores almacenados no están diseñados para ser equivalentes a números. Nunca debe escribir código que se base en valores numéricos equivalentes para `True` y `False` . Siempre que sea posible, debe restringir `Boolean` el uso de variables a los valores lógicos para los que están diseñadas.  
  
## <a name="type-conversions"></a>Conversiones de tipos  

 Cuando Visual Basic convierte valores de tipos de datos numéricos en `Boolean` , 0 se convierte en `False` y todos los demás valores se convierten en `True` . Cuando Visual Basic convierte `Boolean` valores en tipos numéricos, `False` se convierte en 0 y `True` se convierte en-1.  
  
 Al convertir entre `Boolean` valores y tipos de datos numéricos, tenga en cuenta que los métodos de conversión .NET Framework no siempre generan los mismos resultados que las palabras clave de conversión Visual Basic. Esto se debe a que la conversión de Visual Basic conserva el comportamiento compatible con versiones anteriores. Para obtener más información, vea el tema sobre el tipo Boolean no se convierte a un tipo numérico con precisión en los [tipos de datos de solución de problemas](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="programming-tips"></a>Sugerencias de programación  
  
- **Números negativos.** `Boolean` no es un tipo numérico y no puede representar un valor negativo. En cualquier caso, no debe usar `Boolean` para contener valores numéricos.  
  
- **Caracteres de tipo.** `Boolean` no tiene un carácter de tipo literal o un carácter de tipo de identificador.  
  
- **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Boolean?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, `runningVB` es una `Boolean` variable, que almacena un valor sí/no sencillo.  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Boolean?displayProperty=nameWithType>
- [Tipo de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Solución de problemas de los tipos de datos](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [CType Function](../functions/ctype-function.md)
