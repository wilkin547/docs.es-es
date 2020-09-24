---
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a21134c3283d3d9d8d7660eecaaf74d60ecf6662
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166526"
---
# <a name="oracle-distributed-transactions"></a>Transacciones distribuidas de Oracle

El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa. La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones. Para deshabilitar la inscripción automática en transacciones existentes, especifique   
  
```csharp  
Enlist=false  
```  
  
 como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Consulte también

- [Oracle y ADO.NET](oracle-and-adonet.md)
- [Información general de ADO.NET](ado-net-overview.md)
