---
title: "&lt;serviceThrottling&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# &lt;serviceThrottling&gt;
Especifica el mecanismo de limitación de peticiones de un servicio de Windows Communication Foundation \(WCF\).  
  
## Sintaxis  
  
```  
  
<serviceThrottling maxConcurrentCalls="Integer"  
    maxConcurrentInstances="Integer"  
    maxConcurrentSessions="Integer" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|maxConcurrentCalls|Entero positivo que limita el número de mensajes que actualmente procesan en <xref:System.ServiceModel.ServiceHost>.  Las llamadas que superan el límite se ponen en cola.  Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.  El valor predeterminado es 16 \* número de procesadores.|  
|maxConcurrentInstances|Entero positivo que limita el número de los objetos <xref:System.ServiceModel.InstanceContext> que se ejecutan a la vez en <xref:System.ServiceModel.ServiceHost>.  Las solicitudes para crear instancias adicionales se ponen en cola y se completan cuando queda disponible una ranura por debajo del límite.  El valor predeterminado es la suma de maxConcurrentSessions y MaxConcurrentCalls|  
|maxConcurrentSessions|Entero positivo que limita el número máximo de sesiones que un objeto <xref:System.ServiceModel.ServiceHost> puede aceptar.<br /><br /> El servicio admitirá conexiones que excedan el límite, pero solo los canales por debajo del límite estarán activos \(los mensajes se leen desde el canal\).  Establecer este valor en 0 es equivalente a establecerlo en Int32.MaxValue.  El valor predeterminado es 100 \* número de procesadores.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.  
  
 Se escribe un seguimiento cada vez que se alcanza el valor de los atributos.  El primer seguimiento se escribe como una advertencia.  
  
## Ejemplo  
 El ejemplo de configuración siguiente especifica que el servicio limita el máximo de llamadas simultáneas a 2, y el número máximo de instancias simultáneas a 10.  Para obtener un ejemplo detallado de la ejecución de este ejemplo, vea [Limitación de peticiones](../../../../../docs/framework/wcf/samples/throttling.md).  
  
```  
<behaviors>   
  <serviceBehaviors>   
    <behavior name="CalculatorServiceBehavior">   
      <serviceDebug includeExceptionDetailInFaults="False" />   
      <serviceMetadata httpGetEnabled="True"/>   
      <!-- Specify throttling behavior -->  
      <serviceThrottling maxConcurrentCalls="2"   
           maxConcurrentInstances="10"/>   
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>   
 <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>   
 [Utilización de ServiceThrottlingBehavior para controlar el rendimiento de los servicios WCF](../../../../../docs/framework/wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)