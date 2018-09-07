---
title: Cómo llamar a operaciones del servicio WCF de forma asincrónica
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 90e00e4264ff808151c9e1c58fdaf290765620c8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44076760"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a>Cómo llamar a operaciones del servicio WCF de forma asincrónica
En este tema se explica cómo puede tener acceso un cliente a una operación de servicio de forma asincrónica. El servicio en este tema implementa la interfaz `ICalculator`. El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos. (Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [programación multiproceso con el modelo asincrónico basado en eventos](https://go.microsoft.com/fwlink/?LinkId=248184)). Para obtener un ejemplo que muestra cómo implementar una operación asincrónica en un servicio, consulte [Cómo: implementar una operación de servicio asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md). Para obtener más información acerca de las operaciones sincrónicas y asincrónicas, vea [sincrónica y operaciones asincrónicas](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
>  El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>. Para obtener información acerca de cómo realizar llamadas asincrónicas mediante el <xref:System.ServiceModel.ChannelFactory%601>, consulte [Cómo: llamar a las operaciones de forma asincrónica utilizando un generador de canales](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## <a name="procedure"></a>Procedimiento  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a>Para llamar a operaciones de servicio WCF de forma asincrónica  
  
1.  Ejecute el [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) herramienta con ambos el `/async` y `/tcv:Version35` las opciones del comando juntos como se muestra en el siguiente comando.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     Esto genera, además de las operaciones sincrónicas y estándares basado en delegados asincrónicas, una clase de cliente WCF que contiene:  
  
    -   Dos <`operationName` > `Async` operaciones para su uso con el enfoque de llamada asincrónico basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   Eventos completados de operación del formulario <`operationName` > `Completed` para su uso con el enfoque de llamada asincrónico basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType> tipos para cada operación (el formato <`operationName`>`CompletedEventArgs`) para su uso con el enfoque de llamada asincrónico basado en eventos. Por ejemplo:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  Antes de llamar a la operación, utilice un nuevo genérico <xref:System.EventHandler%601?displayProperty=nameWithType> de tipo <`operationName` > `EventArgs` para agregar el método de controlador (creado en el paso anterior) a la <`operationName` > `Completed` eventos. A continuación, llame a la <`operationName` > `Async` método. Por ejemplo:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a>Ejemplo  
  
> [!NOTE]
>  Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>. Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`. Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>. Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a>Vea también  
 [Cómo implementar una operación de servicios asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
