---
description: 'Más información sobre: funcionalidad no admitida'
title: Funcionalidad incompatible
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 5c44dd4aad2d2ee4ec5e00ce42f4de9400cea478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680894"
---
# <a name="unsupported-functionality"></a><span data-ttu-id="1406b-103">Funcionalidad incompatible</span><span class="sxs-lookup"><span data-stu-id="1406b-103">Unsupported Functionality</span></span>

<span data-ttu-id="1406b-104">En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1406b-104">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
- `STDDEV`  
  
- `LIKE`  
  
     <span data-ttu-id="1406b-105">Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="1406b-105">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="1406b-106">Para obtener más información, vea <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1406b-106">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
- `DATEDIFF`  
  
     <span data-ttu-id="1406b-107">LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`.</span><span class="sxs-lookup"><span data-stu-id="1406b-107">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="1406b-108">Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.</span><span class="sxs-lookup"><span data-stu-id="1406b-108">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
- `ROUND`  
  
     <span data-ttu-id="1406b-109">LINQ to SQL proporciona compatibilidad limitada para `ROUND`.</span><span class="sxs-lookup"><span data-stu-id="1406b-109">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="1406b-110">Para obtener más información, vea [métodos System. Math](system-math-methods.md).</span><span class="sxs-lookup"><span data-stu-id="1406b-110">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1406b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1406b-111">See also</span></span>

- [<span data-ttu-id="1406b-112">Tipos de datos y funciones</span><span class="sxs-lookup"><span data-stu-id="1406b-112">Data Types and Functions</span></span>](data-types-and-functions.md)
