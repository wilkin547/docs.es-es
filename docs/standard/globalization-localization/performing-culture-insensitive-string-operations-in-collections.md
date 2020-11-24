---
title: Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
ms.openlocfilehash: f0d932dcbb07253e3ea52238a81b416af148cf98
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829783"
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a><span data-ttu-id="d5dbd-102">Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones</span><span class="sxs-lookup"><span data-stu-id="d5dbd-102">Performing Culture-Insensitive String Operations in Collections</span></span>

<span data-ttu-id="d5dbd-103">En el espacio de nombres <xref:System.Collections> hay clases y miembros que proporcionan, de manera predeterminada, el comportamiento que tiene en cuenta la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-103">There are classes and members in the <xref:System.Collections> namespace that provide culture-sensitive behavior by default.</span></span> <span data-ttu-id="d5dbd-104">Los constructores sin parámetros de las clases <xref:System.Collections.CaseInsensitiveComparer> y <xref:System.Collections.CaseInsensitiveHashCodeProvider> inicializan una instancia nueva con la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-104">The parameterless constructors for the <xref:System.Collections.CaseInsensitiveComparer> and <xref:System.Collections.CaseInsensitiveHashCodeProvider> classes initialize a new instance using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d5dbd-105">Todas las sobrecargas del método <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> crean una instancia de la clase <xref:System.Collections.Hashtable> mediante la propiedad `Thread.CurrentCulture` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-105">All overloads of the <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> method create a new instance of the <xref:System.Collections.Hashtable> class using the `Thread.CurrentCulture` property by default.</span></span> <span data-ttu-id="d5dbd-106">Las sobrecargas del método <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> realizan ordenaciones que tienen en cuenta las referencias culturales de manera predeterminada con `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-106">Overloads of the <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> method perform culture-sensitive sorts by default using `Thread.CurrentCulture`.</span></span> <span data-ttu-id="d5dbd-107"><xref:System.Collections.SortedList> puede afectar la ordenación y la búsqueda en `Thread.CurrentCulture` cuando las cadenas se usan como las claves.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-107">Sorting and lookup in a <xref:System.Collections.SortedList> can be affected by `Thread.CurrentCulture` when strings are used as the keys.</span></span> <span data-ttu-id="d5dbd-108">Siga las recomendaciones de uso que se proporcionan en esta sección para obtener resultados que no tienen en cuenta la referencia cultural de estas clases y métodos en el espacio de nombres `Collections`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-108">Follow the usage recommendations provided in this section to obtain culture-insensitive results from these classes and methods in the `Collections` namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="d5dbd-109">Pasar <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> a un método de comparación realiza una comparación que no tiene en cuenta la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-109">Passing <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="d5dbd-110">Si embargo, no provoca una comparación no lingüística, por ejemplo, para las rutas de acceso de archivo, las claves del Registro y las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="d5dbd-111">Tampoco admite las decisiones de seguridad basadas en el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="d5dbd-112">Para una comparación no lingüística o la compatibilidad con las decisiones de seguridad basadas en los resultados, la aplicación debe usar un método de comparación que acepte un valor <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="d5dbd-113">A continuación, la aplicación debe pasar <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-113">The application should then pass <xref:System.StringComparison>.</span></span>

## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a><span data-ttu-id="d5dbd-114">Uso de las clases CaseInsensitiveComparer y CaseInsensitiveHashCodeProvider</span><span class="sxs-lookup"><span data-stu-id="d5dbd-114">Using the CaseInsensitiveComparer and CaseInsensitiveHashCodeProvider Classes</span></span>

<span data-ttu-id="d5dbd-115">Los constructores sin parámetros para `CaseInsensitiveHashCodeProvider` y `CaseInsensitiveComparer` inicializan una instancia nueva de la clase con `Thread.CurrentCulture`, lo que genera un comportamiento que tiene en cuenta las referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-115">The parameterless constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer` initialize a new instance of the class using the `Thread.CurrentCulture`, resulting in culture-sensitive behavior.</span></span> <span data-ttu-id="d5dbd-116">En el ejemplo de código siguiente se muestra el constructor de `Hashtable` que tiene en cuenta las referencias culturales porque usa los constructores sin parámetros para `CaseInsensitiveHashCodeProvider` y `CaseInsensitiveComparer`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-116">The following code example demonstrates the constructor for a `Hashtable` that is culture-sensitive because it uses the parameterless constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer`.</span></span>

