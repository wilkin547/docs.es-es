---
title: Transacciones distribuidas de Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c901ccf9132dc766d78efb24428b6469458a70fa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="oracle-distributed-transactions"></a>Transacciones distribuidas de Oracle
El objeto <xref:System.Data.OracleClient.OracleConnection> se inscribe automáticamente en una transacción distribuida si determina que hay una transacción activa. La inscripción automática en transacciones tiene lugar cuando se abre la conexión o se recupera del grupo de conexiones. Para deshabilitar la inscripción automática en transacciones existentes, especifique   
  
```  
Enlist=false  
```  
  
 como un parámetro de cadena de conexión de una <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>Vea también  
 [Oracle y ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
