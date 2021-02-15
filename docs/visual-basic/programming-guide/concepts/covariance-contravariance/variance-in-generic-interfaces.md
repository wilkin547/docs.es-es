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
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="77660-103">Varianza en interfaces genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77660-103">Variance in Generic Interfaces (Visual Basic)</span></span>

<span data-ttu-id="77660-104">En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes.</span><span class="sxs-lookup"><span data-stu-id="77660-104">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="77660-105">La compatibilidad con la varianza permite la conversión implícita de clases que implementan estas interfaces.</span><span class="sxs-lookup"><span data-stu-id="77660-105">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="77660-106">Las interfaces siguientes ahora son variantes:</span><span class="sxs-lookup"><span data-stu-id="77660-106">The following interfaces are now variant:</span></span>

- <span data-ttu-id="77660-107"><xref:System.Collections.Generic.IEnumerable%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="77660-107"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>

- <span data-ttu-id="77660-108"><xref:System.Collections.Generic.IEnumerator%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="77660-108"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>

- <span data-ttu-id="77660-109"><xref:System.Linq.IQueryable%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="77660-109"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>

- <span data-ttu-id="77660-110"><xref:System.Linq.IGrouping%602> (`TKey` y `TElement` son covariantes)</span><span class="sxs-lookup"><span data-stu-id="77660-110"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>

- <span data-ttu-id="77660-111"><xref:System.Collections.Generic.IComparer%601> (T es contravariante)</span><span class="sxs-lookup"><span data-stu-id="77660-111"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="77660-112"><xref:System.Collections.Generic.IEqualityComparer%601> (T es contravariante)</span><span class="sxs-lookup"><span data-stu-id="77660-112"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="77660-113"><xref:System.IComparable%601> (T es contravariante)</span><span class="sxs-lookup"><span data-stu-id="77660-113"><xref:System.IComparable%601> (T is contravariant)</span></span>

<span data-ttu-id="77660-114">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que los que se definen en los parámetros de tipo genérico de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="77660-114">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="77660-115">Para ilustrar la característica de la covarianza, considere estas interfaces genéricas: `IEnumerable(Of Object)` y `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="77660-115">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="77660-116">La interfaz `IEnumerable(Of String)` no hereda la interfaz `IEnumerable(Of Object)`.</span><span class="sxs-lookup"><span data-stu-id="77660-116">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="77660-117">En cambio, el tipo `String` hereda el tipo `Object`, y en algunos casos puede que quiera asignar objetos de estas interfaces entre sí.</span><span class="sxs-lookup"><span data-stu-id="77660-117">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="77660-118">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="77660-118">This is shown in the following code example.</span></span>

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

<span data-ttu-id="77660-119">En versiones anteriores del .NET Framework, este código produce un error de compilación en Visual Basic con `Option Strict On` .</span><span class="sxs-lookup"><span data-stu-id="77660-119">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="77660-120">Pero ahora puede usar `strings` en lugar de `objects`, como se muestra en el ejemplo anterior, porque la interfaz <xref:System.Collections.Generic.IEnumerable%601> es covariante.</span><span class="sxs-lookup"><span data-stu-id="77660-120">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="77660-121">La contravarianza permite que un método tenga tipos de argumento menos derivados que los que se especifican en el parámetro genérico de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="77660-121">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="77660-122">Para ilustrar la contravarianza, se presupone que ha creado una clase `BaseComparer` para comparar instancias de la clase `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="77660-122">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="77660-123">La clase `BaseComparer` implementa la interfaz `IEqualityComparer(Of BaseClass)`.</span><span class="sxs-lookup"><span data-stu-id="77660-123">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="77660-124">Como la interfaz <xref:System.Collections.Generic.IEqualityComparer%601> ahora es contravariante, puede usar `BaseComparer` para comparar instancias de clases que heredan la clase `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="77660-124">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="77660-125">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="77660-125">This is shown in the following code example.</span></span>

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

<span data-ttu-id="77660-126">Para obtener más ejemplos, vea [usar la varianza en interfaces para colecciones genéricas (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="77660-126">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="77660-127">La varianza para interfaces genéricas solo es compatible con tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="77660-127">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="77660-128">Los tipos de valor no admiten la varianza.</span><span class="sxs-lookup"><span data-stu-id="77660-128">Value types do not support variance.</span></span> <span data-ttu-id="77660-129">Por ejemplo, `IEnumerable(Of Integer)` no puede convertirse implícitamente en `IEnumerable(Of Object)`, porque los enteros se representan mediante un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="77660-129">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>

```vb
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)
' The following statement generates a compiler error
' with Option Strict On, because Integer is a value type.
' Dim objects As IEnumerable(Of Object) = integers
```

<span data-ttu-id="77660-130">También es importante recordar que las clases que implementan las interfaces variantes siguen siendo invariables.</span><span class="sxs-lookup"><span data-stu-id="77660-130">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="77660-131">Por ejemplo, aunque <xref:System.Collections.Generic.List%601> implementa la interfaz covariante <xref:System.Collections.Generic.IEnumerable%601>, no puede convertir `List(Of Object)` en `List(Of String)` implícitamente.</span><span class="sxs-lookup"><span data-stu-id="77660-131">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="77660-132">Esto se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="77660-132">This is illustrated in the following code example.</span></span>

```vb
' The following statement generates a compiler error
' because classes are invariant.
' Dim list As List(Of Object) = New List(Of String)

' You can use the interface object instead.
Dim listObjects As IEnumerable(Of Object) = New List(Of String)
```

## <a name="see-also"></a><span data-ttu-id="77660-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="77660-133">See also</span></span>

- [<span data-ttu-id="77660-134">Usar la varianza en interfaces para las colecciones genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77660-134">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="77660-135">Crear interfaces genéricas variantes (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77660-135">Creating Variant Generic Interfaces (Visual Basic)</span></span>](creating-variant-generic-interfaces.md)
- [<span data-ttu-id="77660-136">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="77660-136">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="77660-137">Varianza en delegados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77660-137">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)
