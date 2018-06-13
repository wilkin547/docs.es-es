---
title: Comparación de las transacciones en COM+ y ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 4a47fe1686dff2e705b06b001d7d5e4ea6e8c5f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488652"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Comparación de las transacciones en COM+ y ServiceModel
Este tema describe cómo simular el comportamiento de un servicio transaccional de COM + mediante los atributos de Windows Communication Foundation (WCF) el <xref:System.ServiceModel> proporciona el espacio de nombres.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulación de COM+ mediante los atributos de ServiceModel  
 La siguiente tabla compara la <xref:System.EnterpriseServices.TransactionOption> enumeración que se usa para crear un `EnterpriseServices` transacciones y cómo se correlacionan con los atributos WCF la <xref:System.ServiceModel> proporciona el espacio de nombres.  
  
|Atributo COM+|Atributos WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Obligatorio|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `true`.|  
|Compatible|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `Required`.|  
|NotSupported|El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `false`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Disabled|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `NotSupported`.|
