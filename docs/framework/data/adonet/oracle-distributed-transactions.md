---
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 6f910f1dbbe448352c0edd5d1b80df659ac453d4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795146"
---
# <a name="oracle-distributed-transactions"></a>Transacciones distribuidas de Oracle
El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa. La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones. Para deshabilitar la inscripción automática en transacciones existentes, especifique  
  
```  
Enlist=false  
```  
  
 como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Vea también

- [Oracle y ADO.NET](oracle-and-adonet.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
