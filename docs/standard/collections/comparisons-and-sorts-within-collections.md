---
title: Comparaciones y ordenaciones en colecciones
ms.date: 04/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data, collections
- IComparable.CompareTo method
- Collections classes
- Equals method
- collections [.NET Framework], comparisons
ms.assetid: 5e4d3b45-97f0-423c-a65f-c492ed40e73b
ms.openlocfilehash: cb9dd3e8af570251b8bcd2e450e686ad69ab78c4
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287983"
---
# <a name="comparisons-and-sorts-within-collections"></a><span data-ttu-id="6a664-102">Comparaciones y ordenaciones en colecciones</span><span class="sxs-lookup"><span data-stu-id="6a664-102">Comparisons and sorts within collections</span></span>

<span data-ttu-id="6a664-103">Las clases <xref:System.Collections> realizan comparaciones en casi todos los procesos implicados en la administración de colecciones, bien al buscar el elemento que se va a quitar, bien al devolver el valor de un par de clave y valor.</span><span class="sxs-lookup"><span data-stu-id="6a664-103">The <xref:System.Collections> classes perform comparisons in almost all the processes involved in managing collections, whether searching for the element to remove or returning the value of a key-and-value pair.</span></span>

<span data-ttu-id="6a664-104">Normalmente, las colecciones usan un comparador de igualdad o un comparador de orden.</span><span class="sxs-lookup"><span data-stu-id="6a664-104">Collections typically utilize an equality comparer and/or an ordering comparer.</span></span> <span data-ttu-id="6a664-105">En las comparaciones se usan dos constructores.</span><span class="sxs-lookup"><span data-stu-id="6a664-105">Two constructs are used for comparisons.</span></span>

<a name="BKMK_Checkingforequality"></a>
## <a name="check-for-equality"></a><span data-ttu-id="6a664-106">Comprobación de la igualdad</span><span class="sxs-lookup"><span data-stu-id="6a664-106">Check for equality</span></span>

