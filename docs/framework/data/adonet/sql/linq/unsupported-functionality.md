---
title: Funcionalidad incompatible
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097878"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="d4cfa-102">Funcionalidad incompatible</span><span class="sxs-lookup"><span data-stu-id="d4cfa-102">Unsupported Functionality</span></span>
<span data-ttu-id="d4cfa-103">En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d4cfa-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="d4cfa-104">Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="d4cfa-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="d4cfa-105">Para obtener más información, consulta <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d4cfa-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="d4cfa-106">LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="d4cfa-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="d4cfa-107">Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="d4cfa-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="d4cfa-108">LINQ to SQL proporciona compatibilidad limitada para `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="d4cfa-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="d4cfa-109">Para obtener más información, consulte [System.Math (métodos)](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="d4cfa-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4cfa-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4cfa-110">See also</span></span>

- [<span data-ttu-id="d4cfa-111">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="d4cfa-111">Data Types and Functions</span></span>](data-types-and-functions.md)
