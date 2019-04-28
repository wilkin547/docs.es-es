---
title: Comparación de las transacciones en COM+ y ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 4a47fe1686dff2e705b06b001d7d5e4ea6e8c5f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857875"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Comparación de las transacciones en COM+ y ServiceModel
En este tema se describe cómo simular el comportamiento de un servicio de COM + transaccional a mediante los atributos de Windows Communication Foundation (WCF) el <xref:System.ServiceModel> proporciona el espacio de nombres.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulación de COM+ mediante los atributos de ServiceModel  
 La tabla siguiente compara la <xref:System.EnterpriseServices.TransactionOption> enumeración que se usa para crear un `EnterpriseServices` transacciones y cómo se correlacionan con los atributos WCF la <xref:System.ServiceModel> proporciona el espacio de nombres.  
  
|Atributo COM+|Atributos WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Obligatorio|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `true`.|  
|Compatible|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `Required`.|  
|NotSupported|El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `false`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Deshabilitado|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `NotSupported`.|
