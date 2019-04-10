---
title: Filtrar Crear un contrato de Windows Communication Foundation con una clase
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 37d0e6fae8ad0f3a91f1bead23fb5823fc52d420
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313232"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Filtrar Crear un contrato de Windows Communication Foundation con una clase
Es la mejor manera de crear un contrato de Windows Communication Foundation (WCF) mediante el uso de una interfaz. Para obtener más información, vea [Cómo: Definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.  
  
> [!WARNING]
>  `[ServiceContract]` y `[ServiceContractAttribute]` hacer lo mismo. Lo mismo es cierto para `[OperationContract]` y `[OperationContractAttribute]`. En cada caso, el primero es una abreviatura para el último.  
  
 Para obtener más información sobre los contratos de servicio, consulte [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creación de un contrato de Windows Communication Foundation con una clase  
  
1. Cree una nueva clase utilizando Visual Basic, C#, o cualquier otro lenguaje de common language runtime.  
  
2. Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.  
  
3. Cree los métodos en la clase.  
  
4. Aplicar el <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que se debe exponer como parte del contrato público de WCF.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra una clase que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. Para obtener más información sobre este patrón de mensaje, vea [Cómo: Crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, vea [Cómo: Crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: Crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
