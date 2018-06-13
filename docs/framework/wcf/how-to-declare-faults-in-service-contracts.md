---
title: Cómo declarar errores en contratos de servicios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 142ad26702f0732bc5103e29d5a44bc57ab37625
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500241"
---
# <a name="how-to-declare-faults-in-service-contracts"></a>Cómo declarar errores en contratos de servicios
En código administrado, las excepciones se inician al producirse condiciones de error. Sin embargo, en aplicaciones de Windows Communication Foundation (WCF), contratos de servicio especifican qué información de error se devuelve a los clientes mediante la declaración de los errores de SOAP en el contrato de servicio. Para obtener información general de la relación entre las excepciones y errores, vea [especificar y control de errores en contactos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a>Crear un contrato de servicio que especifica un error de SOAP  
  
1.  Crear un contrato de servicio que contiene al menos una operación. Para obtener un ejemplo, vea [Cómo: definir un contrato de servicio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Seleccione una operación capaz de especificar una condición de error sobre la que los clientes esperan ser informados. Para decidir qué condiciones de error justifican devolver errores de SOAP a los clientes, consulte [especificar y control de errores en contactos y servicios](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
3.  Aplique <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> a la operación seleccionada y pase un tipo de error serializable al constructor. Para obtener más información sobre cómo crear y usar tipos serializables, consulte [especificación de transferencia de datos en contratos de servicio](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md). El ejemplo siguiente muestra cómo especificar que la operación `SampleMethod` puede producir un `GreetingFault`.  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  Repita los pasos 2 y 3 en todas las operaciones del contrato que comunican las condiciones de error a los clientes.  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a>Implementar una operación para devolver un error de SOAP especificado  
 Cuando una operación especifica que un error de SOAP concreto puede devolverse (como en el procedimiento anterior) para comunicar una condición de error a la aplicación que realiza la llamada, el siguiente paso es implementar esa especificación.  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a>Iniciar el error de SOAP especificado en la operación  
  
1.  Cuando se produce una condición de error especificada en un <xref:System.ServiceModel.FaultContractAttribute>, inicie una nueva <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> en la que el error de SOAP especificado es el parámetro de tipo. El siguiente ejemplo muestra cómo iniciar el `GreetingFault` en `SampleMethod` mostrado en el procedimiento anterior y en la sección de código siguiente.  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra la implementación de una operación única que especifica `GreetingFault` para la operación `SampleMethod`.  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
