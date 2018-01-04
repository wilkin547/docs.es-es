---
title: "Comparación de las transacciones en COM+ y ServiceModel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87e3df31060a9c71e0b2868aa34373bca221fa79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Comparación de las transacciones en COM+ y ServiceModel
Este tema expone cómo simular el comportamiento de un servicio transaccional de COM+ mediante los atributos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que proporciona el espacio de nombres <xref:System.ServiceModel>.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulación de COM+ mediante los atributos de ServiceModel  
 La siguiente tabla compara la enumeración <xref:System.EnterpriseServices.TransactionOption> utilizada para crear una transacción `EnterpriseServices`, y cómo se correlacionan con los atributos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporcionados por el espacio de nombres <xref:System.ServiceModel>.  
  
|Atributo COM+|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] atributos|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Obligatorio|El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `true`.|  
|Compatible|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `Required`.|  
|NotSupported|El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `false`.<br /><br /> El atributo `TransactionFlow` en el elemento de enlace es `false`.|  
|Disabled|No existe equivalente directo. En general, debería adoptar en su lugar el comportamiento especificado para `NotSupported`.|
