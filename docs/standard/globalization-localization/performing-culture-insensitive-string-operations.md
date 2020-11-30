---
title: Realizar operaciones de cadenas que no distinguen entre referencias culturales
ms.date: 08/22/2018
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
ms.openlocfilehash: a418432dfaba9ab070ddb6dc862dcbd798c16343
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732221"
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="4dee1-102">Realizar operaciones de cadena que no distinguen entre referencias culturales</span><span class="sxs-lookup"><span data-stu-id="4dee1-102">Performing culture-insensitive string operations</span></span>

<span data-ttu-id="4dee1-103">La mayoría de los métodos de .NET que realizan operaciones de cadenas que no distinguen entre referencias culturales de manera predeterminada proporcionan sobrecargas de método que permiten pasar un parámetro <xref:System.Globalization.CultureInfo> para especificar explícitamente la referencia cultural que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4dee1-103">Most .NET methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="4dee1-104">Estas sobrecargas permiten eliminar variaciones de referencia cultural en reglas de ordenación y asignaciones de mayúsculas y minúsculas y garantizan resultados que no distinguen entre referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="4dee1-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="4dee1-105">En esta sección se proporcionan los artículos siguientes para mostrar cómo realizar operaciones de cadenas que no distinguen entre referencias culturales con métodos de .NET que tienen en cuenta las referencias culturales de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4dee1-105">This section provides the following articles to demonstrate how to perform culture-insensitive string operations using .NET methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dee1-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4dee1-106">In this section</span></span>  

 [<span data-ttu-id="4dee1-107">Realizar comparaciones de cadenas que no distinguen entre referencias culturales</span><span class="sxs-lookup"><span data-stu-id="4dee1-107">Performing Culture-Insensitive String Comparisons</span></span>](performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="4dee1-108">Se describe cómo usar los métodos <xref:System.String.Compare%2A?displayProperty=nameWithType> y <xref:System.String.CompareTo%2A?displayProperty=nameWithType> para realizar comparaciones de cadenas que no distinguen entre referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="4dee1-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="4dee1-109">Realizar cambios de mayúsculas y minúsculas que no distinguen entre referencias culturales</span><span class="sxs-lookup"><span data-stu-id="4dee1-109">Performing Culture-Insensitive Case Changes</span></span>](performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="4dee1-110">Se describe cómo usar los métodos <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> y <xref:System.Char.ToLower%2A?displayProperty=nameWithType> para realizar cambios de mayúsculas y minúsculas que no distinguen entre referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="4dee1-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="4dee1-111">Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en colecciones</span><span class="sxs-lookup"><span data-stu-id="4dee1-111">Performing Culture-Insensitive String Operations in Collections</span></span>](performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="4dee1-112">Se describe cómo usar las clases <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider>, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> y <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> para realizar operaciones en colecciones que no distinguen entre referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="4dee1-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="4dee1-113">Realizar operaciones de cadenas que no distinguen entre referencias culturales en matrices</span><span class="sxs-lookup"><span data-stu-id="4dee1-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="4dee1-114">Se describe cómo usar los métodos <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> para realizar operaciones en matrices que no distinguen entre referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="4dee1-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4dee1-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4dee1-115">Related sections</span></span>  

 [<span data-ttu-id="4dee1-116">Operaciones de cadenas que no distinguen referencias culturales</span><span class="sxs-lookup"><span data-stu-id="4dee1-116">Culture-Insensitive String Operations</span></span>](culture-insensitive-string-operations.md)  
 <span data-ttu-id="4dee1-117">Describe por qué debe tomar en cuenta la referencia cultural cuando realiza operaciones en cadenas y proporciona guías que indiquen cuándo realizar operaciones que tienen en cuenta las referencias culturales y cuándo las que no distinguen entre referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="4dee1-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dee1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4dee1-118">See also</span></span>

- [<span data-ttu-id="4dee1-119">Ordenación de tablas de peso (para .NET en sistemas Windows)</span><span class="sxs-lookup"><span data-stu-id="4dee1-119">Sorting Weight Tables (for .NET on Windows systems)</span></span>](https://www.microsoft.com/download/details.aspx?id=10921)
- [<span data-ttu-id="4dee1-120">Tabla de elementos de intercalación predeterminada Unicode (para .NET Core en macOS y Linux)</span><span class="sxs-lookup"><span data-stu-id="4dee1-120">Default Unicode Collation Element Table (for .NET Core on Linux and macOS)</span></span>](https://www.unicode.org/Public/UCA/latest/allkeys.txt)
