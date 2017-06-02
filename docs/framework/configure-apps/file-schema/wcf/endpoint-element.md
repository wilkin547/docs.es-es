---
title: "elemento de &lt;extremo&gt; | Microsoft Docs"
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
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# elemento de &lt;extremo&gt;
Especifica enlace, contrato y propiedades de dirección para un extremo de servicio, que se utiliza para exponer los servicios.  
  
## Sintaxis  
  
```  
  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   bindingName="String"  
   bindingNamespace="String"  
   contract="String"  
   endpointConfiguration=”String”  
   isSystemEndpoint=”Boolean”  
   kind=”String”  
   listenUriMode="Explicit/Unique"  
   listenUri="Uri"  
</endpoint>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|address|Una cadena que contiene la dirección del extremo.  La dirección se puede especificar como una dirección absoluta o relativa.  Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base adecuada para el esquema de transporte usado en el enlace.  Si no se configura una dirección, se supone que la dirección base es la dirección para ese extremo.<br /><br /> El valor predeterminado es una cadena vacía.|  
|behaviorConfiguration|Una cadena que contiene el nombre del comportamiento que se va a utilizar en el extremo.|  
|enlace|Atributo de cadena necesario que especifica el tipo de enlace que se va a utilizar.  El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo.  El tipo es el registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.|  
|bindingConfiguration|Una cadena que especifica el nombre obligatorio del enlace que se utilizará cuando se creen las instancias del extremo.  El nombre de enlace debe estar en el ámbito en el punto definido del extremo.  El valor predeterminado es una cadena vacía.<br /><br /> Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración.  Establezca este atributo si está intentando utilizar un enlace personalizado.  De lo contrario, puede producirse una excepción.|  
|bindingName|Una cadena que especifica el nombre completo único del enlace para la exportación de la definición a través de WSDL.  El valor predeterminado es una cadena vacía.|  
|bindingNamespace|Una cadena que especifica el nombre completo del espacio de nombres del enlace para la exportación de la definición a través de WSDL.  El valor predeterminado es una cadena vacía.|  
|contrato|Una cadena que indica qué contrato está exponiendo este extremo.  El ensamblado debe implementar el tipo de contrato.  Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.  El valor predeterminado es una cadena vacía.|  
|endpointConfiguration|Cadena que especifica el nombre del extremo estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este extremo estándar.  El mismo nombre se debe definir en la sección `<standardEndpoints>`.|  
|isSystemEndpoint|Valor booleano que especifica si un extremo es un extremo de la infraestructura.|  
|kind|Cadena que especifica el tipo de extremo estándar aplicado.  El tipo se debe registrar en la sección `<extensions>` o en machine.config.  Si no se especifica nada, se crea un extremo de servicio común.|  
|listenUriMode|Especifica cómo el transporte trata el `ListenUri` proporcionado para el servicio en el que se realizan escuchas.  Los valores válidos son<br /><br /> -   Explicit<br />-   Unique<br /><br /> El valor predeterminado es Explicito.|  
|listenUri|Una cadena que especifica el URI en el que el extremo de servicio realiza escuchas.  El valor predeterminado es una cadena vacía.|  
|name|Atributo opcional.  Cadena que especifica el nombre del extremo del servicio.  El valor predeterminado es la concatenación del nombre de enlace y el nombre de la descripción de contrato.  Los servicios pueden tener varios extremos, por lo que el atributo `name` del extremo es distinto del nombre del servicio.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<encabezados\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Una colección de encabezados de dirección.|  
|[\<identidad\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Una identidad que habilita la autenticación de un extremo por otros extremos que intercambian mensajes con él.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<servicio\>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Una sección de configuración que define una lista de extremos a los que un cliente puede conectarse.|  
  
## Ejemplo  
 Éste es un ejemplo de una configuración del extremo de servicio.  
  
```  
<endpoint   
    address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    bindingName="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
    <Headers>  
       <Region xmlns="http://tempuri.org/">EastCoast</Region>  
       <Member xmlns="http://tempuri.org/">Gold</Member>  
    </Headers>  
</endpoint>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.Description.ServiceEndpoint>   
 [Extremos: direcciones, enlaces y contratos](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)   
 [Cómo crear un extremo de servicio en configuración](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)