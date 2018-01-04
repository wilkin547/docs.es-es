---
title: "Cómo: Crear un contrato de Windows Communication Foundation con una clase"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44418d9d7ec88ea5cd340312fd1ebe42ef8d20a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Cómo: Crear un contrato de Windows Communication Foundation con una clase
La manera preferida de crear un contrato [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es utilizar una interfaz. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.  
  
> [!WARNING]
>  `[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo. Lo mismo se aplica a `[OperationContract]` y `[OperationContractAttribute]`. En cada caso el anterior es una forma abreviada del último.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]contratos de servicio, consulte [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creación de un contrato de Windows Communication Foundation con una clase  
  
1.  Cree una nueva clase mediante [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# o cualquier otro lenguaje de Common Language Runtime.  
  
2.  Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.  
  
3.  Cree los métodos en la clase.  
  
4.  Aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada método que debe exponerse como parte del contrato público de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra una clase que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Este patrón de mensajes, vea [Cómo: crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, vea [Cómo: crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
