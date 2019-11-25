---
title: Varianza en delegados
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 11146bc4a60f55fc0373f0b5dfa5d44dcf748a5b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349001"
---
# <a name="variance-in-delegates-visual-basic"></a>Variance in Delegates (Visual Basic)

.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic. Esto significa que puede asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado. Esto incluye delegados genéricos y no genéricos.

Por ejemplo, consideremos el siguiente código, que tiene dos clases y dos delegados: genéricos y no genéricos.

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

Al crear delegados de los tipos `SampleDelegate` o `SampleDelegate(Of A, R)`, puede asignar uno de los métodos siguientes a dichos delegados.

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

En el ejemplo de código siguiente se ilustra la conversión implícita entre la firma del método y el tipo de delegado.

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

## <a name="variance-in-generic-type-parameters"></a>Varianza en parámetros de tipo genérico

In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.

Para habilitar la conversión implícita, debe declarar explícitamente parámetros genéricos en un delegado como covariante o contravariante mediante la palabra clave `in` o `out`.

En el ejemplo de código siguiente se muestra cómo se crea un delegado que tiene un parámetro de tipo genérico covariante.

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

Si usa solo la compatibilidad con la varianza para hacer coincidir firmas de método con tipos de delegados y no usa las palabras clave `in` y `out`, es posible que en algunas ocasiones pueda crear instancias de delegados con métodos o expresiones lambda idénticos, pero no pueda asignar un delegado a otro.

In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`. Para solucionar este problema, marque el parámetro genérico `T` con la palabra clave `out`.

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Delegados genéricos con parámetros de tipo variante en .NET Framework

En .NET Framework 4 se presentó por primera vez la compatibilidad con la varianza para los parámetros de tipo genérico en varios delegados genéricos existentes:

- `Action` delega del espacio de nombres <xref:System>, por ejemplo, <xref:System.Action%601> y <xref:System.Action%602>

- `Func` delega del espacio de nombres <xref:System>, por ejemplo, <xref:System.Func%601> y <xref:System.Func%602>

- Delegado <xref:System.Predicate%601>.

- Delegado <xref:System.Comparison%601>.

- Delegado <xref:System.Converter%602>.

For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Declarar parámetros de tipo variante en delegados genéricos

Si un delegado genérico tiene parámetros de tipo genérico covariante o contravariante, se puede hacer referencia a él como un *delegado genérico variante*.

Puede declarar un parámetro de tipo genérico covariante en un delegado genérico mediante la palabra clave `out`. El tipo covariante puede usarse solo como un tipo de valor devuelto de método, y no como un tipo de argumentos de método. En el siguiente ejemplo de código se muestra cómo declarar un delegado genérico covariante.

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

Puede declarar un parámetro de tipo genérico contravariante en un delegado genérico mediante la palabra clave `in`. El tipo contravariante puede usarse solo como un tipo de argumentos de método, y no como un tipo de valor devuelto de método. En el siguiente ejemplo de código se muestra cómo declarar un delegado genérico contravariante.

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> `ByRef` parameters in Visual Basic can't be marked as variant.

También es posible admitir la varianza y la covarianza en el mismo delegado, pero para parámetros de tipo diferentes. Esta implementación se muestra en el ejemplo siguiente.

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Crear instancias de delegados genéricos variantes e invocarlos

Puede crear instancias de delegados variantes e invocarlos del mismo modo que crea instancias de delegados invariables y los invoca. En el ejemplo siguiente, se crea una instancia del delegado mediante una expresión lambda.

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a>Combinar delegados genéricos variantes

No debe combinar delegados variantes. El método <xref:System.Delegate.Combine%2A> no admite la conversión de delegados variantes y espera que los delegados sean exactamente del mismo tipo. This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianza en parámetros de tipo genérico para los tipos de referencia y valor

La varianza para parámetros de tipo genérico solo es compatible con tipos de referencia. For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.

En el ejemplo siguiente se muestra que la varianza en parámetros de tipo genérico no se admite para tipos de valor.

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Relaxed Delegate Conversion in Visual Basic

Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types. For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate. For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).

## <a name="see-also"></a>Vea también

- [Genéricos](../../../../standard/generics/index.md)
- [Usar la varianza para los delegados genéricos Func y Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
