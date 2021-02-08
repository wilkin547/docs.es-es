---
description: 'Más información acerca de cómo: declarar errores en contratos de servicio'
title: Procedimiento para declarar errores en contratos de servicios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 1d83840386338747c983d8c4e9a788a452b9c4b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793264"
---
# <a name="how-to-declare-faults-in-service-contracts"></a>Procedimiento para declarar errores en contratos de servicios

En código administrado, las excepciones se inician al producirse condiciones de error. Sin embargo, en las aplicaciones de Windows Communication Foundation (WCF), los contratos de servicio especifican qué información de error se devuelve a los clientes mediante la declaración de errores de SOAP en el contrato de servicio. Para obtener información general sobre la relación entre las excepciones y los errores, vea [especificar y controlar errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md).

## <a name="create-a-service-contract-that-specifies-a-soap-fault"></a>Crear un contrato de servicio que especifica un error de SOAP

1. Crear un contrato de servicio que contiene al menos una operación. Para obtener un ejemplo, consulte [Cómo: definir un contrato de servicio](how-to-define-a-wcf-service-contract.md).

2. Seleccione una operación capaz de especificar una condición de error sobre la que los clientes esperan ser informados. Para decidir qué condiciones de error justifican la devolución de errores SOAP a los clientes, consulte [especificación y control de errores en contratos y servicios](specifying-and-handling-faults-in-contracts-and-services.md).

3. Aplique <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> a la operación seleccionada y pase un tipo de error serializable al constructor. Para obtener más información sobre la creación y el uso de tipos serializables, vea [especificar transferencia de datos en contratos de servicio](./feature-details/specifying-data-transfer-in-service-contracts.md). El ejemplo siguiente muestra cómo especificar que la operación `SampleMethod` puede producir un `GreetingFault`.

     [!code-csharp[FaultContractAttribute#4](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]

4. Repita los pasos 2 y 3 en todas las operaciones del contrato que comunican las condiciones de error a los clientes.

## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a>Implementar una operación para devolver un error de SOAP especificado

 Cuando una operación especifica que un error de SOAP concreto puede devolverse (como en el procedimiento anterior) para comunicar una condición de error a la aplicación que realiza la llamada, el siguiente paso es implementar esa especificación.

### <a name="throw-the-specified-soap-fault-in-the-operation"></a>Iniciar el error de SOAP especificado en la operación

1. Cuando se produce una condición de error especificada en un <xref:System.ServiceModel.FaultContractAttribute>, inicie una nueva <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> en la que el error de SOAP especificado es el parámetro de tipo. El siguiente ejemplo muestra cómo iniciar el `GreetingFault` en `SampleMethod` mostrado en el procedimiento anterior y en la sección de código siguiente.

     [!code-csharp[FaultContractAttribute#5](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra la implementación de una operación única que especifica `GreetingFault` para la operación `SampleMethod`.

[!code-csharp[FaultContractAttribute#1](~/samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
[!code-vb[FaultContractAttribute#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
