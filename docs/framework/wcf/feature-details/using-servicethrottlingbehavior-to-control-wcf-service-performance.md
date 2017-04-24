---
title: "Utilizaci&#243;n de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "comportamiento [WCF], el rendimiento del servicio"
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Utilizaci&#243;n de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF
El <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> clase expone propiedades que puede usar para limitar cuántas instancias o sesiones se crean en el nivel de aplicación. Con este comportamiento, se precisa el rendimiento de su aplicación [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Control de las instancias del servicio y las llamadas simultáneas  
 Utilice la <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> propiedad para especificar el número máximo de mensajes que se procesan activamente en un <xref:System.ServiceModel.ServiceHost> (clase) y el <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> propiedad para especificar el número máximo de <xref:System.ServiceModel.InstanceContext> objetos en el servicio.  
  
 Dado que determinar la configuración de estas propiedades normalmente se produce después de ejecutar la aplicación con la experiencia real se carga, la configuración de la <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> propiedades normalmente se especifica en un archivo de configuración de aplicación mediante el [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) elemento.  
  
 En el ejemplo de código siguiente se muestra el uso de la <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> clase a partir de un archivo de configuración de aplicación que establece el <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, y <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> propiedades como 1 como un ejemplo. La experiencia real determina los valores óptimos para cualquier aplicación determinada.  
  
 <!-- TODO: review snippet reference [!code-csharp[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  -->  
  
 El comportamiento de tiempo de ejecución exacto depende de los valores de la <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> y <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> propiedades que controlan la cantidad de mensajes puede ejecutarse dentro de una operación a la vez y las duraciones del servicio <xref:System.ServiceModel.InstanceContext> en relación con la entrada de las sesiones del canal, respectivamente.  
  
 Para obtener más información, consulte <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, y <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>   
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>