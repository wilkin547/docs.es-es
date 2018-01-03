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
# <a name="unsupported-functionality"></a>Funcionalidad no admitida
En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>. Para obtener más información, consulta <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
-   `DATEDIFF`  
  
     LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`. Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
-   `ROUND`  
  
     LINQ to SQL proporciona compatibilidad limitada para `ROUND`. Para obtener más información, consulte [System.Math (métodos)](system-math-methods.md).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos y funciones](data-types-and-functions.md)
