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
ms.openlocfilehash: 686087e4520ea5e6e69e5906c628af3ad54749da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649401"
---
# <a name="generic-procedures-in-visual-basic"></a>Procedimientos genéricos en Visual Basic
A *procedimiento genérico*, también denominado una *método genérico*, es un procedimiento definido con al menos un parámetro de tipo. Esto permite que el código de llamada para personalizar los tipos de datos a sus requisitos cada vez que llama al procedimiento.  
  
 Un procedimiento no es genérico el simple hecho de que se define dentro de una clase genérica o una estructura genérica. Para ser genérico, el procedimiento debe tomar al menos un parámetro de tipo, además de los parámetros normales, puede tardar. Una clase o estructura genérica puede contener procedimientos genéricos y una clase no genérica, estructura o módulo puede contener procedimientos genéricos.  
  
 Un procedimiento genérico puede usar sus parámetros de tipo en su lista de parámetros normales, en su tipo de valor devuelto, si existe una y en su procedimiento código.  
  
## <a name="type-inference"></a>Inferencia de tipos  
 Puede llamar a un procedimiento genérico sin proporcionar ningún argumento de tipo en absoluto. Si se le llama de esta forma, el compilador intenta determinar los tipos de datos adecuado para pasar a los argumentos de tipo del procedimiento. Esto se denomina *inferencia de tipo*. El código siguiente muestra una llamada en la que el compilador deduce que debe pasar el tipo `String` al parámetro de tipo `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Si el compilador no puede inferir los argumentos de tipo desde el contexto de la llamada, notifica un error. Una posible causa de este tipo de error es un error de coincidencia de rango de matriz. Por ejemplo, supongamos que define un parámetro normal como una matriz de un parámetro de tipo. Si se llama al procedimiento genérico proporcionando una matriz de un rango diferente (número de dimensiones), hace que la falta de correspondencia producirá un error de inferencia de tipo. El código siguiente muestra una llamada en la que se pasa una matriz bidimensional a un procedimiento que espera una matriz unidimensional.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 Puede invocar la inferencia de tipo omitiendo todos los argumentos de tipo. Si se proporciona un argumento de tipo, debe proporcionar todas ellas.  
  
 Inferencia de tipos solo se admite para los procedimientos genéricos. No se puede invocar la inferencia de tipo en clases genéricas, estructuras, interfaces o delegados.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se define un tipo genérico `Function` procedimiento para buscar un elemento determinado en una matriz. Define un parámetro de tipo y lo utiliza para construir los dos parámetros en la lista de parámetros.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a>Comentarios  
 En el ejemplo anterior, se requiere la capacidad para comparar `searchValue` con cada elemento de `searchArray`. Para garantizar esta capacidad, restringe el parámetro de tipo `T` para implementar la <xref:System.IComparable%601> interfaz. El código usa el <xref:System.IComparable%601.CompareTo%2A> en lugar del método la `=` (operador), porque no hay ninguna garantía de que un argumento de tipo proporcionado para `T` es compatible con la `=` operador.  
  
 Puede probar el `findElement` procedimiento con el código siguiente.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Los anteriores llamadas a `MsgBox` muestran respectivamente "0", "1" y "-1".  
  
## <a name="see-also"></a>Vea también  
 [Tipos genéricos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [Utilizar una clase genérica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Lista de tipos](../../../../visual-basic/language-reference/statements/type-list.md)  
 [Lista de parámetros](../../../../visual-basic/language-reference/statements/parameter-list.md)
