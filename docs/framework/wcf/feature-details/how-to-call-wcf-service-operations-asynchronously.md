---
title: "C&#243;mo llamar a operaciones del servicio WCF de forma asincr&#243;nica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# C&#243;mo llamar a operaciones del servicio WCF de forma asincr&#243;nica
En este tema se explica cómo puede tener acceso un cliente a una operación de servicio de forma asincrónica.El servicio en este tema implementa la interfaz `ICalculator`.El cliente puede llamar a las operaciones de esta interfaz de forma asincrónica mediante el modelo de llamada asincrónica orientado a eventos.\(Para obtener más información sobre el modelo de llamada asincrónica basado en eventos, vea [Programación multiproceso con el modelo asincrónico basado en eventos](http://go.microsoft.com/fwlink/?LinkId=248184)\).Para obtener un ejemplo que muestra cómo implementar de forma asincrónica una operación en un servicio, vea [Cómo: Implementar una operación de servicios asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).Para obtener más información acerca de las operaciones sincrónicas y asincrónicas, vea [Operaciones sincrónicas y asincrónicas](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).  
  
> [!NOTE]
>  El modelo de llamada asincrónica orientado a eventos no es compatible con la utilización de un <xref:System.ServiceModel.ChannelFactory%601>.Para obtener más información acerca de la realización de llamadas asincrónicas mediante el <xref:System.ServiceModel.ChannelFactory%601>, vea [Cómo llamar a operaciones de manera asincrónica mediante un generador de canales](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).  
  
## Procedimiento  
  
#### Para llamar a operaciones de servicio WCF de forma asincrónica  
  
1.  Ejecute la herramienta [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con las opciones de comando `/async` y `/tcv:Version35` a la vez, como muestra el comando siguiente.  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     De este modo se genera, además de las operaciones sincrónicas y las operaciones estándar asincrónicas basadas en delegado, una clase de cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que incluye:  
  
    -   Dos operaciones \<`operationName`\>`Async` que se utilizan con el enfoque de llamada asincrónica basada en eventos.Por ejemplo:  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   Eventos completados de operación del formulario \<`operationName`\>`Completed` que se utilizan con el enfoque de llamada asincrónica basada en eventos.Por ejemplo:  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   Tipos <xref:System.EventArgs?displayProperty=fullName> para cada operación \(del formulario \<`operationName`\>`CompletedEventArgs`\) que se utilizan en el enfoque de llamada asincrónica basado en eventos.Por ejemplo:  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2.  En la aplicación de llamada, cree un método de devolución de llamada al que llamar cuando la operación asincrónica finalice, tal y como se muestra en el siguiente código de ejemplo.  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3.  Antes de llamar a la operación, utilice un nuevo genérico <xref:System.EventHandler%601?displayProperty=fullName> de tipo \<`operationName`\>`EventArgs` para agregar el método del controlador \(creado en el paso anterior \) al evento \<`operationName`\>`Completed`.A continuación, llame al método \<`operationName`\>`Async`.Por ejemplo:  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## Ejemplo  
  
> [!NOTE]
>  Las directrices de diseño del modelo asincrónico basado en eventos afirman que si se devuelve más de un valor, uno de los valores se devuelve como propiedad `Result` y los demás se devuelven como propiedades del objeto <xref:System.EventArgs>.Una de las consecuencias de esto, es que el cliente importa metadatos utilizando las opciones de comando asincrónicas basadas en eventos y la operación devuelve más de una valor, el objeto predeterminado <xref:System.EventArgs> devuelve un valor como propiedad `Result`, y el resto son propiedades del objeto <xref:System.EventArgs>.Para recibir el objeto de mensaje como propiedad `Result` y que los valores devueltos sean propiedades de ese objeto, se utiliza la opción de comando `/messageContract`.Esto genera una firma que devuelve el mensaje de respuesta como la propiedad `Result` del objeto <xref:System.EventArgs>.Todos los valores de devolución internos se convierten, pues, en propiedades del objeto de mensaje de respuesta.  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## Vea también  
 [Cómo: Implementar una operación de servicios asincrónica](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)