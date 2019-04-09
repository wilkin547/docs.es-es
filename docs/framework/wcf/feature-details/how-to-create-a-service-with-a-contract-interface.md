---
title: Filtrar para crear un servicio con una interfaz de contrato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: c31a954d659b3f686f8b9780276a4719064e60cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128718"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Filtrar para crear un servicio con una interfaz de contrato
Es la mejor manera de crear un contrato de Windows Communication Foundation (WCF) mediante el uso de una interfaz. Este contrato especifica la colección y estructura de mensajes requeridas para obtener acceso a las operaciones que el servicio proporciona. Esta interfaz define los tipos de entrada y salida aplicando la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz y la clase <xref:System.ServiceModel.OperationContractAttribute> a los métodos que desee exponer.  
  
 Para obtener más información sobre los contratos de servicio, consulte [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Creación de un contrato WCF con una interfaz  
  
1.  Cree una nueva interfaz utilizando Visual Basic, C#, o cualquier otro lenguaje de common language runtime.  
  
2.  Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.  
  
3.  Defina los métodos en la interfaz.  
  
4.  Aplicar el <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que se debe exponer como parte del contrato público de WCF.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código muestra una interfaz que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. Para obtener más información sobre este patrón de mensaje, vea [Cómo: Crear un contrato de solicitud-respuesta](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, vea [Cómo: Crear un contrato unidireccional](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) y [Cómo: Crear un contrato dúplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
