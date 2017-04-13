---
title: "&lt;comContracts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;comContracts&gt;
La sección de configuración `comContracts` contiene elementos que le permiten especificar varias propiedades de un contrato de servicios de la integración de COM\+.  
  
## Especificar espacio de nombres y contrato  
 Los contratos de servicio de integración de COM\+ están restringidos actualmente al espacio de nombres "http:\/\/tempuri.org" y el nombre del contrato se deriva de la interfaz COM de apoyo.  Puede, sin embargo, especificar alternativas mediante la sección `comContracts` en el archivo de configuración.  
  
 Por ejemplo, puede utilizar la configuración siguiente para especificar el espacio de nombres y nombre del contrato del contrato de servicios, así como una opción para exigir el uso en enlaces con sesión.  
  
```  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
  </comContract>  
</comContracts>  
```  
  
 Cuando se inicializa el servicio, los espacios de nombres y nombres del contrato especificados se aplican a las descripciones de servicio generadas.  
  
 Cuando esta sección está vacía, la inicialización del servicio aplica un espacio de nombres y un nombre de contrato predeterminados tomados del identificador de la interfaz COM de apoyo.  
  
 Además, puede utilizar el elemento [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) para especificar métodos de COM\+ que se exponen cuando la interfaz en un componente de COM\+ se expone como un Servicio Web.  También puede utilizar [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md) para especificar tipos con persistencia utilizados en integración.  Finalmente, puede utilizar el elemento [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md) para incluir tipos definidos por el usuario \(UDT\) que estarán incluidos en el contrato de servicios.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>   
 <xref:System.ServiceModel.Configuration.ComContractElement>   
 [\<exposedMethod\>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md)   
 [\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)   
 [\<userDefinedType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userdefinedtype.md)   
 [\<comContract\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontract.md)   
 [Integración en aplicaciones COM\+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Cómo configurar los parámetros de los servicios COM\+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)