---
title: Varianza en interfaces genéricas (C#)
ms.date: 06/06/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: ea5d3d35bc9ee438263707efd16829b6217a1968
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241336"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="f27de-102">Varianza en interfaces genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="f27de-102">Variance in Generic Interfaces (C#)</span></span>

<span data-ttu-id="f27de-103">En .NET Framework 4 se ha presentado la compatibilidad con la varianza para varias interfaces genéricas existentes.</span><span class="sxs-lookup"><span data-stu-id="f27de-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="f27de-104">La compatibilidad con la varianza permite la conversión implícita de clases que implementan estas interfaces.</span><span class="sxs-lookup"><span data-stu-id="f27de-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span>

<span data-ttu-id="f27de-105">A partir de .NET Framework 4, las siguientes interfaces son variantes:</span><span class="sxs-lookup"><span data-stu-id="f27de-105">Starting with .NET Framework 4, the following interfaces are variant:</span></span>

- <span data-ttu-id="f27de-106"><xref:System.Collections.Generic.IEnumerable%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>

- <span data-ttu-id="f27de-107"><xref:System.Collections.Generic.IEnumerator%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>

- <span data-ttu-id="f27de-108"><xref:System.Linq.IQueryable%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>

- <span data-ttu-id="f27de-109"><xref:System.Linq.IGrouping%602> (`TKey` y `TElement` son covariantes)</span><span class="sxs-lookup"><span data-stu-id="f27de-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>

- <span data-ttu-id="f27de-110"><xref:System.Collections.Generic.IComparer%601> (T es contravariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="f27de-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T es contravariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="f27de-112"><xref:System.IComparable%601> (T es contravariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-112"><xref:System.IComparable%601> (T is contravariant)</span></span>

<span data-ttu-id="f27de-113">A partir de .NET Framework 4.5, las siguientes interfaces son variantes:</span><span class="sxs-lookup"><span data-stu-id="f27de-113">Starting with .NET Framework 4.5, the following interfaces are variant:</span></span>

- <span data-ttu-id="f27de-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T is covariant)</span></span>

- <span data-ttu-id="f27de-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T es covariante)</span><span class="sxs-lookup"><span data-stu-id="f27de-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T is covariant)</span></span>

<span data-ttu-id="f27de-116">La covarianza permite que un método tenga un tipo de valor devuelto más derivado que los que se definen en los parámetros de tipo genérico de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f27de-116">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="f27de-117">Para ilustrar la característica de la covarianza, considere estas interfaces genéricas: `IEnumerable<Object>` y `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="f27de-117">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="f27de-118">La interfaz `IEnumerable<String>` no hereda la interfaz `IEnumerable<Object>`.</span><span class="sxs-lookup"><span data-stu-id="f27de-118">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="f27de-119">En cambio, el tipo `String` hereda el tipo `Object`, y en algunos casos puede que quiera asignar objetos de estas interfaces entre sí.</span><span class="sxs-lookup"><span data-stu-id="f27de-119">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="f27de-120">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f27de-120">This is shown in the following code example.</span></span>

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

<span data-ttu-id="f27de-121">En versiones anteriores de .NET Framework, este código provoca un error de compilación en C# y, si `Option Strict` está activado, en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f27de-121">In earlier versions of .NET Framework, this code causes a compilation error in C# and, if `Option Strict` is on, in Visual Basic.</span></span> <span data-ttu-id="f27de-122">Pero ahora puede usar `strings` en lugar de `objects`, como se muestra en el ejemplo anterior, porque la interfaz <xref:System.Collections.Generic.IEnumerable%601> es covariante.</span><span class="sxs-lookup"><span data-stu-id="f27de-122">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="f27de-123">La contravarianza permite que un método tenga tipos de argumento menos derivados que los que se especifican en el parámetro genérico de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="f27de-123">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="f27de-124">Para ilustrar la contravarianza, se presupone que ha creado una clase `BaseComparer` para comparar instancias de la clase `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="f27de-124">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="f27de-125">La clase `BaseComparer` implementa la interfaz `IEqualityComparer<BaseClass>`.</span><span class="sxs-lookup"><span data-stu-id="f27de-125">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="f27de-126">Como la interfaz <xref:System.Collections.Generic.IEqualityComparer%601> ahora es contravariante, puede usar `BaseComparer` para comparar instancias de clases que heredan la clase `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="f27de-126">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="f27de-127">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f27de-127">This is shown in the following code example.</span></span>

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

<span data-ttu-id="f27de-128">Para obtener más ejemplos, vea [Usar la varianza en interfaces para las colecciones genéricas (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="f27de-128">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="f27de-129">La varianza para interfaces genéricas solo es compatible con tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="f27de-129">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="f27de-130">Los tipos de valor no admiten la varianza.</span><span class="sxs-lookup"><span data-stu-id="f27de-130">Value types do not support variance.</span></span> <span data-ttu-id="f27de-131">Por ejemplo, `IEnumerable<int>` no puede convertirse implícitamente en `IEnumerable<object>`, porque los enteros se representan mediante un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="f27de-131">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

<span data-ttu-id="f27de-132">También es importante recordar que las clases que implementan las interfaces variantes siguen siendo invariables.</span><span class="sxs-lookup"><span data-stu-id="f27de-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="f27de-133">Por ejemplo, aunque <xref:System.Collections.Generic.List%601> implementa la interfaz covariante <xref:System.Collections.Generic.IEnumerable%601>, no puede convertir `List<String>` en `List<Object>` implícitamente.</span><span class="sxs-lookup"><span data-stu-id="f27de-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<String>` to `List<Object>`.</span></span> <span data-ttu-id="f27de-134">Esto se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f27de-134">This is illustrated in the following code example.</span></span>

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a><span data-ttu-id="f27de-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="f27de-135">See also</span></span>

- [<span data-ttu-id="f27de-136">Usar la varianza en interfaces para las colecciones genéricas (C#)</span><span class="sxs-lookup"><span data-stu-id="f27de-136">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="f27de-137">Crear interfaces genéricas variantes (C#)</span><span class="sxs-lookup"><span data-stu-id="f27de-137">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)
- [<span data-ttu-id="f27de-138">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="f27de-138">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="f27de-139">Varianza en delegados (C#)</span><span class="sxs-lookup"><span data-stu-id="f27de-139">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
