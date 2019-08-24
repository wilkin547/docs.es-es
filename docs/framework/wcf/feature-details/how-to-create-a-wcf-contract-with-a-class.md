---
title: Procedimiento Creación de un contrato de Windows Communication Foundation con una clase
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988745"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Procedimiento Creación de un contrato de Windows Communication Foundation con una clase
La manera preferida de crear un contrato de Windows Communication Foundation (WCF) es mediante una interfaz. Para obtener más información, consulte [Cómo Defina un contrato](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)de servicio. Una alternativa, descrita aquí, es crear una clase y después aplicar directamente el atributo <xref:System.ServiceModel.ServiceContractAttribute> a la clase directamente y el atributo <xref:System.ServiceModel.OperationContractAttribute> a cada uno de los métodos de la clase que forman parte del contrato.  
  
> [!WARNING]
> `[ServiceContract]` y `[ServiceContractAttribute]` hacen lo mismo. Lo mismo se cumple para `[OperationContract]` y. `[OperationContractAttribute]` En cada caso, la primera es la abreviatura de este último.  
  
 Para obtener más información acerca de los contratos de servicio, consulte [diseño de contratos de servicio](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Creación de un contrato de Windows Communication Foundation con una clase  
  
1. Cree una nueva clase con Visual Basic, C#o cualquier otro lenguaje de Common Language Runtime.  
  
2. Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la clase.  
  
3. Cree los métodos en la clase.  
  
4. Aplique la <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que debe exponerse como parte del contrato de WCF público.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra una clase que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. Para obtener más información acerca de este patrón de [mensaje, consulte Cómo: Cree un contrato](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)de solicitud-respuesta. Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, vea [Cómo: Crear un contrato](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) unidireccional y [cómo: Cree un contrato](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)dúplex.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
