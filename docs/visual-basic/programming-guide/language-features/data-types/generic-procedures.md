---
title: Procedimientos genéricos
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
ms.openlocfilehash: 16a629e07cf711778b3d8d1863958ec7a6300649
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350082"
---
# <a name="generic-procedures-in-visual-basic"></a>Procedimientos genéricos en Visual Basic
Un *procedimiento genérico*, también denominado *método genérico*, es un procedimiento definido con al menos un parámetro de tipo. Esto permite que el código de llamada adapte los tipos de datos a sus requisitos cada vez que llama al procedimiento.  
  
 Un procedimiento no es genérico simplemente en virtud de definirse dentro de una clase genérica o en una estructura genérica. Para que sea genérico, el procedimiento debe tomar al menos un parámetro de tipo, además de los parámetros normales que puede llevar a cabo. Una clase o estructura genérica puede contener procedimientos no genéricos, y una clase, estructura o módulo no genéricos pueden contener procedimientos genéricos.  
  
 Un procedimiento genérico puede usar sus parámetros de tipo en su lista de parámetros normal, en su tipo de valor devuelto si tiene uno, y en su código de procedimiento.  
  
## <a name="type-inference"></a>Inferencia de tipos  
 Puede llamar a un procedimiento genérico sin proporcionar ningún argumento de tipo. Si se llama de esta manera, el compilador intenta determinar los tipos de datos adecuados que se van a pasar a los argumentos de tipo del procedimiento. Esto se denomina *inferencia de tipos*. En el código siguiente se muestra una llamada en la que el compilador deduce que debe pasar el tipo `String` al parámetro de tipo `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 Si el compilador no puede inferir los argumentos de tipo del contexto de la llamada, notifica un error. Una posible causa de este error es que la clasificación de una matriz no coincide. Por ejemplo, supongamos que define un parámetro normal como una matriz de un parámetro de tipo. Si llama al procedimiento genérico que proporciona una matriz de un rango diferente (número de dimensiones), la incoherencia provocará un error en la inferencia de tipos. En el código siguiente se muestra una llamada en la que se pasa una matriz bidimensional a un procedimiento que espera una matriz unidimensional.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 Solo se puede invocar la inferencia de tipos si se omiten todos los argumentos de tipo. Si proporciona un argumento de tipo, debe proporcionarlos todos.  
  
 La inferencia de tipos solo se admite para los procedimientos genéricos. No se puede invocar la inferencia de tipos en clases, estructuras, interfaces o delegados genéricos.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el ejemplo siguiente se define un procedimiento genérico `Function` para buscar un elemento determinado en una matriz. Define un parámetro de tipo y lo usa para construir los dos parámetros en la lista de parámetros.  
  
### <a name="code"></a>Código  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Comentarios  
 En el ejemplo anterior se requiere la capacidad de comparar `searchValue` con cada elemento de `searchArray`. Para garantizar esta capacidad, restringe el parámetro de tipo `T` para implementar la interfaz de <xref:System.IComparable%601>. El código utiliza el método <xref:System.IComparable%601.CompareTo%2A> en lugar del operador `=`, porque no hay ninguna garantía de que un argumento de tipo proporcionado para `T` admita el operador `=`.  
  
 Puede probar el procedimiento `findElement` con el código siguiente.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Las llamadas anteriores a `MsgBox` Mostrar "0", "1" y "-1", respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Definir una clase que pueda proporcionar la misma funcionalidad en tipos de datos diferentes](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Utilizar una clase genérica](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Lista de tipos](../../../../visual-basic/language-reference/statements/type-list.md)
- [Lista de parámetros](../../../../visual-basic/language-reference/statements/parameter-list.md)
