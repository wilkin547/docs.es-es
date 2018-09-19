---
title: Procedimientos genéricos en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
ms.openlocfilehash: 9a88a979a6b46f897e5f04f4481d4a23e245b165
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969777"
---
# <a name="generic-procedures-in-visual-basic"></a>Procedimientos genéricos en Visual Basic
Un *procedimiento genérico*, también denominado una *método genérico*, es un procedimiento definido con al menos un parámetro de tipo. Esto permite al código que realiza la llamada a adaptar a sus requisitos de los tipos de datos cada vez que llama al procedimiento.  
  
 Un procedimiento no es genérico el simple hecho de que se define dentro de una clase genérica o una estructura genérica. Para ser genérico, el procedimiento debe tener al menos un parámetro de tipo, además de los parámetros normales puede tardar. Una clase o estructura genérica puede contener procedimientos genéricos y una clase no genérica, estructura o módulo puede contener procedimientos genéricos.  
  
 Un procedimiento genérico puede usar sus parámetros de tipo en su lista de parámetros normales, su tipo de valor devuelto si tiene uno y en su procedimiento de código.  
  
## <a name="type-inference"></a>Inferencia de tipos  
 Puede llamar a un procedimiento genérico sin proporcionar argumentos de tipo en absoluto. Si se le llama de este modo, el compilador intenta determinar los tipos de datos adecuado para pasar a los argumentos de tipo del procedimiento. Esto se denomina *inferencia de tipo*. El código siguiente muestra una llamada en la que el compilador deduce que debe pasar el tipo `String` al parámetro de tipo `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Si el compilador no puede deducir los argumentos de tipo desde el contexto de la llamada, notifica un error. Una posible causa de este error es un error de coincidencia de rango de matriz. Por ejemplo, supongamos que define un parámetro normal como una matriz de un parámetro de tipo. Si se llama al procedimiento genérico proporcionando una matriz de un rango diferente (número de dimensiones), la falta de coincidencia hace que la inferencia de tipos producir un error. El código siguiente muestra una llamada en la que se pasa una matriz bidimensional a un procedimiento que espera una matriz unidimensional.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 Puede invocar la inferencia de tipo omitiendo todos los argumentos de tipo. Si proporciona un argumento de tipo, debe proporcionar todos ellos.  
  
 Inferencia de tipos solo se admite para procedimientos genéricos. No se puede invocar la inferencia de tipos en clases genéricas, estructuras, interfaces o delegados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se define un tipo genérico `Function` procedimiento para buscar un elemento determinado en una matriz. Define un parámetro de tipo y lo usa para construir los dos parámetros en la lista de parámetros.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a>Comentarios  
 En el ejemplo anterior, se requiere la capacidad de comparar `searchValue` con cada elemento de `searchArray`. Para garantizar esta capacidad, restringe el parámetro de tipo `T` para implementar el <xref:System.IComparable%601> interfaz. El código usa el <xref:System.IComparable%601.CompareTo%2A> método en lugar de la `=` operador, porque no hay ninguna garantía de que un argumento de tipo proporcionado para `T` admite el `=` operador.  
  
 Puede probar la `findElement` procedimiento con el código siguiente.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Anterior llama a `MsgBox` mostrar "0", "1" y "-1", respectivamente.  
  
## <a name="see-also"></a>Vea también  
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [Utilizar una clase genérica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Lista de tipos](../../../../visual-basic/language-reference/statements/type-list.md)  
 [Lista de parámetros](../../../../visual-basic/language-reference/statements/parameter-list.md)
