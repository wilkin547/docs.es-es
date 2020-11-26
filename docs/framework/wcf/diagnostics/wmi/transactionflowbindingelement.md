---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234900"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement

TransactionFlowBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
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

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  

 Tipo de datos: cadena  
  
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

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
