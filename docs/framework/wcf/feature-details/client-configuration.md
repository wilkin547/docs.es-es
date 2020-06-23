---
title: Configuración del cliente
description: Obtenga información sobre cómo usar la configuración de cliente de WCF para especificar la dirección, el enlace, el comportamiento y el contrato de un extremo, que se utiliza para conectarse a un servicio.
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: c3e3d4904bad39e951e8ba69013ac95894130489
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245380"
---
# <a name="client-configuration"></a>Configuración del cliente
Puede usar la configuración de cliente de Windows Communication Foundation (WCF) para especificar la dirección, el enlace, el comportamiento y el contrato, las propiedades "ABC" del punto de conexión del cliente, que los clientes utilizan para conectarse a los puntos de conexión de servicio. El [\<client>](../../configure-apps/file-schema/wcf/client.md) elemento tiene un [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento cuyos atributos se usan para configurar los ABC del extremo. Estos atributos se describen en la sección [configuración de puntos de conexión](#configuring-endpoints) .  
  
 El [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento también contiene un [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) elemento que se usa para especificar la configuración para importar y exportar metadatos, un [\<headers>](../../configure-apps/file-schema/wcf/headers.md) elemento que contiene una colección de encabezados de dirección personalizados y un [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elemento que habilita la autenticación de un extremo por otros extremos que intercambian mensajes con él. Los [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elementos y forman parte del <xref:System.ServiceModel.EndpointAddress> y se describen en el artículo [direcciones](endpoint-addresses.md) . Los vínculos a temas que explican el uso de las extensiones de metadatos se proporcionan en la sección [configuración de metadatos](#configuring-metadata) .  
  
## <a name="configuring-endpoints"></a>Configuración de puntos de conexión  
 La configuración del cliente está diseñada para permitir que el cliente especifique uno o más puntos de conexión, cada uno con su propio nombre, dirección y contrato, donde cada uno hace referencia a los [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elementos y de la configuración del cliente que se va a usar para configurar ese extremo. El archivo de configuración del cliente debe tener el nombre "App.config", ya que este es el nombre que espera el tiempo de ejecución de WCF. El siguiente ejemplo muestra un archivo de configuración de cliente.  
  
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
            <!-- Add another endpoint by adding another <endpoint> element. -->
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
          <!-- Configure this binding here. -->  
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
  
 El atributo opcional `name` identifica de manera única a un punto de conexión de un contrato determinado. Es utilizado por <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> para especificar qué extremo de la configuración del cliente se destina y se debe cargar cuando se crea un canal para el servicio. Hay disponible un nombre de configuración de punto de conexión de comodín " \* " que indica al <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> método que debe cargar cualquier configuración de extremo en el archivo, siempre que haya precisamente uno disponible y, de lo contrario, produzca una excepción. Si se omite este atributo, el punto de conexión correspondiente se usa como el punto de conexión predeterminado asociado al tipo de contrato especificado. El valor predeterminado para el atributo `name` es una cadena vacía que se iguala como cualquier otro nombre.  
  
 Cada punto de conexión debe tener una dirección asociada a él para ubicar e identificar el punto de conexión. El atributo `address` se puede utilizar para especificar la dirección URL que proporciona la ubicación del punto de conexión. Pero la dirección de un extremo de servicio también se puede especificar en código mediante la creación de un Identificador uniforme de recursos (URI) y se agrega al <xref:System.ServiceModel.ServiceHost> utilizando uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Para obtener más información, vea [Addresses](endpoint-addresses.md). Como indica la introducción, los [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elementos y forman parte de <xref:System.ServiceModel.EndpointAddress> y también se tratan en el tema [direcciones](endpoint-addresses.md) .  
  
 El atributo `binding` indica el tipo de enlace que el punto de conexión espera utilizar al conectarse a un servicio. El tipo debe tener una sección de configuración registrada si se le va a hacer referencia. En el ejemplo anterior, esta es la [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) sección, que indica que el extremo usa un <xref:System.ServiceModel.WSHttpBinding> . Pero puede que haya más de un enlace de un tipo determinado que el punto de conexión puede utilizar. Cada uno de ellos tiene su propio [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento dentro del elemento de tipo (enlace). El atributo `bindingconfiguration` se utiliza para distinguir entre enlaces del mismo tipo. Su valor coincide con el `name` atributo del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento. Para obtener más información sobre cómo configurar un enlace de cliente mediante la configuración, consulte [Cómo: especificar un enlace de cliente en la configuración](../how-to-specify-a-client-binding-in-configuration.md).  
  
 El `behaviorConfiguration` atributo se usa para especificar cuál [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) de los [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) extremos debe usar. Su valor coincide con el `name` atributo del [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento. Para obtener un ejemplo del uso de la configuración para especificar comportamientos de cliente, consulte [configuración de comportamientos de cliente](../configuring-client-behaviors.md).  
  
 El atributo `contract` especifica qué contrato expone este punto de conexión. Este valor se asigna al <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> del <xref:System.ServiceModel.ServiceContractAttribute>. El valor predeterminado es el nombre de tipo completo de la clase que implementa el servicio.  
  
### <a name="configuring-metadata"></a>Configuración de metadatos  
 El [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) elemento se usa para especificar la configuración que se usa para registrar las extensiones de importación de metadatos. Para obtener más información sobre cómo extender el sistema de metadatos, vea [extender el sistema de metadatos](../extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Vea también

- [Puntos de conexión: direcciones, enlaces y contratos](endpoints-addresses-bindings-and-contracts.md)
- [Configuración de los comportamientos del cliente](../configuring-client-behaviors.md)
