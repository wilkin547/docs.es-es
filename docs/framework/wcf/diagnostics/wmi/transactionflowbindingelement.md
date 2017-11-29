---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase TransactionFlowBindingElement no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase TransactionFlowBindingElement tiene las propiedades siguientes:  
  
### <a name="issuedtokens"></a>IssuedTokens  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El protocolo de transacciones utilizado por el servicio para fluir las transacciones.  
  
### <a name="transactions"></a>Transacciones  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Indica si se admite la transacción entrante.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
