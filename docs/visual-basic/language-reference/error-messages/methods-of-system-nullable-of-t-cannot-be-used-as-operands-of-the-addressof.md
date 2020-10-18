---
title: Los métodos de 'System.Nullable(Of T)' no se pueden utilizar como operandos del operador 'AddressOf'
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 173cf19537e3f9ffc4cff6cef71f34b6d365e5d3
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160397"
---
# <a name="bc32126-methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a>BC32126: los métodos de ' System. Nullable (of T) ' no se pueden usar como operandos del operador ' AddressOf '

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

## <a name="see-also"></a>Vea también

- <xref:System.Nullable%601>
- [Operador AddressOf](../operators/addressof-operator.md)
- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
