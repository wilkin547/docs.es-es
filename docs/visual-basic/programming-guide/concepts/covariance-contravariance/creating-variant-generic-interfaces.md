---
title: "Crear Interfaces genéricas variantes (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 324e2a906e84950aa9019bbf68a524458492646e
ms.lasthandoff: 03/13/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Crear Interfaces genéricas variantes (Visual Basic)
Puede declarar los parámetros de tipo genérico en interfaces como covariante o contravariante. *Covarianza* permite que los métodos de interfaz tengan tipos más derivados devueltos al definido por los parámetros de tipo genérico. *Contravarianza* permite que los métodos de interfaz tengan tipos de argumento menos derivados que el especificado por los parámetros genéricos. Una interfaz genérica con covariantes o contravariantes los parámetros de tipo genérico se llama *variante*.  
  
> [!NOTE]
>  .NET framework 4 introdujo la compatibilidad con la varianza para varias interfaces genéricas existentes. La lista de las interfaces variantes de .NET Framework, vea [varianza en Interfaces genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="declaring-variant-generic-interfaces"></a>Declarar Interfaces genéricas variantes  
 Puede declarar interfaces genéricas variantes mediante la `in` y `out` palabras clave para los parámetros de tipo genérico.  
  
> [!IMPORTANT]
>  `ByRef`en Visual Basic no pueden ser variant. También los tipos de valor no admiten la varianza.  
  
 Puede declarar un parámetro de tipo genérico covariante mediante el `out` (palabra clave). El tipo covariante debe cumplir las condiciones siguientes:  
  
-   El tipo se utiliza únicamente como un tipo de valor devuelto de los métodos de interfaz y no se utiliza como un tipo de argumentos de método. Esto se ilustra en el ejemplo siguiente, en el que el tipo `R` se declara como covariante.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     Hay una excepción para esta regla. Si tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo como un parámetro de tipo genérico para el delegado. Esto se ilustra en el tipo `R` en el ejemplo siguiente. Para obtener más información, consulte [varianza en delegados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Using Variance for Func y Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   El tipo no se usa como restricción genérica para los métodos de interfaz. Esto se muestra en el código siguiente.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 Puede declarar una contravariante del parámetro de tipo genérico mediante la `in` (palabra clave). El tipo contravariante puede usarse solo como un tipo de argumentos de método y no como un tipo de valor devuelto de los métodos de interfaz. El tipo contravariante puede utilizarse también para restricciones genéricas. El código siguiente muestra cómo declarar una interfaz contravariante y usar una restricción genérica para uno de sus métodos.  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 También es posible admitir la covarianza y contravarianza en la misma interfaz, pero para distintos parámetros de tipo, como se muestra en el ejemplo de código siguiente.  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 En Visual Basic, no puede declarar eventos en interfaces variantes sin especificar el tipo de delegado. Además, una interfaz variante no puede tener anidadas clases, enumeraciones o estructuras, pero pueden interfaces anidadas. Esto se muestra en el código siguiente.  
  
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
  
## <a name="implementing-variant-generic-interfaces"></a>Implementar Interfaces genéricas variantes  
 Implementar interfaces genéricas variantes en clases mediante la misma sintaxis que se utiliza para las interfaces invariables. En el ejemplo de código siguiente se muestra cómo implementar una interfaz covariante en una clase genérica.  
  
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
  
## <a name="extending-variant-generic-interfaces"></a>Extender Interfaces genéricas variantes  
 Al extender una interfaz genérica variante, tiene que usar el `in` y `out` palabras clave para especificar de forma explícita si la interfaz derivada admite la varianza. El compilador no infiere la varianza de la interfaz que se va a extender. Por ejemplo, considere las siguientes interfaces.  
  
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
  
 En el `Invariant(Of T)` de la interfaz, el parámetro de tipo genérico `T` es invariable, mientras que en `IExtCovariant (Of Out T)`el parámetro de tipo es covariante, si bien ambas interfaces extienden la misma interfaz. La misma regla se aplica a los parámetros de tipo genérico contravariante.  
  
 Puede crear una interfaz que extiende la interfaz donde el parámetro de tipo genérico `T` es covariante y el parámetro de tipo genérico de la interfaz donde es contravariante si en la que se extiende la interfaz `T` es invariable. Esto se muestra en el ejemplo de código siguiente.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 Sin embargo, si un parámetro de tipo genérico `T` es declarada covariante en una interfaz, no puede declarar como contravariante en la interfaz extensible, o viceversa. Esto se muestra en el ejemplo de código siguiente.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a>Evitar la ambigüedad  
 Al implementar interfaces genéricas variantes, la varianza a veces puede provocar ambigüedad. Éste debería evitarse.  
  
 Por ejemplo, si se implementa explícitamente la misma interfaz genérica variante con parámetros de tipo genérico diferente en una clase, puede crear ambigüedad. El compilador no genera un error en este caso, pero no se especifica la implementación de interfaz se elegirá en tiempo de ejecución. Esto podría provocar errores imperceptibles en el código. Considere el ejemplo de código siguiente.  
  
> [!NOTE]
>  Con `Option Strict Off`, Visual Basic genera una advertencia de compilador cuando hay una implementación de interfaz ambigua. Con `Option Strict On`, Visual Basic genera un error del compilador.  
  
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
  
 En este ejemplo, se especifica cómo el `pets.GetEnumerator` método elige entre `Cat` y `Dog`. Esto podría producir problemas en el código.  
  
## <a name="see-also"></a>Vea también  
 [Varianza en Interfaces genéricas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)   
 [Usar la varianza para Func y Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
