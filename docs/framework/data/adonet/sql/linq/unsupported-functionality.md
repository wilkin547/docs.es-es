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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b54bac0c9ce0b473ef8d86b039ef638b79af784f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
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
