---
title: Transacciones distribuidas de Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 4af1c98818f1929850c5ae78892c64993a93d4d2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771961"
---
# <a name="oracle-distributed-transactions"></a>Transacciones distribuidas de Oracle
El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa. La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones. Para deshabilitar la inscripción automática en transacciones existentes, especifique   
  
```  
Enlist=false  
```  
  
 como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Vea también

- [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
