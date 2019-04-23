---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: a58d5620abbb636480ceea3020552246ae284842
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771600"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Sintaxis  
  
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
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica el requisito para un encabezado de token de seguridad emitido (IssuedTokens de WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El protocolo de transacciones utilizado por el servicio para fluir las transacciones.  
  
### <a name="transactions"></a>Transacciones  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Indica si se admite la transacción entrante.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
