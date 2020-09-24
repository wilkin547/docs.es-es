---
title: Funcionalidad incompatible
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: d4fe3d91b80197d962989cd2d3bc9bb2df6e3ffe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164160"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="57fdb-102">Funcionalidad incompatible</span><span class="sxs-lookup"><span data-stu-id="57fdb-102">Unsupported Functionality</span></span>

<span data-ttu-id="57fdb-103">En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="57fdb-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="57fdb-104">Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="57fdb-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="57fdb-105">Para obtener más información, vea <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57fdb-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="57fdb-106">LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="57fdb-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="57fdb-107">Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="57fdb-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="57fdb-108">LINQ to SQL proporciona compatibilidad limitada para `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="57fdb-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="57fdb-109">Para obtener más información, vea [métodos System. Math](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="57fdb-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fdb-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57fdb-110">See also</span></span>

- [<span data-ttu-id="57fdb-111">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="57fdb-111">Data Types and Functions</span></span>](data-types-and-functions.md)
