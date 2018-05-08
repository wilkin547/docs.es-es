---
title: No se puede convertir un tipo anónimo en un árbol de expresión porque contiene un campo que se usa en la inicialización de otro campo
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: d43f6ef19591af326d06a4ce21194d8f9fa58c2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>No se puede convertir un tipo anónimo en un árbol de expresión porque contiene un campo que se usa en la inicialización de otro campo
El compilador no acepta la conversión de un anónimo a un árbol de expresión cuando una propiedad del tipo anónimo se utiliza para inicializar otra propiedad del tipo anónimo. Por ejemplo, en el código siguiente, `Prop1` se declara en la lista de inicialización y, a continuación, se utiliza como valor inicial para `Prop2`.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Id. de error:** BC36548  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asigne el valor inicial para `Prop1` a una variable local. Asigne esta variable a ambos `Prop1` y `Prop2`, tal y como se muestra en el código siguiente.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Tipos anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Árboles de expresión](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [Usar árboles de expresión para crear consultas dinámicas](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
