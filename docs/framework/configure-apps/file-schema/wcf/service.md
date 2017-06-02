---
title: "&lt;servicio&gt; | Microsoft Docs"
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
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
caps.latest.revision: 27
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 27
---
# &lt;servicio&gt;
El elemento `service` contiene los valores para un servicio de Windows Communication Foundation \(WCF\).  También contiene extremos que exponen el servicio.  
  
## Sintaxis  
  
```  
  
<service behaviorConfiguration=String"  
        name="String"  
</service>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|behaviorConfiguration|Una cadena que contiene el nombre de comportamiento que se va a usar para instanciar el servicio.  El nombre de comportamiento debe estar en el ámbito en el punto definido del servicio.  El valor predeterminado es una cadena vacía.|  
|name|Atributo String necesario que especifica el tipo del servicio del que se van a crear instancias.  Este valor debe equivaler a un tipo válido.  El formato debería ser `Namespace.Class.`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<extremo\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|Una colección de elementos `endpoint` que exponen este servicio.|  
|[\<host\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Especifica el host de esta instancia del servicio.  Este elemento es del tipo <xref:System.ServiceModel.Configuration.HostElement>.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<servicios\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## Comentarios  
 Los servicios se definen en la sección de `services` del archivo de configuración.  Un ensamblado puede contener cualquier número de servicios.  Cada servicio tiene su propia sección de configuración de `service`.  Esta sección y su contenido definen el contrato de servicios, comportamiento y extremos del servicio determinado.  
  
 El elemento `behaviorConfiguration` también es opcional.  Identifica el comportamiento que el servicio utiliza.  El comportamiento especificado en este atributo debe vincular a un comportamiento en ámbito en el mismo archivo de configuración.  
  
 Cada servicio expone uno o más extremos, que tienen su propia dirección y enlace.  Todos los enlaces usados dentro del archivo de configuración se deben definir en el ámbito del archivo.  Los enlaces se vinculan a los extremos a través de la combinación de los atributos `name` y `bindingConfiguration`.  El atributo `name` describe la sección en la que está definido el enlace.  El atributo `bindingConfiguration` define qué configuración se usa dentro de la sección de enlaces.  Una sección obligatoria puede definir varias configuraciones.  
  
## Ejemplo  
 Éste es un ejemplo de una configuración de servicio.  
  
```  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceElement>   
 [Configuración de servicios](../../../../../docs/framework/wcf/configuring-services.md)