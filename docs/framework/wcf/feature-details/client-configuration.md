---
title: Configuración del cliente
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: ff82f56639ec451c04624d22fff0bcb03f46d946
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185365"
---
# <a name="client-configuration"></a>Configuración del cliente
Puede usar la configuración de cliente de Windows Communication Foundation (WCF) para especificar la dirección, el enlace, el comportamiento y el contrato, las propiedades "ABC" del extremo de cliente, que los clientes usan para conectarse a los extremos de servicio. El [ \<](../../configure-apps/file-schema/wcf/client.md) elemento de [ \<](../../configure-apps/file-schema/wcf/endpoint-of-client.md)>de cliente tiene un elemento de extremo>cuyos atributos se utilizan para configurar los ABC de punto de conexión. Estos atributos se discuten en la sección [Configuración de los puntos finales.](#configuring-endpoints)  
  
 El [ \<elemento de extremo>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) también contiene un [ \<](../../configure-apps/file-schema/wcf/metadata.md) elemento de>de metadatos que se usa para especificar la configuración para importar y exportar metadatos, un [ \<elemento>de encabezados](../../configure-apps/file-schema/wcf/headers.md) que contiene una colección de encabezados de dirección personalizados y un [ \<](../../configure-apps/file-schema/wcf/identity.md) elemento de>de identidad que permite la autenticación de un punto de conexión por otros extremos que intercambian mensajes con él. Los [ \<encabezados>](../../configure-apps/file-schema/wcf/headers.md) y [ \<los](../../configure-apps/file-schema/wcf/identity.md) elementos de>de identidad forman parte de los <xref:System.ServiceModel.EndpointAddress> elementos y se describen en el artículo [Direcciones.](../../wcf/feature-details/endpoint-addresses.md) Los vínculos a temas que explican el uso de extensiones de metadatos se proporcionan en la sección [Configuración de metadatos.](#configuring-metadata)  
  
## <a name="configuring-endpoints"></a>Configuración de puntos de conexión  
 La configuración del cliente está diseñada para permitir que el cliente especifique uno o varios extremos, cada uno con su propio nombre, dirección y contrato, haciendo referencia a los [ \<enlaces>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) y [ \<comportamientos>elementos](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) de la configuración de cliente que se usará para configurar ese extremo. El archivo de configuración de cliente debe llamarse "App.config" porque este es el nombre que espera el tiempo de ejecución de WCF. El siguiente ejemplo muestra un archivo de configuración de cliente.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 El atributo opcional `name` identifica de manera única a un punto de conexión de un contrato determinado. Es utilizado por <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> para especificar qué extremo de la configuración del cliente se destina y se debe cargar cuando se crea un canal para el servicio. Un nombre de\*configuración de punto de <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> conexión comodín " " está disponible e indica al método que debe cargar cualquier configuración de punto final en el archivo, siempre que haya precisamente uno disponible y, de lo contrario, produce una excepción. Si se omite este atributo, el punto de conexión correspondiente se usa como el punto de conexión predeterminado asociado al tipo de contrato especificado. El valor predeterminado para el atributo `name` es una cadena vacía que se iguala como cualquier otro nombre.  
  
 Cada punto de conexión debe tener una dirección asociada a él para ubicar e identificar el punto de conexión. El atributo `address` se puede utilizar para especificar la dirección URL que proporciona la ubicación del punto de conexión. Pero la dirección de un extremo de servicio también se puede especificar en código mediante la creación de un Identificador uniforme de recursos (URI) y se agrega al <xref:System.ServiceModel.ServiceHost> utilizando uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Para obtener más información, consulte [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Como indica la introducción, los [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) [ \<encabezados>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) y <xref:System.ServiceModel.EndpointAddress> los elementos de>de identidad forman parte de los elementos y también se describen en el tema [Direcciones.](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)  
  
 El atributo `binding` indica el tipo de enlace que el punto de conexión espera utilizar al conectarse a un servicio. El tipo debe tener una sección de configuración registrada si se le va a hacer referencia. En el ejemplo anterior, se trata de la <xref:System.ServiceModel.WSHttpBinding> [ \<sección de>wsHttpBinding,](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) que indica que el punto de conexión utiliza un archivo . Pero puede que haya más de un enlace de un tipo determinado que el punto de conexión puede utilizar. Cada uno de [ \<](../../configure-apps/file-schema/wcf/bindings.md) ellos tiene su propio elemento de enlace>dentro del elemento de tipo (binding). El atributo `bindingconfiguration` se utiliza para distinguir entre enlaces del mismo tipo. Su valor coincide con `name` el atributo del [ \<elemento>](../../configure-apps/file-schema/wcf/bindings.md) de enlace. Para obtener más información acerca de cómo configurar un enlace de cliente mediante la configuración, vea [Cómo: especificar un enlace](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)de cliente en la configuración .  
  
 El `behaviorConfiguration` atributo se utiliza [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) para especificar qué comportamiento>del [ \<punto de conexión que debe](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) usar>el punto de conexión. Su valor coincide con `name` el atributo del [ \<elemento>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) de comportamiento. Para obtener un ejemplo del uso de la configuración para especificar comportamientos de cliente, consulte Configuración de [comportamientos](../../../../docs/framework/wcf/configuring-client-behaviors.md)de cliente .  
  
 El atributo `contract` especifica qué contrato expone este punto de conexión. Este valor se asigna al <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> del <xref:System.ServiceModel.ServiceContractAttribute>. El valor predeterminado es el nombre de tipo completo de la clase que implementa el servicio.  
  
### <a name="configuring-metadata"></a>Configuración de metadatos  
 El [ \<elemento de>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) de metadatos se utiliza para especificar la configuración utilizada para registrar las extensiones de importación de metadatos. Para obtener más información sobre cómo ampliar el sistema de metadatos, consulte Extending the Metadata System ( [Extending the Metadata System ).](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
  
## <a name="see-also"></a>Consulte también

- [Puntos de conexión: direcciones, enlaces y contratos](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [Configuración de los comportamientos del cliente](../../../../docs/framework/wcf/configuring-client-behaviors.md)
