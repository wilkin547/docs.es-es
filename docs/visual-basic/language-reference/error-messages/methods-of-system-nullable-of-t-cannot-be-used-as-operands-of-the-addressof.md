---
title: "Métodos de &#39; System. Nullable (Of T) &#39; no se pueden utilizar como operandos de la &#39; AddressOf &#39; operador"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords: BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ce0e9bc6abd71f22e3f6c3486ef40493e74d820f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="methods-of-39systemnullableof-t39-cannot-be-used-as-operands-of-the-39addressof39-operator"></a>Métodos de &#39; System. Nullable (Of T) &#39; no se pueden utilizar como operandos de la &#39; AddressOf &#39; operador
Una instrucción usa la `AddressOf` operador con un operando que representa un procedimiento con el <xref:System.Nullable%601> estructura.  
  
 **Id. de error:** BC32126  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Reemplace el nombre del procedimiento en el `AddressOf` cláusula con un operando que no es un miembro de <xref:System.Nullable%601>.  
  
-   Escriba una clase que contiene el método de <xref:System.Nullable%601> que desea usar. En el ejemplo siguiente, la `NullableWrapper` clase define un nuevo método denominado `GetValueOrDefault`. Dado que este nuevo método no es un miembro de <xref:System.Nullable%601>, éste puede aplicarse a `nullInstance`, una instancia de un tipo que acepta valores NULL, para formar un argumento para `AddressOf`.  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Nullable%601>  
 [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
