---
title: "System.String (Métodos)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d33e99c0fb184413c989900b652ce7bb5b5d67eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="systemstring-methods"></a><span data-ttu-id="e0b6e-102">System.String (Métodos)</span><span class="sxs-lookup"><span data-stu-id="e0b6e-102">System.String Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="e0b6e-103"> no admite los métodos <xref:System.String> siguientes.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-103"> does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="e0b6e-104">Métodos System.String no admitidos en general</span><span class="sxs-lookup"><span data-stu-id="e0b6e-104">Unsupported System.String Methods in General</span></span>  
 <span data-ttu-id="e0b6e-105">Métodos <xref:System.String> no admitidos en general:</span><span class="sxs-lookup"><span data-stu-id="e0b6e-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
-   <span data-ttu-id="e0b6e-106">Sobrecargas que reconocen la referencia cultural (métodos que toman una `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).</span><span class="sxs-lookup"><span data-stu-id="e0b6e-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
-   <span data-ttu-id="e0b6e-107">Métodos que utilizan o generan una matriz `char`.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="e0b6e-108">Métodos System.String estáticos no admitidos</span><span class="sxs-lookup"><span data-stu-id="e0b6e-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="e0b6e-109">Métodos System.String estáticos no admitidos</span><span class="sxs-lookup"><span data-stu-id="e0b6e-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="e0b6e-110">Métodos System.String no estáticos no admitidos</span><span class="sxs-lookup"><span data-stu-id="e0b6e-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="e0b6e-111">Métodos System.String no estáticos no admitidos</span><span class="sxs-lookup"><span data-stu-id="e0b6e-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="e0b6e-112">Diferencias respecto a .NET</span><span class="sxs-lookup"><span data-stu-id="e0b6e-112">Differences from .NET</span></span>  
  
-   <span data-ttu-id="e0b6e-113">Las consultas no tienen en cuenta las intercalaciones de SQL Server que podrían aplicarse en el servidor y, por lo tanto, proporcionan de forma predeterminada comparaciones dependientes de la referencia cultural, sin distinción entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="e0b6e-114">Este comportamiento difiere del predeterminado, la semántica con distinción entre mayúsculas y minúsculas de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="e0b6e-115">Cuando `LastIndexOf` devuelve 0, la cadena es `NULL` o la posición encontrada es 0.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
-   <span data-ttu-id="e0b6e-116">Pueden obtenerse resultados inesperados en operaciones de concatenación u otras operaciones con cadenas de longitud fija (`CHAR`, `NCHAR`), porque a estos tipos se les aplica relleno automáticamente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
-   <span data-ttu-id="e0b6e-117">Dado que muchos métodos, como `Replace`, `ToLower`, `ToUpper`, y el indizador de carácter, no tienen ningún equivalente válido para las columnas `TEXT` o `NTEXT` y XML, se producirán `SqlExceptions` si se convierten de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="e0b6e-118">Este comportamiento se considera que es aceptable para estos tipos.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="e0b6e-119">Sin embargo, todas las operaciones de cadena deben coincidir con la semántica de Common Language Runtime (CLR) para `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` y `NVARCHAR(max)`.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b6e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0b6e-120">See Also</span></span>  
 [<span data-ttu-id="e0b6e-121">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="e0b6e-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
