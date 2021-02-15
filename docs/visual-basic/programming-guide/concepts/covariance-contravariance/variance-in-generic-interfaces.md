---
description: 'Más información sobre: varianza en interfaces genéricas (Visual Basic)'
title: Varianza en interfaces genéricas
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: 42257f80cb929756583b1e488cd315450b9db35e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100469843"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a>Varianza en interfaces genéricas (Visual Basic)

En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes. La compatibilidad con la varianza permite la conversión implícita de clases que implementan estas interfaces. Las interfaces siguientes ahora son variantes:

- <xref:System.Collections.Generic.IEnumerable%601> (T es covariante)

- <xref:System.Collections.Generic.IEnumerator%601> (T es covariante)

- <xref:System.Linq.IQueryable%601> (T es covariante)

- <xref:System.Linq.IGrouping%602> (`TKey` y `TElement` son covariantes)

- <xref:System.Collections.Generic.IComparer%601> (T es contravariante)

- <xref:System.Collections.Generic.IEqualityComparer%601> (T es contravariante)

- <xref:System.IComparable%601> (T es contravariante)

La covarianza permite que un método tenga un tipo de valor devuelto más derivado que los que se definen en los parámetros de tipo genérico de la interfaz. Para ilustrar la característica de la covarianza, considere estas interfaces genéricas: `IEnumerable(Of Object)` y `IEnumerable(Of String)`. La interfaz `IEnumerable(Of String)` no hereda la interfaz `IEnumerable(Of Object)`. En cambio, el tipo `String` hereda el tipo `Object`, y en algunos casos puede que quiera asignar objetos de estas interfaces entre sí. Esto se muestra en el ejemplo de código siguiente.

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

En versiones anteriores del .NET Framework, este código produce un error de compilación en Visual Basic con `Option Strict On` . Pero ahora puede usar `strings` en lugar de `objects`, como se muestra en el ejemplo anterior, porque la interfaz <xref:System.Collections.Generic.IEnumerable%601> es covariante.

La contravarianza permite que un método tenga tipos de argumento menos derivados que los que se especifican en el parámetro genérico de la interfaz. Para ilustrar la contravarianza, se presupone que ha creado una clase `BaseComparer` para comparar instancias de la clase `BaseClass`. La clase `BaseComparer` implementa la interfaz `IEqualityComparer(Of BaseClass)`. Como la interfaz <xref:System.Collections.Generic.IEqualityComparer%601> ahora es contravariante, puede usar `BaseComparer` para comparar instancias de clases que heredan la clase `BaseClass`. Esto se muestra en el ejemplo de código siguiente.

```vb
' Simple hierarchy of classes.
Class BaseClass
End Class

Class DerivedClass
    Inherits BaseClass
End Class

' Comparer class.
Class BaseComparer
    Implements IEqualityComparer(Of BaseClass)

    Public Function Equals1(ByVal x As BaseClass,
                            ByVal y As BaseClass) As Boolean _
                            Implements IEqualityComparer(Of BaseClass).Equals
        Return (x.Equals(y))
    End Function

    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _
        Implements IEqualityComparer(Of BaseClass).GetHashCode
        Return obj.GetHashCode
    End Function
End Class
Sub Test()
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to
    ' IEqualityComparer(Of DerivedClass).
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer
End Sub
```

Para obtener más ejemplos, vea [usar la varianza en interfaces para colecciones genéricas (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md).

La varianza para interfaces genéricas solo es compatible con tipos de referencia. Los tipos de valor no admiten la varianza. Por ejemplo, `IEnumerable(Of Integer)` no puede convertirse implícitamente en `IEnumerable(Of Object)`, porque los enteros se representan mediante un tipo de valor.

```vb
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)
' The following statement generates a compiler error
' with Option Strict On, because Integer is a value type.
' Dim objects As IEnumerable(Of Object) = integers
```

También es importante recordar que las clases que implementan las interfaces variantes siguen siendo invariables. Por ejemplo, aunque <xref:System.Collections.Generic.List%601> implementa la interfaz covariante <xref:System.Collections.Generic.IEnumerable%601>, no puede convertir `List(Of Object)` en `List(Of String)` implícitamente. Esto se muestra en el siguiente código de ejemplo.

```vb
' The following statement generates a compiler error
' because classes are invariant.
' Dim list As List(Of Object) = New List(Of String)

' You can use the interface object instead.
Dim listObjects As IEnumerable(Of Object) = New List(Of String)
```

## <a name="see-also"></a>Vea también

- [Usar la varianza en interfaces para las colecciones genéricas (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md)
- [Crear interfaces genéricas variantes (Visual Basic)](creating-variant-generic-interfaces.md)
- [Interfaces genéricas](../../../../standard/generics/interfaces.md)
- [Varianza en delegados (Visual Basic)](variance-in-delegates.md)
