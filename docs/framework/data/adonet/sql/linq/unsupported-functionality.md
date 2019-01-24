---
title: Funcionalidad no admitida
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 5022c9011c2aac5b3272e359f991c40236a5673f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686710"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="9c42b-102">Funcionalidad no admitida</span><span class="sxs-lookup"><span data-stu-id="9c42b-102">Unsupported Functionality</span></span>
<span data-ttu-id="9c42b-103">En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9c42b-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="9c42b-104">Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="9c42b-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="9c42b-105">Para obtener más información, consulta <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9c42b-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="9c42b-106">LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="9c42b-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="9c42b-107">Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="9c42b-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="9c42b-108">LINQ to SQL proporciona compatibilidad limitada para `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="9c42b-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="9c42b-109">Para obtener más información, consulte [System.Math (métodos)](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="9c42b-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c42b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c42b-110">See also</span></span>
- [<span data-ttu-id="9c42b-111">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="9c42b-111">Data Types and Functions</span></span>](data-types-and-functions.md)
