---
title: Creación de interfaces genéricas variantes
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 884349159d2738d8481b217f9dab383483616f2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400647"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Crear interfaces genéricas variantes (Visual Basic)

Puede declarar parámetros de tipo genérico en las interfaces como covariantes o contravariantes. La *covarianza* permite que los métodos de interfaz tengan tipos de valor devuelto más derivados que los que se definen en los parámetros de tipo genérico. La *contravarianza* permite que los métodos de interfaz tengan tipos de argumento menos derivados que los que se especifican en los parámetros genéricos. Las interfaces genéricas que tienen parámetros de tipo genérico covariantes o contravariantes se llaman *variantes*.

> [!NOTE]
> En .NET Framework 4 se introdujo la compatibilidad con la varianza para varias interfaces genéricas existentes. Para obtener la lista de las interfaces variantes en el .NET Framework, vea [varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Declarar interfaces genéricas variantes

Puede declarar interfaces genéricas variantes mediante las palabras clave `in` y `out` para los parámetros de tipo genérico.

> [!IMPORTANT]
> `ByRef`los parámetros de Visual Basic no pueden ser variantes. Los tipos de valor tampoco admiten la varianza.

Puede declarar un parámetro de tipo genérico covariante mediante la palabra clave `out`. El tipo covariante debe cumplir las siguientes condiciones:

- El tipo se usa únicamente como tipo de valor devuelto de los métodos de interfaz, y no como tipo de los argumentos de método. Esto se muestra en el siguiente ejemplo, en el que el tipo `R` se declara como covariante.

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    Hay una excepción para esta regla. Si tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo como parámetro de tipo genérico para el delegado. Esto se muestra en el siguiente ejemplo con el tipo `R`. Para obtener más información, vea [varianza en delegados (Visual Basic)](variance-in-delegates.md) y [usar la varianza para los delegados genéricos FUNC y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- El tipo no se usa como restricción genérica para los métodos de interfaz. Esto se muestra en el siguiente código.

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

Puede declarar un parámetro de tipo genérico contravariante mediante la palabra clave `in`. El tipo contravariante solo se puede usar como tipo de los argumentos de método, y no como tipo de valor devuelto de los métodos de interfaz. El tipo contravariante también se puede usar para las restricciones genéricas. En el siguiente código se muestra cómo declarar una interfaz contravariante y cómo usar una restricción genérica para uno de sus métodos.

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

También se puede admitir la covarianza y la contravarianza en la misma interfaz, pero para distintos parámetros de tipo, como se muestra en el siguiente ejemplo de código.

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

En Visual Basic, no se pueden declarar eventos en interfaces variantes sin especificar el tipo de delegado. Además, una interfaz variante no puede tener clases, enumeraciones o estructuras anidadas, pero puede tener interfaces anidadas. Esto se muestra en el siguiente código.

```vb
Interface ICovariant(Of Out R)
    ' The following statement generates a compiler error.
    ' Event SampleEvent()
    ' The following statement specifies the delegate type and
    ' does not generate an error.
    Event AnotherEvent As EventHandler

    ' The following statements generate compiler errors,
    ' because a variant interface cannot have
    ' nested enums, classes, or structures.

    'Enum SampleEnum : test : End Enum
    'Class SampleClass : End Class
    'Structure SampleStructure : Dim value As Integer : End Structure

    ' Variant interfaces can have nested interfaces.
    Interface INested : End Interface
End Interface
```

## <a name="implementing-variant-generic-interfaces"></a>Implementar interfaces genéricas variantes

Las interfaces genéricas variantes se implementan en las clases usando la misma sintaxis que se usa para las interfaces invariables. En el siguiente ejemplo de código se muestra cómo implementar una interfaz covariante en una clase genérica.

```vb
Interface ICovariant(Of Out R)
    Function GetSomething() As R
End Interface

Class SampleImplementation(Of R)
    Implements ICovariant(Of R)
    Public Function GetSomething() As R _
    Implements ICovariant(Of R).GetSomething
        ' Some code.
    End Function
End Class
```

Las clases que implementan interfaces variantes son invariables. Por ejemplo, considere el fragmento de código siguiente:

```vb
 The interface is covariant.
Dim ibutton As ICovariant(Of Button) =
    New SampleImplementation(Of Button)
Dim iobj As ICovariant(Of Object) = ibutton

' The class is invariant.
Dim button As SampleImplementation(Of Button) =
    New SampleImplementation(Of Button)
' The following statement generates a compiler error
' because classes are invariant.
' Dim obj As SampleImplementation(Of Object) = button
```

## <a name="extending-variant-generic-interfaces"></a>Extender interfaces genéricas variantes

Al extender una interfaz genérica variante, debe usar las palabras clave `in` y `out` para especificar de forma explícita si la interfaz derivada admite la varianza. El compilador no infiere la varianza de la interfaz que se va a extender. Por ejemplo, observe las siguientes interfaces.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T)
End Interface

Interface IExtCovariant(Of Out T)
    Inherits ICovariant(Of T)
End Interface
```

En la `Invariant(Of T)` interfaz, el parámetro de tipo genérico `T` es invariable, mientras que en `IExtCovariant (Of Out T)` el parámetro de tipo es covariante, aunque ambas interfaces amplían la misma interfaz. La misma regla se aplica a los parámetros de tipo genérico contravariantes.

Puede crear una interfaz que extienda la interfaz donde el parámetro de tipo genérico `T` es covariante y la interfaz donde es contravariante si, en la interfaz que va a extender, el parámetro de tipo genérico `T` es invariable. Esto se muestra en el siguiente código de ejemplo.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

Pero si un parámetro de tipo genérico `T` se declara como covariante en una interfaz, no puede declararlo como contravariante en la interfaz extensible (o viceversa). Esto se muestra en el siguiente código de ejemplo.

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a>Evitar la ambigüedad

Al implementar interfaces genéricas variantes, la varianza a veces puede implicar ambigüedad. Éste debería evitarse.

Por ejemplo, si implementa explícitamente en una clase la misma interfaz genérica variante con distintos parámetros de tipo genérico, puede crear ambigüedad. El compilador no genera ningún error en este caso, pero no se especifica la implementación de interfaz que se elegirá en tiempo de ejecución. Esto podría provocar errores imperceptibles en el código. Observe el siguiente ejemplo de código.

> [!NOTE]
> Con `Option Strict Off` , Visual Basic genera una advertencia del compilador cuando hay una implementación de interfaz ambigua. Con `Option Strict On` , Visual Basic genera un error del compilador.

```vb
' Simple class hierarchy.
Class Animal
End Class

Class Cat
    Inherits Animal
End Class

Class Dog
    Inherits Animal
End Class

' This class introduces ambiguity
' because IEnumerable(Of Out T) is covariant.
Class Pets
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)

    Public Function GetEnumerator() As IEnumerator(Of Cat) _
        Implements IEnumerable(Of Cat).GetEnumerator
        Console.WriteLine("Cat")
        ' Some code.
    End Function

    Public Function GetEnumerator1() As IEnumerator(Of Dog) _
        Implements IEnumerable(Of Dog).GetEnumerator
        Console.WriteLine("Dog")
        ' Some code.
    End Function

    Public Function GetEnumerator2() As IEnumerator _
        Implements IEnumerable.GetEnumerator
        ' Some code.
    End Function
End Class

Sub Main()
    Dim pets As IEnumerable(Of Animal) = New Pets()
    pets.GetEnumerator()
End Sub
```

En este ejemplo no se especifica cómo elige el método `pets.GetEnumerator` entre `Cat` y `Dog`. Esto podría producir problemas en el código.

## <a name="see-also"></a>Consulte también

- [Varianza en interfaces genéricas (Visual Basic)](variance-in-generic-interfaces.md)
- [Usar la varianza para los delegados genéricos Func y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md)