```vb
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)
```

```csharp
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);
```

<span data-ttu-id="d5dbd-117">Si desea crear `Hashtable` que no tiene en cuenta las referencias culturales con las clases `CaseInsensitiveComparer` y `CaseInsensitiveHashCodeProvider`, inicialice instancias nuevas de estas clases con los constructores que aceptan un parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-117">If you want to create a culture-insensitive `Hashtable` using the `CaseInsensitiveComparer` and `CaseInsensitiveHashCodeProvider` classes, initialize new instances of these classes using the constructors that accept a `culture` parameter.</span></span> <span data-ttu-id="d5dbd-118">Para el parámetro `culture`, especifique <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-118">For the `culture` parameter, specify <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d5dbd-119">El ejemplo de código siguiente muestra el constructor para un `Hashtable` que no tiene en cuenta las referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-119">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a><span data-ttu-id="d5dbd-120">Uso del método CollectionsUtil.CreateCaseInsensitiveHashTable</span><span class="sxs-lookup"><span data-stu-id="d5dbd-120">Using the CollectionsUtil.CreateCaseInsensitiveHashTable Method</span></span>

<span data-ttu-id="d5dbd-121">El método `CollectionsUtil.CreateCaseInsensitiveHashTable` es un acceso directo para crear una instancia de la clase `Hashtable` que no toma en cuenta las mayúsculas y minúsculas de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-121">The `CollectionsUtil.CreateCaseInsensitiveHashTable` method is a useful shortcut for creating a new instance of the `Hashtable` class that ignores the case of strings.</span></span> <span data-ttu-id="d5dbd-122">Sin embargo, todas las sobrecargas del método `CollectionsUtil.CreateCaseInsensitiveHashTable` tienen en cuenta las referencias culturales porque usan la propiedad `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-122">However, all overloads of the `CollectionsUtil.CreateCaseInsensitiveHashTable` method are culture-sensitive because they use the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="d5dbd-123">No puede crear un `Hashtable` que no tiene en cuenta las referencias culturales con este método.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-123">You cannot create a culture-insensitive `Hashtable` using this method.</span></span> <span data-ttu-id="d5dbd-124">Para crear un `Hashtable` que no tiene en cuenta las referencias culturales, use el constructor `Hashtable` que acepta un parámetro `culture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-124">To create a culture-insensitive `Hashtable`, use the `Hashtable` constructor that accepts a `culture` parameter.</span></span> <span data-ttu-id="d5dbd-125">Para el parámetro `culture`, especifique `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-125">For the `culture` parameter, specify `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="d5dbd-126">El ejemplo de código siguiente muestra el constructor para un `Hashtable` que no tiene en cuenta las referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-126">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>

## <a name="using-the-sortedlist-class"></a><span data-ttu-id="d5dbd-127">Uso de la clase SortedList</span><span class="sxs-lookup"><span data-stu-id="d5dbd-127">Using the SortedList Class</span></span>

<span data-ttu-id="d5dbd-128">`SortedList` representa una colección de pares clave-valor ordenados por claves a los que se accede por clave y por índice.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-128">A `SortedList` represents a collection of key-and-value pairs that are sorted by the keys and are accessible by key and by index.</span></span> <span data-ttu-id="d5dbd-129">Cuando usa `SortedList` donde las cadenas son las claves, la propiedad `Thread.CurrentCulture` puede afectar la ordenación y la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-129">When you use a `SortedList` where strings are the keys, the sorting and lookup can be affected by the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="d5dbd-130">Para obtener el comportamiento que no tiene en cuenta las referencias culturales desde `SortedList`, cree `SortedList` con uno de los constructores que acepta un parámetro `comparer`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-130">To obtain culture-insensitive behavior from a `SortedList`, create a `SortedList` using one of the constructors that accepts a `comparer` parameter.</span></span> <span data-ttu-id="d5dbd-131">El parámetro `comparer` especifica la implementación <xref:System.Collections.IComparer> para usarla al comparar claves.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-131">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing keys.</span></span> <span data-ttu-id="d5dbd-132">Para el parámetro, especifique una clase de comparador personalizada que usa`CultureInfo.InvariantCulture` para comparar claves.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-132">For the parameter, specify a custom comparer class that uses `CultureInfo.InvariantCulture` to compare keys.</span></span> <span data-ttu-id="d5dbd-133">En el ejemplo siguiente se muestra una clase de comparación que no tiene en cuenta las referencias culturales y que puede especificar como el parámetro `comparer` para un constructor `SortedList`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-133">The following example illustrates a custom culture-insensitive comparer class that you can specify as the `comparer` parameter to a `SortedList` constructor.</span></span>

