---
title: DirectCast (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 628ce4f06b91d0f514f71dea3aad8ea0fee6dccf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778552"
---
# <a name="directcast-operator-visual-basic"></a>DirectCast (Operador) (Visual Basic)
Introduce una operación de conversión de tipos en función de herencia o implementación.  
  
## <a name="remarks"></a>Comentarios  
 `DirectCast` no utiliza las rutinas de la aplicación auxiliar de tiempo de ejecución para la conversión, por lo que puede proporcionar un poco mayor rendimiento que Visual Basic `CType` al convertir en tipo de datos y `Object`.  
  
 Usa el `DirectCast` palabra clave similar a la forma de usar el [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) y [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) palabra clave. Proporcione una expresión como el primer argumento y un tipo para convertir como segundo argumento. `DirectCast` requiere una relación de herencia o implementación entre los tipos de datos de los dos argumentos. Esto significa que un tipo debe heredar o implementar la otra.  
  
## <a name="errors-and-failures"></a>Errores y errores  
 `DirectCast` genera un error del compilador si detecta que no existe ninguna relación de herencia o implementación. Pero la falta de un error del compilador no garantiza una conversión correcta. Si la conversión deseada es de restricción, se podría producir un error en tiempo de ejecución. Si esto ocurre, el runtime produce una <xref:System.InvalidCastException> error.  
  
## <a name="conversion-keywords"></a>Palabras clave para conversiones  
 Una comparación de las palabras clave de conversión de tipo es como sigue.  
  
|Palabra clave|Tipos de datos|Relación de argumento|Error de tiempo de ejecución|  
|---|---|---|---|  
|[Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Los tipos de datos|Debe definirse de ampliación o conversión de restricción entre dos tipos de datos|Se produce <xref:System.InvalidCastException>|  
|`DirectCast`|Los tipos de datos|Un tipo debe heredar o implementar otro tipo|Se produce <xref:System.InvalidCastException>|  
|[TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md)|Solo los tipos de referencia|Un tipo debe heredar o implementar otro tipo|Devuelve [nada](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra dos usos de `DirectCast`, que se produce un error en tiempo de ejecución y otra que se realiza correctamente.  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 En el ejemplo anterior, tipo de tiempo de ejecución de `q` es `Double`. `CType` se realiza correctamente porque `Double` puede convertirse en `Integer`. Sin embargo, la primera `DirectCast` produce un error en tiempo de ejecución porque el tiempo de ejecución de tipos de `Double` no tiene ninguna relación de herencia con `Integer`, aunque existe una conversión. El segundo `DirectCast` se realiza correctamente porque convierte del tipo <xref:System.Windows.Forms.Form> escriba <xref:System.Windows.Forms.Control>, desde el que <xref:System.Windows.Forms.Form> hereda.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
