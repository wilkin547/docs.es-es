---
title: "&lt;etwTracking&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;etwTracking&gt;
Un comportamiento del servicio que permite a un servicio usar el seguimiento de ETW utilizando un objeto <xref:System.Activities.Tracking.ETWTrackingParticipant>.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <etwTracking profileName=”String” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|profileName|Una cadena que especifica el nombre del perfil de seguimiento asociado a este comportamiento.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\> de \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración configura un participante de seguimiento en un servicio de flujo de trabajo.  
  
 Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.  Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.  
  
## Ejemplo  
 El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.  
  
 El Id. del proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se definen en la sección **\<diagnostics\>**.  El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.  Esto viene definido por el atributo **profileName** del elemento **\<add\>**.  Una vez definidos, el participante de seguimiento se agrega al comportamiento del servicio **\<etwTracking\>**.  Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.  
  
```  
  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>   
 [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Participantes de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-participants.md)