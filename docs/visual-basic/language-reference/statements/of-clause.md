---
title: Of (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: c0cfbb5109d5b49f995028944e735c96440c9ab2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583507"
---
# <a name="of-clause-visual-basic"></a>Of (Cláusula, Visual Basic)
Presenta una cláusula `Of`, que identifica un *parámetro de tipo* en una clase *genérica* , una estructura, una interfaz, un delegado o un procedimiento. Para obtener información sobre los tipos genéricos, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Usar la palabra clave of  
 En el ejemplo de código siguiente se usa la palabra clave `Of` para definir el contorno de una clase que toma dos parámetros de tipo. *Restringe* el parámetro `keyType` por la interfaz <xref:System.IComparable>, lo que significa que el código utilizado debe proporcionar un argumento de tipo que implementa <xref:System.IComparable>. Esto es necesario para que el procedimiento `add` pueda llamar al método <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType>. Para más información sobre las restricciones, vea [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 Si completa la definición de clase anterior, puede construir una variedad de clases `dictionary` a partir de ella. Los tipos que se proporcionan a `entryType` y `keyType` determinan qué tipo de entrada contiene la clase y qué tipo de clave asocia a cada entrada. Debido a la restricción, debe proporcionar a `keyType` un tipo que implementa <xref:System.IComparable>.  
  
 En el ejemplo de código siguiente se crea un objeto que contiene `String` entradas y asocia una clave `Integer` a cada una de ellas. `Integer` implementa <xref:System.IComparable> y, por tanto, satisface la restricción en `keyType`.  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 La palabra clave `Of` se puede usar en los siguientes contextos:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- <xref:System.IComparable>
- [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
