---
title: "C&#243;mo: Inspeccionar y modificar mensajes en el servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c5b1cc7-84f3-45f8-9226-d59c278e8c42
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# C&#243;mo: Inspeccionar y modificar mensajes en el servicio
Puede inspeccionar o modificar los mensajes entrantes o salientes a través de un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] cliente implementando un <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName> e insertarlos en la ejecución del servicio. Para obtener más información, consulte [extender distribuidores](../../../../docs/framework/wcf/extending/extending-dispatchers.md). La característica equivalente en el servicio es el <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>.  
  
### <a name="to-inspect-or-modify-messages"></a>Inspeccionar o modificar los mensajes  
  
1.  Implemente el <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName> interfaz.  
  
2.  Implemente un <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> interfaz dependiendo del ámbito en el que desea insertar fácilmente su inspector de mensajes del servicio.  
  
3.  Inserte su comportamiento antes de llamar a la <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> método en el <xref:System.ServiceModel.ServiceHost?displayProperty=fullName>. Para obtener más información, consulte [configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código muestran, en orden:  
  
-   Una implementación de inspector de servicio.  
  
-   Un comportamiento del servicio que inserta el inspector.  
  
-   Un archivo de configuración que carga y ejecuta el comportamiento en una aplicación de servicio.  
  
 [!code-csharp[Interceptors#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#7)]
 [!code-vb[Interceptors#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#7)]  
  
 [!code-csharp[Interceptors#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#8)]
 [!code-vb[Interceptors#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#8)]  
  
 <!-- TODO: review snippet reference [!code[Interceptors#9](../../../../samples/snippets/common/VS_Snippets_CFX/interceptors/common/hostapplication.exe.config#9)]  -->
 <!-- TODO: review snippet reference [!code-csharp[Interceptors#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/hostapplication.exe.config#9)]  -->
 <!-- TODO: review snippet reference [!code-vb[Interceptors#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/hostapplication.exe.config#9)]  -->  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>   
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>   
 [Configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)