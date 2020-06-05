---
title: Los métodos de 'System.Nullable(Of T)' no se pueden utilizar como operandos del operador 'AddressOf'
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 61c6fe7c33b3292066e653304ded43a863413723
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397225"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a>Los métodos de 'System.Nullable(Of T)' no se pueden utilizar como operandos del operador 'AddressOf'
Una instrucción utiliza el `AddressOf` operador con un operando que representa un procedimiento de la <xref:System.Nullable%601> estructura.  
  
 **Identificador de error:** BC32126  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Reemplace el nombre del procedimiento en la `AddressOf` cláusula por un operando que no sea miembro de <xref:System.Nullable%601> .  
  
- Escriba una clase que contenga el método de <xref:System.Nullable%601> que desea usar. En el ejemplo siguiente, la `NullableWrapper` clase define un nuevo método denominado `GetValueOrDefault` . Dado que este nuevo método no es miembro de <xref:System.Nullable%601> , se puede aplicar a `nullInstance` , una instancia de un tipo que acepta valores NULL, para formar un argumento para `AddressOf` .  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Nullable%601>
- [AddressOf (operador)](../operators/addressof-operator.md)
- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
