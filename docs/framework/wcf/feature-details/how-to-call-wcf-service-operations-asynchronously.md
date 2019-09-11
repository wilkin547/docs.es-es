---
title: Procedimiento Llamar a operaciones de servicio WCF de forma asincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2c0a6f1477ceec5471c22fa3e46d85f5856b298e
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895068"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Procedimiento Llamar a operaciones de servicio WCF de forma asincrónica
En este tema se explica cómo puede tener acceso un cliente a una operación de servicio de forma asincrónica. El servicio en este tema implementa la interfaz `ICalculator`. El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos. (Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](https://go.microsoft.com/fwlink/?LinkId=248184)). Para obtener un ejemplo que muestra cómo implementar una operación de forma asincrónica en un servicio [, consulte Cómo: Implemente una operación](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)de servicio asincrónica. Para obtener más información sobre las operaciones sincrónicas y asincrónicas, vea [operaciones sincrónicas y asincrónicas](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
> El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>. Para obtener información sobre cómo realizar llamadas asincrónicas <xref:System.ServiceModel.ChannelFactory%601>mediante el [, consulte Cómo: Llamar a las operaciones de forma asincrónica](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)mediante un generador de canales.  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Para llamar a operaciones de servicio WCF de forma asincrónica  
  
1. Ejecute la herramienta de [utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con `/async` las `/tcv:Version35` opciones de comando y, tal y como se muestra en el siguiente comando.  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Esto genera, además de las operaciones asincrónicas sincrónicas y estándar basadas en delegado, una clase de cliente de WCF que contiene:  
  
    - Dos operaciones`operationName` de <> `Async` para su uso con el enfoque de llamada asincrónica basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - Los eventos de operación completada del`operationName` formulario <> `Completed` para su uso con el enfoque de llamada asincrónica basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <xref:System.EventArgs?displayProperty=nameWithType>tipos para cada operación (de la forma <`operationName`>`CompletedEventArgs`) para su uso con el enfoque de llamada asincrónica basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. Antes de llamar a la operación, utilice un nuevo <xref:System.EventHandler%601?displayProperty=nameWithType> genérico de tipo`operationName` <`Completed` > `EventArgs` para agregar el método de control (creado en el paso anterior) al`operationName` evento <.> A continuación, llame`operationName` al método <> `Async` . Por ejemplo:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Ejemplo  
  
> [!NOTE]
> Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>. Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`. Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>. Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Implementar una operación de servicio asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
