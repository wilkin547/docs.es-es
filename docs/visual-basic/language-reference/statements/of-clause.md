---
title: "Of (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a>Of (Cláusula, Visual Basic)
Presenta un `Of` cláusula, que identifica un *parámetro de tipo* en un *genérico* clase, estructura, interfaz, delegado o procedimiento. Para obtener información sobre los tipos genéricos, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## <a name="using-the-of-keyword"></a>Mediante la palabra clave  
 El siguiente ejemplo de código utiliza la `Of` (palabra clave) para definir el contorno de una clase que toma dos parámetros de tipo. Se *restringe* el `keyType` parámetro por la <xref:System.IComparable> interfaz, lo que significa que el código utilizado debe proporcionar un argumento de tipo que implementa <xref:System.IComparable>. Esto es necesario para que la `add` procedimiento puede llamar a la <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> método. Para obtener más información sobre las restricciones, vea [lista de tipo](../../../visual-basic/language-reference/statements/type-list.md).  
  
```  
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
  
 Si completa la definición de clase anterior, puede construir una variedad de `dictionary` clases de él. Los tipos que se pasan al `entryType` y `keyType` determinar qué tipo de entrada de la clase contiene y qué tipo de clave se asocia a cada entrada. Debido a la restricción, debe proporcionar al `keyType` un tipo que implementa <xref:System.IComparable>.  
  
 En el ejemplo de código siguiente se crea un objeto que contiene `String` entradas y asocia un `Integer` clave con cada uno de ellos. `Integer`implementa <xref:System.IComparable> y por consiguiente satisface la restricción en `keyType`.  
  
```  
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
 <xref:System.IComparable>  
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
