---
title: Funcionalidad incompatible
ms.date: 03/30/2017
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
ms.openlocfilehash: 18a1a8f33a9360b4299648bcd329f4c5f2e7de88
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097878"
---
# <a name="unsupported-functionality"></a>Funcionalidad incompatible
En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>. Para obtener más información, consulta <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`. Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
-   `ROUND`  
  
     LINQ to SQL proporciona compatibilidad limitada para `ROUND`. Para obtener más información, consulte [System.Math (métodos)](system-math-methods.md).  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos y funciones](data-types-and-functions.md)
