---
title: DirectCast (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 8ea29b80cf27bbb2c21a8cebbfaa0a294e05f11d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331310"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast (Operador) (Visual Basic)
Introduce una operación de conversión de tipos basada en la herencia o la implementación.  
  
## <a name="remarks"></a>Comentarios  
 `DirectCast` no utiliza las rutinas auxiliares de Visual Basic en tiempo de ejecución para la conversión, por lo que puede proporcionar un rendimiento algo mejor que `CType` al convertir a y desde el tipo de datos `Object`.  
  
 La palabra clave `DirectCast` se utiliza de manera similar a la forma en que se usa la [función ctype](../../../visual-basic/language-reference/functions/ctype-function.md) y la palabra clave del [operador TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) . Proporcione una expresión como primer argumento y un tipo al que convertirlo como segundo argumento. `DirectCast` requiere una relación de herencia o implementación entre los tipos de datos de los dos argumentos. Esto significa que un tipo debe heredar de o implementar el otro.  
  
## <a name="errors-and-failures"></a>Errores y errores  
 `DirectCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o de implementación. Pero la falta de un error del compilador no garantiza una conversión correcta. Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución. Si esto sucede, el tiempo de ejecución produce un error de <xref:System.InvalidCastException>.  
  
## <a name="conversion-keywords"></a>Palabras clave para conversiones  
 A continuación se muestra una comparación de las palabras clave de conversión de tipos.  
  
|Palabra clave|Tipos de datos|Relación entre argumentos|Error en tiempo de ejecución|  
|---|---|---|---|  
|[Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Cualquier tipo de datos|La conversión de ampliación o de restricción debe definirse entre los dos tipos de datos|Produce <xref:System.InvalidCastException>|  
|`DirectCast`|Cualquier tipo de datos|Un tipo debe heredar de o implementar el otro tipo|Produce <xref:System.InvalidCastException>|  
|[TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md)|Solo tipos de referencia|Un tipo debe heredar de o implementar el otro tipo|No devuelve [nada](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestran dos usos de `DirectCast`, uno que produce un error en tiempo de ejecución y otro que se ejecuta correctamente.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 En el ejemplo anterior, el tipo en tiempo de ejecución de `q` es `Double`. `CType` se realiza correctamente porque `Double` se puede convertir en `Integer`. Sin embargo, se produce un error en el primer `DirectCast` en tiempo de ejecución porque el tipo de `Double` en tiempo de ejecución no tiene ninguna relación de herencia con `Integer`, aunque exista una conversión. La segunda `DirectCast` se realiza correctamente porque convierte de tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, del que <xref:System.Windows.Forms.Form> hereda.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
