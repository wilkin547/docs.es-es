---
title: Varianza en delegados (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
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
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a>Varianza en delegados (Visual Basic)
.NET framework 3.5 introdujo la compatibilidad con la varianza para hacer coincidir las firmas de método con tipos de delegado en todos los delegados en C# y Visual Basic. Esto significa que puede asignar a los delegados no sólo los métodos con firmas coincidentes, sino también los métodos que devuelven más derivados de tipos (covarianza) o que aceptan parámetros que tienen tipos menos derivados (contravarianza) que el especificado por el tipo de delegado. Esto incluye a los delegados genéricos y no genéricos.  
  
 Por ejemplo, considere el siguiente código, que tiene dos clases y dos delegados: genéricos y no genéricos.  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 Al crear delegados de la `SampleDelegate` o `SampleDelegate(Of A, R)` tipos, puede asignar uno de los siguientes métodos a dichos delegados.  
  
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
  
 Para obtener más ejemplos, vea [utilizar varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) y [Using Variance for Func y Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
## <a name="variance-in-generic-type-parameters"></a>Varianza en parámetros de tipo genérico  
 En .NET Framework 4 y versiones posteriores puede habilitar la conversión implícita entre los delegados, para que los delegados genéricos con parámetros de tipo genérico especifican tipos distintos pueden asignarse entre sí, si los tipos se hereden entre sí como requiere la varianza.  
  
 Para habilitar la conversión implícita, debe declarar explícitamente los parámetros genéricos de un delegado como covariante o contravariante utilizando la `in` o `out` (palabra clave).  
  
 En el ejemplo de código siguiente se muestra cómo crear a un delegado que tiene un parámetro de tipo genérico covariante.  
  
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
  
 Si utiliza sólo admiten la varianza para hacer coincidir las firmas de método con tipos de delegado y no use el `in` y `out` palabras clave, es posible que a veces se pueden crear instancias de delegados con métodos o expresiones lambda idénticos, pero no se puede asignar un delegado a otro.  
  
 En el ejemplo de código siguiente, `SampleGenericDelegate(Of String)` no se puede convertir explícitamente a `SampleGenericDelegate(Of Object)`, aunque `String` hereda `Object`. Puede solucionar este problema, marque el parámetro genérico `T` con el `out` (palabra clave).  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Parámetros de tipo de los delegados genéricos que tengan variante en .NET Framework  
 .NET framework 4 introdujo la compatibilidad con la varianza para los parámetros de tipo genérico en varios delegados genéricos existentes:  
  
-   `Action`delegados de la <xref:System>espacio de nombres, por ejemplo, <xref:System.Action%601>y <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System>  
  
-   `Func`delegados de la <xref:System>espacio de nombres, por ejemplo, <xref:System.Func%601>y <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System>  
  
-   El <xref:System.Predicate%601>delegado</xref:System.Predicate%601>  
  
-   El <xref:System.Comparison%601>delegado</xref:System.Comparison%601>  
  
-   El <xref:System.Converter%602>delegado</xref:System.Converter%602>  
  
 Para obtener más información y ejemplos, vea [Using Variance for Func y Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Declarar parámetros de tipo variante en delegados genéricos  
 Si un delegado genérico tiene covariante o parámetros de tipo genérico contravariante, que puede hacer referencia como un *delegado genérico variante*.  
  
 Puede declarar un parámetro de tipo genérico covariante en un delegado genérico mediante la `out` (palabra clave). El tipo covariante puede usarse solo como un tipo de valor devuelto del método y no como un tipo de argumentos de método. En el ejemplo de código siguiente se muestra cómo declarar a un delegado genérico covariante.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 Puede declarar una contravariante del parámetro de tipo genérico en un delegado genérico mediante la `in` (palabra clave). El tipo contravariante puede usarse solo como un tipo de argumentos de método y no como un tipo de valor devuelto del método. En el ejemplo de código siguiente se muestra cómo declarar a un delegado genérico contravariante.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  `ByRef`parámetros de Visual Basic no se pueden marcar como variante.  
  
 También es posible admitir la varianza y la covarianza en el mismo delegado, pero para distintos parámetros de tipo. Esta implementación se muestra en el ejemplo siguiente.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Crear instancias e invocar delegados genéricos variantes  
 Puede crear instancias e invocar a delegados variantes igual que crear instancias e invoca delegados invariables. En el ejemplo siguiente, se crea una instancia del delegado mediante una expresión lambda.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
### <a name="combining-variant-generic-delegates"></a>Combinación de delegados genéricos variantes  
 No debe combinar a delegados variantes. El <xref:System.Delegate.Combine%2A>método no admite la conversión de delegado variantes y espera que los delegados para ser del mismo tipo.</xref:System.Delegate.Combine%2A> Esto puede provocar una excepción en tiempo de ejecución al combinar delegados mediante la <xref:System.Delegate.Combine%2A>(método) (en C# y Visual Basic) o mediante el `+` (operador) (en C#), tal como se muestra en el ejemplo de código siguiente.</xref:System.Delegate.Combine%2A>  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianza en parámetros de tipo genérico para los tipos de referencia y valor  
 Varianza en parámetros de tipo genérico es compatible con sólo los tipos de referencia. Por ejemplo, `DVariant(Of Int)`no se puede convertir implícitamente a `DVariant(Of Object)` o `DVariant(Of Long)`, porque integer es un tipo de valor.  
  
 En el ejemplo siguiente se muestra que la varianza de tipo genérico con parámetros no se admite para tipos de valor.  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Conversión de delegado flexible en Visual Basic  
 Conversión de delegado flexible permite más flexibilidad en la coincidencia de las firmas de método con tipos de delegado. Por ejemplo, permite omitir las especificaciones de parámetro y omite los valores devueltos de función al asignar un método a un delegado. Para obtener más información, consulte [la conversión de delegado no estricta](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="see-also"></a>Vea también  
 [Genéricos](https://msdn.microsoft.com/library/ms172192)   
 [Usar la varianza para Func y Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
