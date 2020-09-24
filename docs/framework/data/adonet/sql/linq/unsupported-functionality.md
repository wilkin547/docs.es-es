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
# <a name="unsupported-functionality"></a>Funcionalidad incompatible

En LINQ to SQL, la siguiente funcionalidad de SQL no se puede exponer a través de la conversión de las construcciones existentes de Common Language Runtime (CLR) y .NET Framework:  
  
- `STDDEV`  
  
- `LIKE`  
  
     Aunque `LIKE` no se admite a través de la conversión directa, existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>. Para obtener más información, vea <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.  
  
- `DATEDIFF`  
  
     LINQ to SQL proporciona compatibilidad limitada para `DATEDIFF`. Existe una funcionalidad similar en la clase <xref:System.Data.Linq.SqlClient.SqlMethods>.  
  
- `ROUND`  
  
     LINQ to SQL proporciona compatibilidad limitada para `ROUND`. Para obtener más información, vea [métodos System. Math](system-math-methods.md).  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos y funciones](data-types-and-functions.md)
