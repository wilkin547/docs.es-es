---
title: Procedimiento para llamar a operaciones de manera asincrónica mediante un generador de canales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cc17dd47-b9ad-451c-a362-e36e0aac7ba0
ms.openlocfilehash: 25d88b00e0bb1105be57989ff5d090a308177329
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601275"
---
# <a name="how-to-call-operations-asynchronously-using-a-channel-factory"></a>Procedimiento para llamar a operaciones de manera asincrónica mediante un generador de canales
En este tema se cubre cómo un cliente puede obtener acceso de forma asincrónica a una operación del servicio al utilizar una aplicación de cliente basada en <xref:System.ServiceModel.ChannelFactory%601>. (Al utilizar un objeto <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> para invocar un servicio, puede utilizar el modelo de llamada asincrónica orientado a eventos. Para obtener más información, vea [Cómo: llamar a las operaciones de servicio de forma asincrónica](how-to-call-wcf-service-operations-asynchronously.md). Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [patrón asincrónico basado en eventos (EAP)](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).  
  
 El servicio en este tema implementa la interfaz `ICalculator`. El cliente puede llamar a las operaciones en esta interfaz de forma asincrónica, lo que significa que las operaciones como `Add` se dividen en dos métodos, `BeginAdd` y `EndAdd`, de los cuales el primero inicia la llamada y el segundo recupera el resultado cuando la operación termina. Para obtener un ejemplo que muestra cómo implementar una operación de forma asincrónica en un servicio, vea [Cómo: implementar una operación de servicio asincrónica](../how-to-implement-an-asynchronous-service-operation.md). Para obtener más información sobre las operaciones sincrónicas y asincrónicas, consulte [operaciones sincrónicas y asincrónicas](../synchronous-and-asynchronous-operations.md).  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Para llamar a operaciones de servicio WCF de forma asincrónica  
  
1. Ejecute la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con la `/async` opción como se muestra en el siguiente comando.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a  
    ```  
  
     Esto genera una versión de cliente asincrónica del contrato de servicio para la operación.  
  
2. Cree una función de devolución de llamada a la que se va a llamar cuando la operación asincrónica haya finalizado, tal y como aparece en el siguiente código de ejemplo.  
  
     [!code-csharp[C_How_To_CF_Async#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#2)]
     [!code-vb[C_How_To_CF_Async#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#2)]  
  
3. Para obtener acceso de forma asincrónica a una operación de servicio, cree el cliente y llame a `Begin[Operation]` (por ejemplo, `BeginAdd`) y especifique una función de devolución de llamada, tal y como se muestra en el siguiente código de ejemplo.  
  
     [!code-csharp[C_How_To_CF_Async#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/client.cs#3)]
     [!code-vb[C_How_To_CF_Async#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/client.vb#3)]  
  
     Cuando la función de devolución de llamada se ejecuta, el cliente llama a `End<operation>``EndAdd` (por ejemplo, ) para recuperar el resultado.  
  
## <a name="example"></a>Ejemplo  
 El servicio que se usa con el código de cliente que se utiliza en el procedimiento anterior implementa la interfaz `ICalculator` tal y como se muestra en el código siguiente. En el lado del servicio, `Add` las `Subtract` operaciones y del contrato se invocan sincrónicamente en el tiempo de ejecución de Windows Communication Foundation (WCF), aunque los pasos del cliente anteriores se invocan de forma asincrónica en el cliente. Las operaciones `Multiply` y `Divide` se utilizan para invocar de forma asincrónica el servicio en el lado del servicio, incluso aunque el cliente los invoque de forma sincrónica. Este ejemplo establece la propiedad <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> en `true`. Esta configuración de propiedad, en combinación con la implementación del .NET Framework modelo asincrónico, indica al tiempo de ejecución que invoque la operación de forma asincrónica.  
  
 [!code-csharp[C_How_To_CF_Async#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_how_to_cf_async/cs/service.cs#4)]
 [!code-vb[C_How_To_CF_Async#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_how_to_cf_async/vb/service.vb#4)]  