```vb
Imports System.Collections
Imports System.Globalization

Friend Class InvariantComparer
    Implements IComparer
    Private m_compareInfo As CompareInfo
    Friend Shared [Default] As New InvariantComparer()

    Friend Sub New()
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo
    End Sub

    Public Function Compare(a As Object, b As Object) As Integer _
            Implements IComparer.Compare
        Dim sa As String = CType(a, String)
        Dim sb As String = CType(b, String)
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then
            Return m_compareInfo.Compare(sa, sb)
        Else
            Return Comparer.Default.Compare(a, b)
        End If
    End Function
End Class
```

```csharp
using System;
using System.Collections;
using System.Globalization;

internal class InvariantComparer : IComparer
{
    private CompareInfo m_compareInfo;
    internal static readonly InvariantComparer Default = new
        InvariantComparer();

    internal InvariantComparer()
    {
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;
    }

    public int Compare(Object a, Object b)
    {
        String sa = a as String;
        String sb = b as String;
        if (sa != null && sb != null)
            return m_compareInfo.Compare(sa, sb);
        else
            return Comparer.Default.Compare(a,b);
    }
}
```

<span data-ttu-id="d5dbd-134">En general, si usa `SortedList` en las cadenas sin especificar un comparador invariable personalizado, un cambio en `Thread.CurrentCulture` una vez que se rellena la lista puede invalidarla.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-134">In general, if you use a `SortedList` on strings without specifying a custom invariant comparer, a change to `Thread.CurrentCulture` after the list has been populated can invalidate the list.</span></span>

## <a name="using-the-arraylistsort-method"></a><span data-ttu-id="d5dbd-135">Uso del método ArrayList.Sort</span><span class="sxs-lookup"><span data-stu-id="d5dbd-135">Using the ArrayList.Sort Method</span></span>

<span data-ttu-id="d5dbd-136">Las sobrecargas del método `ArrayList.Sort` realizan ordenaciones que tienen en cuenta las referencias culturales de manera predeterminada con la propiedad `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-136">Overloads of the `ArrayList.Sort` method perform culture-sensitive sorts by default using the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="d5dbd-137">Los resultados pueden variar según la referencia cultural debido a criterios de ordenación distintos.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-137">Results can vary by culture due to different sort orders.</span></span> <span data-ttu-id="d5dbd-138">Para eliminar el comportamiento que tiene en cuenta las referencias culturales, use las sobrecargas de este método que aceptan una implementación `IComparer`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-138">To eliminate culture-sensitive behavior, use the overloads of this method that accept an `IComparer` implementation.</span></span> <span data-ttu-id="d5dbd-139">Para el parámetro `comparer`, especifique una clase de comparador invariable personalizada que use `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-139">For the `comparer` parameter, specify a custom invariant comparer class that uses `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="d5dbd-140">En el tema [Uso de la clase SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) se proporciona un ejemplo de una clase de comparador invariable personalizada.</span><span class="sxs-lookup"><span data-stu-id="d5dbd-140">An example of a custom invariant comparer class is provided in the [Using the SortedList Class](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5dbd-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5dbd-141">See also</span></span>

- <xref:System.Collections.CaseInsensitiveComparer>
- <xref:System.Collections.CaseInsensitiveHashCodeProvider>
- <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>
- <xref:System.Collections.SortedList>
- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IComparer>
- [<span data-ttu-id="d5dbd-142">Realizar operaciones de cadenas que no distinguen entre referencias culturales</span><span class="sxs-lookup"><span data-stu-id="d5dbd-142">Performing Culture-Insensitive String Operations</span></span>](performing-culture-insensitive-string-operations.md)
- <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
