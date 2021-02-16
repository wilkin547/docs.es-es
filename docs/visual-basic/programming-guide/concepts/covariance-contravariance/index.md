---
description: 'Más información sobre: covarianza y contravarianza (Visual Basic)'
title: Covarianza y contravarianza
ms.date: 07/20/2015
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
ms.openlocfilehash: 6569b2c6c4790a5fcf53a9991543286ad6c4314c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100485255"
---
# <a name="covariance-and-contravariance-visual-basic"></a><span data-ttu-id="25085-103">Covarianza y contravarianza (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-103">Covariance and Contravariance (Visual Basic)</span></span>

<span data-ttu-id="25085-104">En Visual Basic, la covarianza y la contravarianza habilitan la conversión de referencias implícita de tipos de matriz, tipos de delegado y argumentos de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="25085-104">In Visual Basic, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="25085-105">La covarianza conserva la compatibilidad de asignaciones y la contravarianza la invierte.</span><span class="sxs-lookup"><span data-stu-id="25085-105">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>

<span data-ttu-id="25085-106">El siguiente código muestra la diferencia entre la compatibilidad de asignaciones, la covarianza y la contravarianza.</span><span class="sxs-lookup"><span data-stu-id="25085-106">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>

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

<span data-ttu-id="25085-107">La covarianza de matrices permite la conversión implícita de una matriz de un tipo más derivado a una matriz de un tipo menos derivado.</span><span class="sxs-lookup"><span data-stu-id="25085-107">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="25085-108">Pero esta operación no es segura, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="25085-108">But this operation is not type safe, as shown in the following code example.</span></span>

```vb
Dim array() As Object = New String(10) {}
' The following statement produces a run-time exception.
' array(0) = 10
```

<span data-ttu-id="25085-109">La compatibilidad de la covarianza y la contravarianza con grupos de métodos permite hacer coincidir firmas de método con tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="25085-109">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="25085-110">Esto le permite asignar a los delegados no solo métodos con firmas coincidentes, sino métodos que devuelven tipos más derivados (covarianza) o que aceptan parámetros con tipos menos derivados (contravarianza) que el especificado por el tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="25085-110">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="25085-111">Para obtener más información, vea [Variance in Delegates (Visual Basic)](variance-in-delegates.md) (Varianza en delegados (Visual Basic)) y [Using Variance in Delegates (Visual Basic)](using-variance-in-delegates.md) (Usar varianza en delegados (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="25085-111">For more information, see [Variance in Delegates (Visual Basic)](variance-in-delegates.md) and [Using Variance in Delegates (Visual Basic)](using-variance-in-delegates.md).</span></span>

<span data-ttu-id="25085-112">En el ejemplo de código siguiente, se muestra la compatibilidad de covarianza y contravarianza con grupos de métodos.</span><span class="sxs-lookup"><span data-stu-id="25085-112">The following code example shows covariance and contravariance support for method groups.</span></span>

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

<span data-ttu-id="25085-113">En .NET Framework 4 o posterior, Visual Basic admite la covarianza y la contravarianza en interfaces y delegados genéricos y permite la conversión implícita de parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="25085-113">In .NET Framework 4 or later, Visual Basic supports covariance and contravariance in generic interfaces and delegates and allows for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="25085-114">Para obtener más información, vea [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md) (Varianza en interfaces genéricas (Visual Basic)) y [Variance in Delegates (Visual Basic)](variance-in-delegates.md) (Varianza en delegados (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="25085-114">For more information, see [Variance in Generic Interfaces (Visual Basic)](variance-in-generic-interfaces.md) and [Variance in Delegates (Visual Basic)](variance-in-delegates.md).</span></span>

<span data-ttu-id="25085-115">En el ejemplo de código siguiente, se muestra la conversión implícita de referencias para interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="25085-115">The following code example shows implicit reference conversion for generic interfaces.</span></span>

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

<span data-ttu-id="25085-116">Un delegado o interfaz genéricos se denominan *variante* si sus parámetros genéricos se declaran como covariantes o contravariantes.</span><span class="sxs-lookup"><span data-stu-id="25085-116">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="25085-117">Visual Basic le permite crear sus propias interfaces y delegados variantes.</span><span class="sxs-lookup"><span data-stu-id="25085-117">Visual Basic enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="25085-118">Para obtener más información, vea [Creating Variant Generic Interfaces (Visual Basic)](creating-variant-generic-interfaces.md) (Crear interfaces genéricas variantes (Visual Basic)) y [Variance in Delegates (Visual Basic)](variance-in-delegates.md) (Varianza en delegados (Visual Basic)).</span><span class="sxs-lookup"><span data-stu-id="25085-118">For more information, see [Creating Variant Generic Interfaces (Visual Basic)](creating-variant-generic-interfaces.md) and [Variance in Delegates (Visual Basic)](variance-in-delegates.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="25085-119">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="25085-119">Related Topics</span></span>

|<span data-ttu-id="25085-120">Title</span><span class="sxs-lookup"><span data-stu-id="25085-120">Title</span></span>|<span data-ttu-id="25085-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="25085-121">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="25085-122">Varianza en interfaces genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-122">Variance in Generic Interfaces (Visual Basic)</span></span>](variance-in-generic-interfaces.md)|<span data-ttu-id="25085-123">Describe la covarianza y contravarianza en las interfaces genéricas y proporciona una lista de interfaces genéricas variantes en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="25085-123">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|
|[<span data-ttu-id="25085-124">Crear interfaces genéricas variantes (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-124">Creating Variant Generic Interfaces (Visual Basic)</span></span>](creating-variant-generic-interfaces.md)|<span data-ttu-id="25085-125">Se muestra cómo crear interfaces variantes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="25085-125">Shows how to create custom variant interfaces.</span></span>|
|[<span data-ttu-id="25085-126">Usar la varianza en interfaces para las colecciones genéricas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-126">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="25085-127">Se muestra cómo la compatibilidad de covarianza y contravarianza en las interfaces <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IComparable%601> puede ayudarle a volver a usar el código.</span><span class="sxs-lookup"><span data-stu-id="25085-127">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|
|[<span data-ttu-id="25085-128">Varianza en delegados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-128">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)|<span data-ttu-id="25085-129">Se describe la covarianza y contravarianza en delegados genéricos y no genéricos y se proporciona una lista de delegados genéricos variantes en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="25085-129">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|
|[<span data-ttu-id="25085-130">Usar varianza en delegados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-130">Using Variance in Delegates (Visual Basic)</span></span>](using-variance-in-delegates.md)|<span data-ttu-id="25085-131">Se muestra cómo usar la compatibilidad de covarianza y contravarianza en los delegados no genéricos para que coincidan las firmas de método con los tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="25085-131">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|
|[<span data-ttu-id="25085-132">Usar la varianza para los delegados genéricos Func y Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25085-132">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="25085-133">Se muestra cómo la compatibilidad de covarianza y contravarianza en los delegados `Func` y `Action` puede ayudarle a volver a usar el código.</span><span class="sxs-lookup"><span data-stu-id="25085-133">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
