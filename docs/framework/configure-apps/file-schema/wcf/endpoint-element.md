---
title: <endpoint> (elemento)
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: befebc090900576b1e0f7ca679e1f5f5cd15af9a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183811"
---
# <a name="endpoint-element"></a>Elemento \<endpoint>

Especifica enlace, contrato y propiedades de dirección para un extremo de servicio, que se utiliza para exponer los servicios.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
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
|address|Una cadena que contiene la dirección del extremo. La dirección se puede especificar como una dirección absoluta o relativa. Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base adecuada para el esquema de transporte usado en el enlace. Si no se configura una dirección, se supone que la dirección base es la dirección para ese punto de conexión.<br /><br /> El valor predeterminado es una cadena vacía.|  
|behaviorConfiguration|Una cadena que contiene el nombre del comportamiento que se va a utilizar en el extremo.|  
|binding|Atributo de cadena necesario que especifica el tipo de enlace que se va a utilizar. El tipo debe tener una sección de configuración registrada para que se haga referencia al mismo. El tipo es el registrado por el nombre de sección, en lugar de por el nombre de tipo del enlace.|  
|bindingConfiguration|Una cadena que especifica el nombre obligatorio del enlace que se utilizará cuando se creen las instancias del extremo. El nombre de enlace debe estar en el ámbito en el punto definido del extremo. El valor predeterminado es una cadena vacía.<br /><br /> Este atributo se utiliza junto con `binding` para hacer referencia a una configuración de enlace concreta en el archivo de configuración. Establezca este atributo si está intentando utilizar un enlace personalizado. De lo contrario, puede producirse una excepción.|  
|bindingName|Una cadena que especifica el nombre completo único del enlace para la exportación de la definición a través de WSDL. El valor predeterminado es una cadena vacía.|  
|bindingNamespace|Una cadena que especifica el nombre completo del espacio de nombres del enlace para la exportación de la definición a través de WSDL. El valor predeterminado es una cadena vacía.|  
|contrato|Una cadena que indica qué contrato está exponiendo este punto de conexión. El ensamblado debe implementar el tipo de contrato. Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad. El valor predeterminado es una cadena vacía.|  
|endpointConfiguration|Cadena que especifica el nombre del punto de conexión estándar establecido por el atributo `kind`, que hace referencia a la información de configuración adicional de este punto de conexión estándar. El mismo nombre se debe definir en la sección `<standardEndpoints>`.|  
|isSystemEndpoint|Valor booleano que especifica si un punto de conexión es un punto de conexión de la infraestructura.|  
|kind|Cadena que especifica el tipo de extremo estándar aplicado. El tipo se debe registrar en la sección `<extensions>` o en machine.config. Si no se especifica nada, se crea un punto de conexión de servicio común.|  
|listenUriMode|Especifica cómo el transporte trata el `ListenUri` proporcionado para el servicio en el que se realizan escuchas. Los valores válidos son<br /><br /> -Explicit<br />-Único<br /><br /> El valor predeterminado es Explicito.|  
|listenUri|Una cadena que especifica el URI en el que el extremo de servicio realiza escuchas. El valor predeterminado es una cadena vacía.|  
|name|Atributo opcional. Cadena que especifica el nombre del punto de conexión del servicio. El valor predeterminado es la concatenación del nombre de enlace y el nombre de la descripción de contrato. Los servicios pueden tener varios puntos de conexión, por lo que el atributo `name` del punto de conexión es distinto del nombre del servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<headers>](headers.md)|Una colección de encabezados de dirección.|  
|[\<identity>](identity.md)|Una identidad que habilita la autenticación de un punto de conexión por otros puntos de conexión que intercambian mensajes con él.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<service>](service.md)|Una sección de configuración que define una lista de puntos de conexión a los que un cliente puede conectarse.|  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [Puntos de conexión: direcciones, enlaces y contratos](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Procedimiento para crear un punto de conexión de servicio en la configuración](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
