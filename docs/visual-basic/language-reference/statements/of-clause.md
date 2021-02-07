---
description: 'Más información sobre: cláusula of (Visual Basic)'
title: Cláusula Of
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
ms.openlocfilehash: d6002041a2fe8db5b07e12e9e396a65fde30b716
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768849"
---
# <a name="of-clause-visual-basic"></a>Of (Cláusula, Visual Basic)

Introduce una `Of` cláusula, que identifica un *parámetro de tipo* en una clase *genérica* , una estructura, una interfaz, un delegado o un procedimiento. Para obtener información sobre los tipos genéricos, vea [tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Usar la palabra clave of  

 En el ejemplo de código siguiente `Of` se usa la palabra clave para definir el contorno de una clase que toma dos parámetros de tipo. *Restringe* el `keyType` parámetro mediante la <xref:System.IComparable> interfaz, lo que significa que el código utilizado debe proporcionar un argumento de tipo que implemente <xref:System.IComparable> . Esto es necesario para que el `add` procedimiento pueda llamar al <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> método. Para más información sobre las restricciones, vea [Type List](type-list.md).  
  
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
  
 Si completa la definición de clase anterior, puede crear una variedad de `dictionary` clases a partir de ella. Los tipos que se suministran a `entryType` y `keyType` determinan qué tipo de entrada contiene la clase y qué tipo de clave asocia a cada entrada. Debido a la restricción, debe proporcionar a `keyType` un tipo que implementa <xref:System.IComparable> .  
  
 En el ejemplo de código siguiente se crea un objeto que contiene `String` entradas y asocia una `Integer` clave a cada una de ellas. `Integer` implementa <xref:System.IComparable> y, por tanto, satisface la restricción en `keyType` .  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 La palabra clave `Of` se puede usar en los siguientes contextos:  
  
 [Instrucción Class](class-statement.md)  
  
 [Delegate (Instrucción)](delegate-statement.md)  
  
 [Instrucción Function](function-statement.md)  
  
 [Instrucción Interface](interface-statement.md)  
  
 [Structure (Instrucción)](structure-statement.md)  
  
 [Instrucción Sub](sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- <xref:System.IComparable>
- [Type List](type-list.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [In](../modifiers/in-generic-modifier.md)
- [Fuera](../modifiers/out-generic-modifier.md)
