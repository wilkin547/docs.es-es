---
title: "&lt;exposedMethod&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;exposedMethod&gt;
Representa un método de COM\+ que se expone cuando la interfaz en un componente COM\+ se expone como un servicio web.  
  
## Sintaxis  
  
```  
  
<comContracts>  
  <comContract>  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Una cadena que contiene el método de COM\+ que se expone cuando la interfaz de un componente COM\+ se expone como servicio Web.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<exposedMethods\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Una colección de elementos de [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md).|  
  
## Comentarios  
 La herramienta de configuración de integración \(ComSvcConfig.exe\) de COM\+ se puede usar para agregar métodos concretos de una interfaz COM para que aparezca en el contrato del servicio generado.  
  
 Por ejemplo, puede usar el comando siguiente para agregar los tres métodos con nombre de la interfaz COM `IFinances`, en el componente financiero `ItemOrders`, al contrato del servicio generado.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 Al ejecutar también la herramienta ComSvcConfig.exe, se genera el contrato del servicio siguiente que hace una lista de los métodos previamente mencionados como elementos [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md).  
  
```  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" name="IFinances" namespace="http://contoso.com/services/financial">  
    <exposedMethod name="TransferFunds"/>  
    <exposedMethod name="AddFunds"/>  
    <exposedMethod name="RemoveFunds"/>  
</comContract>  
```  
  
 En el momento de inicialización del servicio, el tiempo de ejecución intenta generar un contrato de servicio reflejando y agregando sólo los métodos incluidos en la lista de elementos [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md).  Un seguimiento se genera para cada método de interfaz que no está incluido en el contrato del servicio.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ComMethodElementCollection>   
 <xref:System.ServiceModel.Configuration.ComMethodElement>   
 [\<comContracts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)   
 [Integración en aplicaciones COM\+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Cómo configurar los parámetros de los servicios COM\+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)