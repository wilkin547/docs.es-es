---
title: Covarianza y contravarianza
ms.date: 07/20/2015
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
ms.openlocfilehash: 11dd71a8cfde12b7af1de79e3f5a095f79d8aa6e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400634"
---
# <a name="covariance-and-contravariance-visual-basic"></a>Covarianza y contravarianza (Visual Basic)

En Visual Basic, la covarianza y la contravarianza habilitan la conversión de referencias implícita de tipos de matriz, tipos de delegado y argumentos de tipo genérico. La covarianza conserva la compatibilidad de asignaciones y la contravarianza la invierte.

El siguiente código muestra la diferencia entre la compatibilidad de asignaciones, la covarianza y la contravarianza.

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

La covarianza de matrices permite la conversión implícita de una matriz de un tipo más derivado a una matriz de un tipo menos derivado. Pero esta operación no es segura, tal como se muestra en el ejemplo de código siguiente.

```vb
Dim array() As Object = New String(10) {}
' The following statement produces a run-time exception.
' array(0) = 10
```

La compatibilidad de la covarianza y la contravarianza con grupos de métodos permite hacer coincidir firmas de método con tipos de delegado. Esto le permite asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado. Para obtener más información, vea [Variance in Delegates (Visual Basic)](variance-in-delegates.md) (Varianza en delegados (Visual Basic)) y [Using Variance in Delegates (Visual Basic)](using-variance-in-delegates.md) (Usar varianza en delegados (Visual Basic)).

En el ejemplo de código siguiente, se muestra la compatibilidad de covarianza y contravarianza con grupos de métodos.

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

En .NET Framework 4 o posterior, Visual Basic admite la covarianza y la contravarianza en interfaces y delegados genéricos y permite la conversión implícita de parámetros de tipo genérico. Para obtener más información, vea [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md) (Varianza en interfaces genéricas (Visual Basic)) y [Variance in Delegates (Visual Basic)](variance-in-delegates.md) (Varianza en delegados (Visual Basic)).

En el ejemplo de código siguiente, se muestra la conversión implícita de referencias para interfaces genéricas.

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

Un delegado o interfaz genéricos se denominan *variante* si sus parámetros genéricos se declaran como covariantes o contravariantes. Visual Basic le permite crear sus propias interfaces y delegados variantes. Para obtener más información, vea [Creating Variant Generic Interfaces (Visual Basic)](creating-variant-generic-interfaces.md) (Crear interfaces genéricas variantes (Visual Basic)) y [Variance in Delegates (Visual Basic)](variance-in-delegates.md) (Varianza en delegados (Visual Basic)).

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md)|Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.|
|[Crear interfaces genéricas variantes (Visual Basic)](creating-variant-generic-interfaces.md)|Se muestra cómo crear interfaces variantes personalizadas.|
|[Usar la varianza en interfaces para las colecciones genéricas (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md)|Se muestra cómo la compatibilidad de covarianza y contravarianza en las interfaces <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601> puede ayudarle a volver a usar el código.|
|[Varianza en delegados (Visual Basic)](variance-in-delegates.md)|Se describe la covarianza y contravarianza en delegados genéricos y no genéricos y se proporciona una lista de delegados genéricos variantes en .NET Framework.|
|[Usar varianza en delegados (Visual Basic)](using-variance-in-delegates.md)|Se muestra cómo usar la compatibilidad de covarianza y contravarianza en los delegados no genéricos para que coincidan las firmas de método con los tipos de delegado.|
|[Usar la varianza para los delegados genéricos Func y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)|Se muestra cómo la compatibilidad de covarianza y contravarianza en los delegados `Func` y `Action` puede ayudarle a volver a usar el código.|
