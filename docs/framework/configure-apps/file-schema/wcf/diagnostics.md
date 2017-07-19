---
title: "&lt;diagn&#243;stico&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# &lt;diagn&#243;stico&gt;
El elemento `diagnostics` define valores que pueden ser utilizados por un administrador para la inspección y control en tiempo de ejecución.  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
   <diagnostics etwProviderId=”String”  
       performanceCounters="Off/ServiceOnly/All/Default"         
       wmiProviderEnabled="Boolean" >  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
          maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
             <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|etwProviderId|Cadena que especifica el identificador del proveedor de la traza de eventos, que escribe los eventos en las sesiones de ETW.|  
|performanceCounters|Especifica si se habilitan los contadores de rendimiento para el ensamblado.  Los valores válidos son<br /><br /> -   Desactivado: Los contadores de rendimiento están deshabilitados.<br />-   ServiceOnly: Sólo los contadores de rendimiento relevantes para este servicio están habilitados.<br />-   Todos: Los contadores de rendimiento se pueden ver en tiempo de ejecución.<br />-   Valor predeterminado: Se crea un \_WCF\_Admin de instancia de contador de rendimiento único.  Esta instancia se utiliza para habilitar la colección de datos de SQM usados por la infraestructura.  Ninguno de los valores de contador para esta instancia está actualizado y por consiguiente permanecerá a cero.  Éste es el valor predeterminado si ninguna configuración está presente para WCF.|  
|wmiProviderEnabled|Un valor booleano que especifica si el proveedor de WMI para el ensamblado está habilitado.  El proveedor de WMI se requiere para que el usuario obtenga acceso en tiempo de ejecución a las características de control e inspección de Windows Communication Foundation \(WCF\).  De manera predeterminada, es `false`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<endToEndTracing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.|  
|[\<messageLogging\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|Describe los valores para el registro de mensajes WCF.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|serviceModel|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## Comentarios  
 La sección `diagnostics` define los valores de diagnóstico para todos los servicios situados en un ensamblado.  No es posible definir los valores de diagnóstico independientes en el nivel de servicio a menos que sólo haya un servicio en el ensamblado.  Los atributos se establecen según los requisitos de la sección.  
  
## Ejemplo  
  
```  
<diagnostics wmiProviderEnabled="false"  
       performanceCounters="all">  
       <messageLogging logEntireMessage="true"  
          logMalformedMessages="true"  
          logMessagesAtServiceLevel="true"  
          logMessagesAtTransportLevel="true"  
          maxMessagesToLog="42"  
          maxSizeOfMessageToLog="42">  
         <filters>  
         <clear />  
    </filters>  
       </messageLogging>  
</diagnostics>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>