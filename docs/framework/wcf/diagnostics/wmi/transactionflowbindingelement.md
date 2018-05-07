---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
