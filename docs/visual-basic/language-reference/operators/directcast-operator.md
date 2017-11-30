---
title: DirectCast (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords: DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a>DirectCast (Operador) (Visual Basic)
Introduce una operación de conversión de tipos en función de herencia o implementación.  
  
## <a name="remarks"></a>Comentarios  
 `DirectCast`no se utiliza Visual Basic rutinas auxiliares de tiempo de ejecución para la conversión, por lo que puede proporcionar un poco retrasada con un rendimiento mayor que `CType` al convertir a y desde el tipo de datos `Object`.  
  
 Usa el `DirectCast` palabra clave similar a la forma de usar el [CType (función)](../../../visual-basic/language-reference/functions/ctype-function.md) y [TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md) (palabra clave). Proporcione una expresión como el primer argumento y un tipo para convertir como segundo argumento. `DirectCast`requiere una relación de herencia o implementación entre los tipos de datos de los dos argumentos. Esto significa que un tipo debe heredar de o implementar la otra.  
  
## <a name="errors-and-failures"></a>Errores y errores  
 `DirectCast`genera un error del compilador si detecta que no existe ninguna relación de herencia o implementación. Pero la falta de un error del compilador no garantiza una conversión correcta. Si la conversión deseada es de restricción, podría producirse un error en tiempo de ejecución. Si esto ocurre, el runtime produce una <xref:System.InvalidCastException> error.  
  
## <a name="conversion-keywords"></a>Palabras clave para conversiones  
 Una comparación de las palabras clave de conversión de tipo es como sigue.  
  
|Palabra clave|Tipos de datos|Relación de argumentos|Error de tiempo de ejecución|  
|---|---|---|---|  
|[Función CType](../../../visual-basic/language-reference/functions/ctype-function.md)|Los tipos de datos|De ampliación o conversión de restricción se debe definir entre los dos tipos de datos|Produce<xref:System.InvalidCastException>|  
|`DirectCast`|Los tipos de datos|Un tipo debe heredar de tipo ni lo implementa otro|Produce<xref:System.InvalidCastException>|  
|[TryCast (operador)](../../../visual-basic/language-reference/operators/trycast-operator.md)|Solo los tipos de referencia|Un tipo debe heredar de tipo ni lo implementa otro|Devuelve [nada](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra dos usos de `DirectCast`, uno que se produce un error en tiempo de ejecución y uno que sea correcto.  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 En el ejemplo anterior, escriba el tiempo de ejecución de `q` es `Double`. `CType`se realiza correctamente porque `Double` puede convertirse a `Integer`. Sin embargo, la primera `DirectCast` se produce un error en tiempo de ejecución porque el tiempo de ejecución de tipos de `Double` no tiene ninguna relación de herencia con `Integer`, aunque existe una conversión. El segundo `DirectCast` se realiza correctamente porque convierte del tipo <xref:System.Windows.Forms.Form> al tipo <xref:System.Windows.Forms.Control>, desde el que <xref:System.Windows.Forms.Form> hereda.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
