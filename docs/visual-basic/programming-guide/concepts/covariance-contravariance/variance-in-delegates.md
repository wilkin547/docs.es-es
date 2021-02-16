---
description: 'Más información sobre: varianza en delegados (Visual Basic)'
title: Varianza en delegados
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: d47f05a5ce3f3e59223f1f37ab09fb8a21e6e7ba
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100458971"
---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="ed806-103">Varianza en delegados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed806-103">Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="ed806-104">.NET Framework 3,5 presentó la compatibilidad de la varianza con las signaturas de método coincidentes con tipos de delegado en todos los delegados en C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ed806-104">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="ed806-105">Esto significa que puede asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="ed806-105">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="ed806-106">Esto incluye delegados genéricos y no genéricos.</span><span class="sxs-lookup"><span data-stu-id="ed806-106">This includes both generic and non-generic delegates.</span></span>

<span data-ttu-id="ed806-107">Por ejemplo, consideremos el siguiente código, que tiene dos clases y dos delegados: genéricos y no genéricos.</span><span class="sxs-lookup"><span data-stu-id="ed806-107">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

<span data-ttu-id="ed806-108">Al crear delegados de los tipos `SampleDelegate` o `SampleDelegate(Of A, R)`, puede asignar uno de los métodos siguientes a dichos delegados.</span><span class="sxs-lookup"><span data-stu-id="ed806-108">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>

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

<span data-ttu-id="ed806-109">En el ejemplo de código siguiente se ilustra la conversión implícita entre la firma del método y el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="ed806-109">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>

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

