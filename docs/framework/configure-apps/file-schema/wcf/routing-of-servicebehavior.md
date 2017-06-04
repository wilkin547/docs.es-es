---
title: "&lt;routing&gt; de &lt;serviceBehavior&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;routing&gt; de &lt;serviceBehavior&gt;
Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <routing filterTable=”String”  
         routeOnHeadersOnly="Boolean"  
         SoapProcessingEnabled=”Boolean” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|filterTable|Cadena que especifica el nombre de la tabla de enrutamiento que contiene filtros que va a evaluar el servicio del enrutamiento.  Este valor debe coincidir con el atributo `name` de un elemento [\<filterTable\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) en la sección [\<filterTables\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md).|  
|routeOnHeaderOnly|Valor booleano que especifica si el filtro examinará el cuerpo del mensaje y el encabezado, o solo el encabezado.  De manera predeterminada, es `true`.|  
|soapProcessingEnabled|Valor booleano que especifica si se debe producir el procesamiento SOAP.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Cuando se agrega a la configuración del comportamiento del servicio, este elemento de configuración habilita el enrutamiento para el servicio.  Puede especificar la tabla de enrutamiento real que va a usar el servicio en este elemento.  
  
 Mediante esta sección de configuración, puede cambiar la configuración de enrutamiento sobre la marcha cuando cambie el patrón de implementación.  En tiempo de ejecución, puede registrar su propia extensión de enrutamiento con una nueva configuración de enrutamiento y el servicio de enrutamiento empezará a usar la información de configuración actualizada para los mensajes y sesiones nuevos, mientras deja que los mensajes o las sesiones en curso usen las reglas que estaban en vigor cuando se iniciaron. Esto le permite realizar la reconfiguración del servicio de enrutamiento con menos reciclaje y segura para la sesión durante el tiempo de ejecución.  
  
## Vea también  
 <xref:System.ServiceModel.Routing.RoutingExtenstion>   
 <xref:System.ServiceModel.Routing.Configuration.RoutingExtenstionElement>