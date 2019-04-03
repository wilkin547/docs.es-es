---
title: Los métodos de 'System.Nullable(Of T)' no se pueden utilizar como operandos del operador 'AddressOf'
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 54d66a60d20a6add4c2b4a160f87b58b5a1d00e9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817271"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a><span data-ttu-id="fb81e-102">Los métodos de 'System.Nullable(Of T)' no se pueden utilizar como operandos del operador 'AddressOf'</span><span class="sxs-lookup"><span data-stu-id="fb81e-102">Methods of 'System.Nullable(Of T)' cannot be used as operands of the 'AddressOf' operator</span></span>
<span data-ttu-id="fb81e-103">Una instrucción usa la `AddressOf` operador con un operando que representa un procedimiento de la <xref:System.Nullable%601> estructura.</span><span class="sxs-lookup"><span data-stu-id="fb81e-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="fb81e-104">**Identificador de error:** BC32126</span><span class="sxs-lookup"><span data-stu-id="fb81e-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fb81e-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="fb81e-105">To correct this error</span></span>  
  
-   <span data-ttu-id="fb81e-106">Reemplace el nombre del procedimiento en el `AddressOf` cláusula con un operando que no es un miembro de <xref:System.Nullable%601>.</span><span class="sxs-lookup"><span data-stu-id="fb81e-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
-   <span data-ttu-id="fb81e-107">Escribir una clase que contiene el método de <xref:System.Nullable%601> que desea usar.</span><span class="sxs-lookup"><span data-stu-id="fb81e-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="fb81e-108">En el ejemplo siguiente, la `NullableWrapper` clase define un nuevo método denominado `GetValueOrDefault`.</span><span class="sxs-lookup"><span data-stu-id="fb81e-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="fb81e-109">Dado que este nuevo método no es un miembro de <xref:System.Nullable%601>, éste puede aplicarse a `nullInstance`, una instancia de un tipo que acepta valores NULL, para formar un argumento para `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="fb81e-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb81e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb81e-110">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="fb81e-111">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="fb81e-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="fb81e-112">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="fb81e-112">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="fb81e-113">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb81e-113">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