<span data-ttu-id="ed806-110">Para obtener más ejemplos, vea [usar la varianza en delegados (Visual Basic)](using-variance-in-delegates.md) y [usar la varianza para los delegados genéricos FUNC y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="ed806-110">For more examples, see [Using Variance in Delegates (Visual Basic)](using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span></span>

## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="ed806-111">Varianza en parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="ed806-111">Variance in Generic Type Parameters</span></span>

<span data-ttu-id="ed806-112">En .NET Framework 4 y versiones posteriores, puede habilitar la conversión implícita entre los delegados, de modo que los delegados genéricos que tengan distintos tipos especificados por los parámetros de tipo genérico se puedan asignar entre sí, si los tipos se heredan entre sí según sea necesario para la varianza.</span><span class="sxs-lookup"><span data-stu-id="ed806-112">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>

<span data-ttu-id="ed806-113">Para habilitar la conversión implícita, debe declarar explícitamente parámetros genéricos en un delegado como covariante o contravariante mediante la palabra clave `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="ed806-113">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>

<span data-ttu-id="ed806-114">En el ejemplo de código siguiente se muestra cómo se crea un delegado que tiene un parámetro de tipo genérico covariante.</span><span class="sxs-lookup"><span data-stu-id="ed806-114">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>

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

<span data-ttu-id="ed806-115">Si usa solo la compatibilidad con la varianza para hacer coincidir firmas de método con tipos de delegados y no usa las palabras clave `in` y `out`, es posible que en algunas ocasiones pueda crear instancias de delegados con métodos o expresiones lambda idénticos, pero no pueda asignar un delegado a otro.</span><span class="sxs-lookup"><span data-stu-id="ed806-115">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>

<span data-ttu-id="ed806-116">En el siguiente ejemplo de código, `SampleGenericDelegate(Of String)` no se puede convertir explícitamente en `SampleGenericDelegate(Of Object)` , aunque `String` hereda `Object` .</span><span class="sxs-lookup"><span data-stu-id="ed806-116">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="ed806-117">Para solucionar este problema, marque el parámetro genérico `T` con la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="ed806-117">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>

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

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="ed806-118">Delegados genéricos con parámetros de tipo variante en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ed806-118">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>

<span data-ttu-id="ed806-119">En .NET Framework 4 se presentó por primera vez la compatibilidad con la varianza para los parámetros de tipo genérico en varios delegados genéricos existentes:</span><span class="sxs-lookup"><span data-stu-id="ed806-119">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>

- <span data-ttu-id="ed806-120">`Action` delega del espacio de nombres <xref:System>, por ejemplo, <xref:System.Action%601> y <xref:System.Action%602></span><span class="sxs-lookup"><span data-stu-id="ed806-120">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>

- <span data-ttu-id="ed806-121">`Func` delega del espacio de nombres <xref:System>, por ejemplo, <xref:System.Func%601> y <xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="ed806-121">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>

- <span data-ttu-id="ed806-122">Delegado <xref:System.Predicate%601>.</span><span class="sxs-lookup"><span data-stu-id="ed806-122">The <xref:System.Predicate%601> delegate</span></span>

- <span data-ttu-id="ed806-123">Delegado <xref:System.Comparison%601>.</span><span class="sxs-lookup"><span data-stu-id="ed806-123">The <xref:System.Comparison%601> delegate</span></span>

- <span data-ttu-id="ed806-124">Delegado <xref:System.Converter%602>.</span><span class="sxs-lookup"><span data-stu-id="ed806-124">The <xref:System.Converter%602> delegate</span></span>

<span data-ttu-id="ed806-125">Para obtener más información y ejemplos, vea [usar la varianza para los delegados genéricos FUNC y Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="ed806-125">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).</span></span>

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="ed806-126">Declarar parámetros de tipo variante en delegados genéricos</span><span class="sxs-lookup"><span data-stu-id="ed806-126">Declaring Variant Type Parameters in Generic Delegates</span></span>

<span data-ttu-id="ed806-127">Si un delegado genérico tiene parámetros de tipo genérico covariante o contravariante, se puede hacer referencia a él como un *delegado genérico variante*.</span><span class="sxs-lookup"><span data-stu-id="ed806-127">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>

<span data-ttu-id="ed806-128">Puede declarar un parámetro de tipo genérico covariante en un delegado genérico mediante la palabra clave `out`.</span><span class="sxs-lookup"><span data-stu-id="ed806-128">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="ed806-129">El tipo covariante puede usarse solo como un tipo de valor devuelto de método, y no como un tipo de argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="ed806-129">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="ed806-130">En el siguiente ejemplo de código se muestra cómo declarar un delegado genérico covariante.</span><span class="sxs-lookup"><span data-stu-id="ed806-130">The following code example shows how to declare a covariant generic delegate.</span></span>

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

<span data-ttu-id="ed806-131">Puede declarar un parámetro de tipo genérico contravariante en un delegado genérico mediante la palabra clave `in`.</span><span class="sxs-lookup"><span data-stu-id="ed806-131">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="ed806-132">El tipo contravariante puede usarse solo como un tipo de argumentos de método, y no como un tipo de valor devuelto de método.</span><span class="sxs-lookup"><span data-stu-id="ed806-132">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="ed806-133">En el siguiente ejemplo de código se muestra cómo declarar un delegado genérico contravariante.</span><span class="sxs-lookup"><span data-stu-id="ed806-133">The following code example shows how to declare a contravariant generic delegate.</span></span>

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> <span data-ttu-id="ed806-134">`ByRef` los parámetros de Visual Basic no se pueden marcar como Variant.</span><span class="sxs-lookup"><span data-stu-id="ed806-134">`ByRef` parameters in Visual Basic can't be marked as variant.</span></span>

<span data-ttu-id="ed806-135">También es posible admitir la varianza y la covarianza en el mismo delegado, pero para parámetros de tipo diferentes.</span><span class="sxs-lookup"><span data-stu-id="ed806-135">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="ed806-136">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed806-136">This is shown in the following example.</span></span>

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="ed806-137">Crear instancias de delegados genéricos variantes e invocarlos</span><span class="sxs-lookup"><span data-stu-id="ed806-137">Instantiating and Invoking Variant Generic Delegates</span></span>

<span data-ttu-id="ed806-138">Puede crear instancias de delegados variantes e invocarlos del mismo modo que crea instancias de delegados invariables y los invoca.</span><span class="sxs-lookup"><span data-stu-id="ed806-138">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="ed806-139">En el ejemplo siguiente, se crea una instancia del delegado mediante una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="ed806-139">In the following example, the delegate is instantiated by a lambda expression.</span></span>

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="ed806-140">Combinar delegados genéricos variantes</span><span class="sxs-lookup"><span data-stu-id="ed806-140">Combining Variant Generic Delegates</span></span>

<span data-ttu-id="ed806-141">No debe combinar delegados variantes.</span><span class="sxs-lookup"><span data-stu-id="ed806-141">You should not combine variant delegates.</span></span> <span data-ttu-id="ed806-142">El método <xref:System.Delegate.Combine%2A> no admite la conversión de delegados variantes y espera que los delegados sean exactamente del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="ed806-142">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="ed806-143">Esto puede conducir a una excepción en tiempo de ejecución cuando se combinan delegados mediante el <xref:System.Delegate.Combine%2A> método (en c# y Visual Basic) o mediante el `+` operador (en c#), tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed806-143">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="ed806-144">Varianza en parámetros de tipo genérico para los tipos de referencia y valor</span><span class="sxs-lookup"><span data-stu-id="ed806-144">Variance in Generic Type Parameters for Value and Reference Types</span></span>

<span data-ttu-id="ed806-145">La varianza para parámetros de tipo genérico solo es compatible con tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="ed806-145">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="ed806-146">Por ejemplo, `DVariant(Of Int)` no se puede convertir implícitamente en `DVariant(Of Object)` o `DVariant(Of Long)` , porque Integer es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ed806-146">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>

<span data-ttu-id="ed806-147">En el ejemplo siguiente se muestra que la varianza en parámetros de tipo genérico no se admite para tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="ed806-147">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>

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

## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="ed806-148">Conversión de delegado flexible en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed806-148">Relaxed Delegate Conversion in Visual Basic</span></span>

<span data-ttu-id="ed806-149">La conversión de delegado relajado permite más flexibilidad en la coincidencia de firmas de método con tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="ed806-149">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="ed806-150">Por ejemplo, le permite omitir las especificaciones de parámetro y omitir los valores devueltos de función al asignar un método a un delegado.</span><span class="sxs-lookup"><span data-stu-id="ed806-150">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="ed806-151">Para obtener más información, vea [conversión de delegado relajado](../../language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="ed806-151">For more information, see [Relaxed Delegate Conversion](../../language-features/delegates/relaxed-delegate-conversion.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed806-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed806-152">See also</span></span>

- [<span data-ttu-id="ed806-153">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ed806-153">Generics</span></span>](../../../../standard/generics/index.md)
- [<span data-ttu-id="ed806-154">Usar la varianza para los delegados genéricos Func y Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed806-154">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
