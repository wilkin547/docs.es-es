---
title: Comparación de las transacciones en COM+ y ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 30ecbd374e909141dbc944740f90c1b41ac44ed2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264913"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Comparación de las transacciones en COM+ y ServiceModel

En este tema se describe cómo simular el comportamiento de un servicio transaccional de COM+ mediante los atributos Windows Communication Foundation (WCF) que <xref:System.ServiceModel> proporciona el espacio de nombres.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulación de COM+ mediante los atributos de ServiceModel  

 En la tabla siguiente se compara la <xref:System.EnterpriseServices.TransactionOption> enumeración utilizada para crear una `EnterpriseServices` transacción y cómo se relacionan con los atributos WCF que <xref:System.ServiceModel> proporciona el espacio de nombres.  
  
|Atributo COM+|Atributos de WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Requerido|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `true`.|  
|Compatible|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `Required`.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `false`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Disabled|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `NotSupported`.|
