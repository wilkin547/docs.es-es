---
title: Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="64e31-102">Realizar operaciones de cadenas que no tienen en cuenta las referencias culturales en matrices</span><span class="sxs-lookup"><span data-stu-id="64e31-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="64e31-103">Sobrecargas de la <xref:System.Array.Sort%2A?displayProperty=nameWithType> y <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> métodos realizan ordenaciones de cuenta de la referencia cultural predeterminada utilizando la <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="64e31-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="64e31-104">Cuenta de la referencia cultural devuelta por estos métodos pueden variar según la referencia cultural debido a diferencias en los criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="64e31-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="64e31-105">Para eliminar el comportamiento de la cuenta de la referencia cultural, use una de las sobrecargas de este método que acepta un `comparer` parámetro.</span><span class="sxs-lookup"><span data-stu-id="64e31-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="64e31-106">El `comparer` parámetro especifica el <xref:System.Collections.IComparer> implementación va a utilizar al comparar elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="64e31-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="64e31-107">Para el parámetro, especifique una clase comparadora invariable personalizada que utiliza <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64e31-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64e31-108">Se proporciona un ejemplo de una clase comparadora invariable personalizada en el tema "Utilizar la clase SortedList" de la [realizar operaciones de cadena cuenta las referencias culturales en colecciones](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) tema.</span><span class="sxs-lookup"><span data-stu-id="64e31-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="64e31-109">**Tenga en cuenta** pasar **CultureInfo.InvariantCulture** a una comparación método lleva a cabo una comparación de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="64e31-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="64e31-110">Si embargo, no provoca una comparación no lingüística, por ejemplo, para las rutas de acceso de archivo, las claves del Registro y las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="64e31-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="64e31-111">Tampoco admite las decisiones de seguridad basadas en el resultado de la comparación.</span><span class="sxs-lookup"><span data-stu-id="64e31-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="64e31-112">Para una comparación no lingüística o soporte técnico para tomar decisiones de seguridad basada en el resultado, la aplicación debe utilizar un método de comparación que acepta un <xref:System.StringComparison> valor.</span><span class="sxs-lookup"><span data-stu-id="64e31-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="64e31-113">A continuación, debe pasar la aplicación <xref:System.StringComparison.Ordinal>.</span><span class="sxs-lookup"><span data-stu-id="64e31-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e31-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="64e31-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="64e31-115">Realizar operaciones de cadenas que no distinguen entre referencias culturales</span><span class="sxs-lookup"><span data-stu-id="64e31-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
