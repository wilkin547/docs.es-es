---
title: Funcionalidad no admitida
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 244d9ee7accd3686729542d0f0a15966bcde7b78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="unsupported-functionality"></a><span data-ttu-id="b2627-102">Funcionalidad no admitida</span><span class="sxs-lookup"><span data-stu-id="b2627-102">Unsupported Functionality</span></span>
<span data-ttu-id="b2627-103">En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b2627-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="b2627-104">Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="b2627-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="b2627-105">Para obtener más información, consulta <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2627-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="b2627-106">LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="b2627-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="b2627-107">Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="b2627-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="b2627-108">LINQ to SQL proporciona compatibilidad limitada para `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="b2627-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="b2627-109">Para obtener más información, consulte [System.Math (métodos)](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="b2627-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2627-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2627-110">See Also</span></span>  
 [<span data-ttu-id="b2627-111">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="b2627-111">Data Types and Functions</span></span>](data-types-and-functions.md)
