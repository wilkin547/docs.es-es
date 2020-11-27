---
title: 'Cómo: Crear un contrato de Windows Communication Foundation con una clase'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: f2164b4f4c997de764139a7a0a2aecbf91616458
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286245"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Cómo: Crear un contrato de Windows Communication Foundation con una clase

La manera preferida de crear un contrato de Windows Communication Foundation (WCF) es mediante una interfaz. Para obtener más información, vea [Cómo: definir un contrato de servicio](../how-to-define-a-wcf-service-contract.md). Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.  
  
> [!WARNING]
> `[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo. Lo mismo se cumple para `[OperationContract]` y `[OperationContractAttribute]` . En cada caso, la primera es la abreviatura de este último.  
  
 Para obtener más información acerca de los contratos de servicio, consulte [diseño de contratos de servicio](../designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creación de un contrato de Windows Communication Foundation con una clase  
  
1. Cree una nueva clase con Visual Basic, C# o cualquier otro lenguaje de Common Language Runtime.  
  
2. Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.  
  
3. Cree los métodos en la clase.  
  
4. Aplique la <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que debe exponerse como parte del contrato de WCF público.  
  
## <a name="example"></a>Ejemplo  

 El ejemplo de código siguiente muestra una clase que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. Para obtener más información sobre este patrón de mensaje, consulte [Cómo: crear un contrato de Request-Reply](how-to-create-a-request-reply-contract.md). Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, consulte [Cómo: crear un contrato de One-Way](how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
