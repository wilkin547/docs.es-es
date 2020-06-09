---
title: Cómo llamar a operaciones del servicio WCF de forma asincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 400ed8e5ee8b236e9d0f843f27b7c2112ec28861
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601262"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Cómo llamar a operaciones del servicio WCF de forma asincrónica

En este artículo se explica cómo un cliente puede tener acceso de forma asincrónica a una operación de servicio. El servicio de este artículo implementa la `ICalculator` interfaz. El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos. (Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)). Para obtener un ejemplo que muestra cómo implementar una operación de forma asincrónica en un servicio, vea [Cómo: implementar una operación de servicio asincrónica](../how-to-implement-an-asynchronous-service-operation.md). Para obtener más información sobre las operaciones sincrónicas y asincrónicas, vea [operaciones sincrónicas y asincrónicas](../synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>. Para obtener información sobre cómo realizar llamadas asincrónicas mediante <xref:System.ServiceModel.ChannelFactory%601> , vea [Cómo: llamar a operaciones de forma asincrónica con un generador de canales](how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Para llamar a operaciones de servicio WCF de forma asincrónica  
  
1. Ejecute la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) con las `/async` Opciones de `/tcv:Version35` comando y, tal y como se muestra en el siguiente comando.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Esto genera, además de las operaciones asincrónicas sincrónicas y estándar basadas en delegado, una clase de cliente de WCF que contiene:  
  
    - Dos `operationName` > `Async` operaciones de <para su uso con el enfoque de llamada asincrónica basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Los eventos de operación completada del formulario <`operationName` > `Completed` para su uso con el enfoque de llamada asincrónica basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType>tipos para cada operación (de la forma <`operationName` > `CompletedEventArgs` ) para su uso con el enfoque de llamada asincrónica basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Antes de llamar a la operación, utilice un nuevo genérico <xref:System.EventHandler%601?displayProperty=nameWithType> de tipo <`operationName` > `EventArgs` para agregar el método de control (creado en el paso anterior) al `operationName` > `Completed` evento <. A continuación, llame al `operationName` > `Async` método <. Por ejemplo:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Ejemplo  
  
> [!NOTE]
> Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>. Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`. Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>. Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para implementar una operación de servicios asincrónica](../how-to-implement-an-asynchronous-service-operation.md)