<span data-ttu-id="6a664-107">Los métodos como `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>y `Remove` utilizan un comparador de igualdad para los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="6a664-107">Methods such as `Contains`, <xref:System.Collections.IList.IndexOf%2A>, <xref:System.Collections.Generic.List%601.LastIndexOf%2A>, and `Remove` use an equality comparer for the collection elements.</span></span> <span data-ttu-id="6a664-108">Si la colección es genérica, se compara la igualdad de los elementos según las siguientes directrices:</span><span class="sxs-lookup"><span data-stu-id="6a664-108">If the collection is generic, then items are compared for equality according to the following guidelines:</span></span>

- <span data-ttu-id="6a664-109">Si el tipo T implementa la interfaz genérica <xref:System.IEquatable%601> , el comparador de igualdad es el método <xref:System.IEquatable%601.Equals%2A> de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a664-109">If type T implements the <xref:System.IEquatable%601> generic interface, then the equality comparer is the <xref:System.IEquatable%601.Equals%2A> method of that interface.</span></span>

- <span data-ttu-id="6a664-110">Si el tipo T no implementa <xref:System.IEquatable%601>, se utiliza <xref:System.Object.Equals%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6a664-110">If type T does not implement <xref:System.IEquatable%601>, <xref:System.Object.Equals%2A?displayProperty=nameWithType> is used.</span></span>

<span data-ttu-id="6a664-111">Además, algunas sobrecargas de constructores para colecciones de diccionario aceptan una implementación de <xref:System.Collections.Generic.IEqualityComparer%601>, que se utiliza para comparar la igualdad de claves.</span><span class="sxs-lookup"><span data-stu-id="6a664-111">In addition, some constructor overloads for dictionary collections accept an <xref:System.Collections.Generic.IEqualityComparer%601> implementation, which is used to compare keys for equality.</span></span> <span data-ttu-id="6a664-112">Para ver un ejemplo, consulte el constructor <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> .</span><span class="sxs-lookup"><span data-stu-id="6a664-112">For an example, see the <xref:System.Collections.Generic.Dictionary%602.%23ctor%2A> constructor.</span></span>

<a name="BKMK_Determiningsortorder"></a>
## <a name="determine-sort-order"></a><span data-ttu-id="6a664-113">Determinación del criterio de ordenación</span><span class="sxs-lookup"><span data-stu-id="6a664-113">Determine sort order</span></span>

<span data-ttu-id="6a664-114">Los métodos como `BinarySearch` y `Sort` utilizan un comparador de orden para los elementos de la colección.</span><span class="sxs-lookup"><span data-stu-id="6a664-114">Methods such as `BinarySearch` and `Sort` use an ordering comparer for the collection elements.</span></span> <span data-ttu-id="6a664-115">Las comparaciones pueden ser entre elementos de la colección o entre un elemento y un valor especificado.</span><span class="sxs-lookup"><span data-stu-id="6a664-115">The comparisons can be between elements of the collection, or between an element and a specified value.</span></span> <span data-ttu-id="6a664-116">Para comparar objetos, existe el concepto de un `default comparer` y un `explicit comparer`.</span><span class="sxs-lookup"><span data-stu-id="6a664-116">For comparing objects, there is the concept of a `default comparer` and an `explicit comparer`.</span></span>

<span data-ttu-id="6a664-117">El comparador predeterminado se basa en al menos uno de los objetos que se comparan para implementar la interfaz **IComparable** .</span><span class="sxs-lookup"><span data-stu-id="6a664-117">The default comparer relies on at least one of the objects being compared to implement the **IComparable** interface.</span></span> <span data-ttu-id="6a664-118">Una práctica recomendada es implementar **IComparable** en todas las clases que se utilizan como valores en una colección de lista o como claves en una colección de diccionarios.</span><span class="sxs-lookup"><span data-stu-id="6a664-118">It is a good practice to implement **IComparable** on all classes are used as values in a list collection or as keys in a dictionary collection.</span></span> <span data-ttu-id="6a664-119">Para una colección genérica, la comparación de igualdad se determina según lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a664-119">For a generic collection, equality comparison is determined according to the following:</span></span>

- <span data-ttu-id="6a664-120">Si el tipo T implementa la interfaz genérica <xref:System.IComparable%601?displayProperty=nameWithType> , el comparador predeterminado es el método <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a664-120">If type T implements the <xref:System.IComparable%601?displayProperty=nameWithType> generic interface, then the default comparer is the <xref:System.IComparable%601.CompareTo%28%600%29?displayProperty=nameWithType> method of that interface</span></span>

- <span data-ttu-id="6a664-121">Si el tipo T implementa la interfaz no genérica <xref:System.IComparable?displayProperty=nameWithType> , el comparador predeterminado es el método <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> de dicha interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a664-121">If type T implements the non-generic <xref:System.IComparable?displayProperty=nameWithType> interface, then the default comparer is the <xref:System.IComparable.CompareTo%28System.Object%29?displayProperty=nameWithType> method of that interface.</span></span>

- <span data-ttu-id="6a664-122">Si el tipo T no implementa ninguna de estas interfaces, no hay ningún comparador predeterminado y debe proporcionarse explícitamente un delegado de comparación o comparador.</span><span class="sxs-lookup"><span data-stu-id="6a664-122">If type T doesn't implement either interface, then there is no default comparer, and a comparer or comparison delegate must be provided explicitly.</span></span>

<span data-ttu-id="6a664-123">Para proporcionar comparaciones explícitas, algunos métodos aceptan una implementación de **IComparer** como parámetro.</span><span class="sxs-lookup"><span data-stu-id="6a664-123">To provide explicit comparisons, some methods accept an **IComparer** implementation as a parameter.</span></span> <span data-ttu-id="6a664-124">Por ejemplo, el método <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> acepta una implementación de <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6a664-124">For example, the <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> method accepts an <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> implementation.</span></span>

<span data-ttu-id="6a664-125">La configuración de la referencia cultural actual del sistema puede afectar a las comparaciones y ordenaciones de una colección.</span><span class="sxs-lookup"><span data-stu-id="6a664-125">The current culture setting of the system can affect the comparisons and sorts within a collection.</span></span> <span data-ttu-id="6a664-126">De forma predeterminada, las comparaciones y ordenaciones de las clases **colecciones** tienen en cuenta la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="6a664-126">By default, the comparisons and sorts in the **Collections** classes are culture-sensitive.</span></span> <span data-ttu-id="6a664-127">Para omitir la configuración de referencia cultural y así obtener resultados de comparación y ordenación coherentes, utilice <xref:System.Globalization.CultureInfo.InvariantCulture%2A> con sobrecargas de miembros que acepten un <xref:System.Globalization.CultureInfo>.</span><span class="sxs-lookup"><span data-stu-id="6a664-127">To ignore the culture setting and therefore obtain consistent comparison and sorting results, use the <xref:System.Globalization.CultureInfo.InvariantCulture%2A> with member overloads that accept a <xref:System.Globalization.CultureInfo>.</span></span> <span data-ttu-id="6a664-128">Para obtener más información, consulte [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) y [Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="6a664-128">For more information, see [Performing Culture-Insensitive String Operations in Collections](../globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) and [Performing Culture-Insensitive String Operations in Arrays](../globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md).</span></span>

<a name="BKMK_Equalityandsortexample"></a>
## <a name="equality-and-sort-example"></a><span data-ttu-id="6a664-129">Ejemplo de igualdad y ordenación</span><span class="sxs-lookup"><span data-stu-id="6a664-129">Equality and sort example</span></span>

<span data-ttu-id="6a664-130">El código siguiente muestra una implementación de <xref:System.IEquatable%601> y <xref:System.IComparable%601> en un objeto comercial simple.</span><span class="sxs-lookup"><span data-stu-id="6a664-130">The following code demonstrates an implementation of <xref:System.IEquatable%601> and <xref:System.IComparable%601> on a simple business object.</span></span> <span data-ttu-id="6a664-131">Además, cuando el objeto se almacena en una lista y se ordena, la llamada al método <xref:System.Collections.Generic.List%601.Sort> implica el uso del comparador predeterminado para el tipo `Part` y el método <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> implementado mediante el uso de un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="6a664-131">In addition, when the object is stored in a list and sorted, you will see that calling the <xref:System.Collections.Generic.List%601.Sort> method results in the use of the default comparer for the `Part` type, and the <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29> method implemented by using an anonymous method.</span></span>

[!code-csharp[System.Collections.Generic.List.Sort#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.collections.generic.list.sort/cs/program.cs#1)]
[!code-vb[System.Collections.Generic.List.Sort#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.collections.generic.list.sort/vb/module1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="6a664-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a664-132">See also</span></span>

- <xref:System.Collections.IComparer>
- <xref:System.IEquatable%601>
- <xref:System.Collections.Generic.IComparer%601>
- <xref:System.IComparable>
- <xref:System.IComparable%601>
