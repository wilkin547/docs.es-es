---
title: "Los m&#233;todos de &#39;System.Nullable(Of T)&#39; no se pueden utilizar como operandos del operador &#39;AddressOf&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32126"
  - "bc32126"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32126"
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Los m&#233;todos de &#39;System.Nullable(Of T)&#39; no se pueden utilizar como operandos del operador &#39;AddressOf&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una instrucción usa el operador `AddressOf` con un operando que representa un procedimiento de la estructura <xref:System.Nullable%601>.  
  
 **Id. de error:** BC32126  
  
### Para corregir este error  
  
-   Reemplace el nombre de procedimiento en la cláusula `AddressOf` por un operando que no sea miembro de <xref:System.Nullable%601>.  
  
-   Escriba una clase que incluya el método de <xref:System.Nullable%601> que desea usar.  En el ejemplo siguiente, la clase `NullableWrapper` define un nuevo método denominado `GetValueOrDefault`.  Dado que este nuevo método no es miembro de <xref:System.Nullable%601>, se puede aplicar a `nullInstance`, una instancia de un tipo que acepta valores NULL, para formar un argumento para `AddressOf`.  
  
    ```vb#  
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
  
## Vea también  
 <xref:System.Nullable%601>   
 [AddressOf \(Operador\)](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)