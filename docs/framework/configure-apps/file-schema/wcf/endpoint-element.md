---
title: elemento de &lt;extremo&gt;
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: ea95e2d16027869778e99cb217d5ea4f7ba7d21a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147491"
---
# <a name="ltendpointgt-element"></a>elemento de &lt;extremo&gt;
Especifica enlace, contrato y propiedades de dirección para un punto de conexión de servicio, que se utiliza para exponer los servicios.  
  
 \<system.ServiceModel>  
\<servicio >  
\<punto de conexión >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|address|Una cadena que contiene la dirección del extremo. La dirección se puede especificar como una dirección absoluta o relativa. Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base adecuada para el esquema de transporte usado en el enlace. Si no se configura una dirección, se supone que la dirección base es la dirección para ese extremo.<br /><br /> El valor predeterminado es una cadena vacía.|  
|behaviorConfiguration|Una cadena que contiene el nombre del comportamiento que se va a utilizar en el extremo.|  
|enlace|Atributo de cadena necesario que especifica el tipo de enlace que se va a utilizar. El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo. El tipo es el registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.|  
|bindingConfiguration|Una cadena que especifica el nombre obligatorio del enlace que se utilizará cuando se creen las instancias del extremo. El nombre de enlace debe estar en el ámbito en el punto definido del extremo. El valor predeterminado es una cadena vacía.<br /><br /> Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración. Establezca este atributo si está intentando utilizar un enlace personalizado. De lo contrario, puede producirse una excepción.|  
|bindingName|Una cadena que especifica el nombre completo único del enlace para la exportación de la definición a través de WSDL. El valor predeterminado es una cadena vacía.|  
|bindingNamespace|Una cadena que especifica el nombre completo del espacio de nombres del enlace para la exportación de la definición a través de WSDL. El valor predeterminado es una cadena vacía.|  
|contrato|Una cadena que indica qué contrato está exponiendo este extremo. El ensamblado debe implementar el tipo de contrato. Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad. El valor predeterminado es una cadena vacía.|  
|endpointConfiguration|Cadena que especifica el nombre del extremo estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este extremo estándar. El mismo nombre se debe definir en la sección `<standardEndpoints>`.|  
|isSystemEndpoint|Valor booleano que especifica si un extremo es un extremo de la infraestructura.|  
|kind|Cadena que especifica el tipo de extremo estándar aplicado. El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un extremo de servicio común.|  
|listenUriMode|Especifica cómo el transporte trata el `ListenUri` proporcionado para el servicio en el que se realizan escuchas. Los valores válidos son<br /><br /> -Explícita<br />-Unique<br /><br /> El valor predeterminado es Explicito.|  
|listenUri|Una cadena que especifica el URI en el que el extremo de servicio realiza escuchas. El valor predeterminado es una cadena vacía.|  
|name|Atributo opcional. Cadena que especifica el nombre del extremo del servicio. El valor predeterminado es la concatenación del nombre de enlace y el nombre de la descripción de contrato. Los servicios pueden tener varios puntos de conexión, por lo que el atributo `name` del punto de conexión es distinto del nombre del servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<encabezados >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Una colección de encabezados de dirección.|  
|[\<identidad >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<servicio >](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.|  
  
## <a name="example"></a>Ejemplo  
 Éste es un ejemplo de una configuración del punto de conexión de servicio.  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.Description.ServiceEndpoint>  
 [Puntos de conexión: Las direcciones, enlaces y contratos](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [Cómo: Crear un punto de conexión de servicio en la configuración](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
