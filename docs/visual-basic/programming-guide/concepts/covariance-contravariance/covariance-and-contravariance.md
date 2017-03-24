---
title: Covarianza y contravarianza (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b785e298c5ba38a8e3d8cc549b2dcf2df1ef6bd8
ms.lasthandoff: 03/13/2017

---
# <a name="covariance-and-contravariance-visual-basic"></a>Covarianza y contravarianza (Visual Basic)
En Visual Basic, covarianza y contravarianza habilitar la conversión de referencia implícita de tipos de matriz, tipos de delegado y argumentos de tipo genérico. Covarianza mantiene la compatibilidad de asignación y la contravarianza invierte.  
  
 El código siguiente muestra la diferencia entre la compatibilidad con la asignación, covarianza y contravarianza.  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 Covarianza de matrices, permite la conversión implícita de una matriz de un tipo más derivado a una matriz de un tipo menos derivado. Pero esta operación no es seguro, tal como se muestra en el ejemplo de código siguiente.  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 Covarianza y contravarianza grupos de métodos permite para hacer coincidir las firmas de método con tipos de delegado. Esto permite asignar a los delegados no solo los métodos que coincidan las firmas, sino también los métodos que devuelven que más derivados (covarianza) de tipos o que acepta parámetros que tienen tipos menos derivados (contravarianza) que el especificado por el tipo de delegado. Para obtener más información, consulte [varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [utilizar varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
 En el ejemplo de código siguiente se muestra la covarianza y contravarianza soporte para grupos de métodos.  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 En .NET Framework 4 o posterior Visual Basic admiten la covarianza y contravarianza en interfaces y delegados genéricos y permiten la conversión implícita de parámetros de tipo genérico. Para obtener más información, consulte [varianza en Interfaces genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) y [varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
 En el ejemplo de código siguiente se muestra la conversión implícita de referencia para las interfaces genéricas.  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 Una interfaz genérica o delegado se denomina *variante* si sus parámetros genéricos se declaran covariantes o contravariante. Visual Basic le permite crear sus propias interfaces y delegados variantes. Para obtener más información, consulte [crear Interfaces genéricas variantes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) y [varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|-----------|-----------------|  
|[Varianza en Interfaces genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.|  
|[Crear Interfaces genéricas variantes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|Muestra cómo crear interfaces variantes personalizadas.|  
|[Usar la varianza en Interfaces para las colecciones genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|Muestra cómo admiten la covarianza y contravarianza en los <xref:System.Collections.Generic.IEnumerable%601>y <xref:System.IComparable%601>interfaces pueden ayudarle a reutilizar el código.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|[Varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|Describe la covarianza y contravarianza en delegados genéricos y no genéricos y proporciona una lista de delegados genéricos variantes en .NET Framework.|  
|[Utilizar varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|Muestra cómo utilizar la compatibilidad con la covarianza y contravarianza en delegados no genéricos para hacer coincidir las firmas de método con tipos de delegado.|  
|[Usar la varianza para Func y Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|Muestra cómo admiten la covarianza y contravarianza en los `Func` y `Action` delegados pueden ayudarle a reutilizar el código.|
