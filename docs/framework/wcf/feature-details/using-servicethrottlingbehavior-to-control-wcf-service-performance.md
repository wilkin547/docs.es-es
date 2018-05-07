---
title: Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF
ms.date: 03/30/2017
helpviewer_keywords:
- behavior [WCF], service performance
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
ms.openlocfilehash: b54d1d6146b9751fdd12502771de01fe52854c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-servicethrottlingbehavior-to-control-wcf-service-performance"></a>Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF
La clase <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> expone las propiedades que pueden utilizarse para limitar cuántas instancias o sesiones se crean en el nivel de la aplicación. Con este comportamiento, puede ajustar el rendimiento de la aplicación de Windows Communication Foundation (WCF).  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>Control de las instancias del servicio y las llamadas simultáneas  
 Utilice la propiedad <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> para especificar el número máximo de mensajes que se procesan activamente en una clase <xref:System.ServiceModel.ServiceHost>, y la propiedad <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> para especificar el número máximo de objetos <xref:System.ServiceModel.InstanceContext> del servicio.  
  
 Carga debido a determinar los valores de estas propiedades normalmente tiene lugar después de ejecutar la aplicación con la experiencia real, la configuración para el <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> propiedades normalmente se especifica en un archivo de configuración de aplicación mediante el [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) elemento.  
  
 El siguiente ejemplo de código muestra el uso de la clase <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> de un archivo de configuración de la aplicación que establece el valor 1 en <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, y las propiedades <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>, como ejemplo banal. La experiencia real determina los valores óptimos para cualquier aplicación determinada.  
  
 [!code-xml[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  
  
 El comportamiento de tiempo de ejecución exacto depende en los valores de <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> y las propiedades <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>, que controlan cuántos mensajes pueden ejecutarse al mismo tiempo en una operación, y las duraciones del servicio <xref:System.ServiceModel.InstanceContext> en relación a las sesiones del canal de entrada, respectivamente.  
  
 Para obtener información detallada, vea <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, y <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>  
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>
