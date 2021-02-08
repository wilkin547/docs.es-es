---
description: 'Más información acerca de cómo: crear un servicio con una interfaz de contrato'
title: Procedimiento para crear un servicio con una interfaz de contrato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: 5080f6bb45030811b87f952fb62a74801bc1ef88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793836"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Procedimiento para crear un servicio con una interfaz de contrato

La manera preferida de crear un contrato de Windows Communication Foundation (WCF) es mediante una interfaz. Este contrato especifica la colección y estructura de mensajes requeridas para obtener acceso a las operaciones que el servicio proporciona. Esta interfaz define los tipos de entrada y salida aplicando la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz y la clase <xref:System.ServiceModel.OperationContractAttribute> a los métodos que desee exponer.  
  
 Para obtener más información acerca de los contratos de servicio, consulte [diseño de contratos de servicio](../designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Creación de un contrato WCF con una interfaz  
  
1. Cree una nueva interfaz con Visual Basic, C# o cualquier otro lenguaje de Common Language Runtime.  
  
2. Aplique la clase <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz.  
  
3. Defina los métodos en la interfaz.  
  
4. Aplique la <xref:System.ServiceModel.OperationContractAttribute> clase a cada método que debe exponerse como parte del contrato de WCF público.  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo de código muestra una interfaz que define un contrato de servicio.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 Los métodos que tienen aplicada la clase <xref:System.ServiceModel.OperationContractAttribute> usan de forma predeterminada un patrón de mensaje solicitud-respuesta. Para obtener más información sobre este patrón de mensaje, consulte [Cómo: crear un contrato de Request-Reply](how-to-create-a-request-reply-contract.md). Puede crear y utilizar también otros patrones de mensaje estableciendo las propiedades del atributo. Para obtener más ejemplos, consulte [Cómo: crear un contrato de One-Way](how-to-create-a-one-way-contract.md) y [Cómo: crear un contrato dúplex](how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
