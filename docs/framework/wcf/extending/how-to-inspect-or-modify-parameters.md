---
title: "C&#243;mo: inspeccionar o modificar par&#225;metros | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ab6c0ac7-aac4-45ba-93d6-a0e9afd1756f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: inspeccionar o modificar par&#225;metros
Puede inspeccionar o modificar los mensajes entrantes o salientes para una única operación en un [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] objeto de cliente o un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servicio implementando la <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName> interfaz e insertarlos en el tiempo de ejecución de cliente o servicio. Normalmente se utiliza un comportamiento de operación para agregar inspectores de parámetro en una sola operación; se pueden utilizar otros comportamientos para proporcionar acceso fácil al tiempo de ejecución en un ámbito mayor. Para obtener más información, consulte [clientes extender](../../../../docs/framework/wcf/extending/extending-clients.md) y [extender distribuidores](../../../../docs/framework/wcf/extending/extending-dispatchers.md).  
  
### <a name="inspecting-or-modifying-parameters"></a>Inspeccionando o modificando parámetros  
  
1.  Implemente el <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName> interfaz.  
  
2.  Implemente un <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName> o <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> (dependiendo del ámbito requerido) para agregar su inspector de parámetro a la <xref:System.ServiceModel.Dispatcher.ClientOperation.ParameterInspectors%2A?displayProperty=fullName> o <xref:System.ServiceModel.Dispatcher.DispatchOperation.ParameterInspectors%2A?displayProperty=fullName> propiedades.  
  
3.  Inserte su comportamiento antes de llamar a <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName> o <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> método en el <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>. Para obtener más información, consulte [configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código muestran, en orden:  
  
-   Una implementación de inspector de parámetro.  
  
-   La implementación de comportamiento que inserta el inspector de parámetro con un <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>, <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>y un <xref:System.ServiceModel.Description.IServiceBehavior?displayProperty=fullName>.  
  
-   Un archivo de configuración que carga y ejecuta el comportamiento del punto de conexión en una aplicación cliente para insertar el inspector de parámetro en el cliente.  
  
 [!code-csharp[Interceptors#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/interceptors.cs#4)]
 [!code-vb[Interceptors#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/interceptors.vb#4)]  
  
 [!code-csharp[Interceptors#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/insertingbehaviors.cs#5)]
 [!code-vb[Interceptors#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/insertingbehaviors.vb#5)]  
  
 <!-- TODO: review snippet reference [!code[Interceptors#3](../../../../samples/snippets/common/VS_Snippets_CFX/interceptors/common/client.exe.config#3)]  -->
 <!-- TODO: review snippet reference [!code-csharp[Interceptors#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/interceptors/cs/client.exe.config#3)]  -->
 <!-- TODO: review snippet reference [!code-vb[Interceptors#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/interceptors/vb/client.exe.config#3)]  -->  
  
## <a name="see-also"></a>Vea también  
 [Configurar y extender el tiempo de ejecución con comportamientos](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)