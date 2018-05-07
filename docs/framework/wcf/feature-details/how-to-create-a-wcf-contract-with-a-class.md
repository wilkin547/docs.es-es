---
title: 'Cómo: Crear un contrato de Windows Communication Foundation con una clase'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 296f500532040aaebf0f6d7d37a7a9aae99a3451
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Cómo: Crear un contrato de Windows Communication Foundation con una clase
Es la mejor manera de crear un contrato de Windows Communication Foundation (WCF) mediante el uso de una interfaz. Para obtener más información, consulte [Cómo: definir un contrato de servicio](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.  
  
> [!WARNING]
>  `[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo. Lo mismo se aplica a `[OperationContract]` y `[OperationContractAttribute]`. En cada caso el anterior es una forma abreviada del último.  
  
 Para obtener más información acerca de los contratos de servicio, consulte [diseñar contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creación de un contrato de Windows Communication Foundation con una clase  
  
1.  Cree una nueva clase mediante Visual Basic, C# o cualquier otro lenguaje de common language runtime.  
  
2.  Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.  
  
3.  Cree los métodos en la clase.  
  
4.  Aplicar la <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que debe exponerse como parte del contrato público de WCF.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra una clase que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. Para obtener más información sobre este patrón de mensaje, consulte [Cómo: crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, vea [Cómo: crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
