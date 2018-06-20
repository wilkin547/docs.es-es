---
title: Configuración del cliente
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 26557b6cbbe33626152878eccab62de11d22660d
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207422"
---
# <a name="client-configuration"></a>Configuración del cliente
Puede usar la configuración de cliente de Windows Communication Foundation (WCF) para especificar la dirección, enlace, comportamiento y contrato, las propiedades "ABC" del punto de conexión de cliente, que los clientes utilizan para conectarse a los extremos de servicio. El [ \<cliente >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento tiene un [ \<extremo >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento cuyos atributos se utilizan para configurar los ABC del extremo. Estos atributos se discuten en la sección “Configuración de puntos de conexión” de este tema.  
  
 El [ \<extremo >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento también contiene un [ \<metadatos >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento que se utiliza para especificar la configuración para la importación y exportación de metadatos, un [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) elemento que contiene una colección de encabezados de dirección personalizados y un [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento que habilita la autenticación de un extremo por otros puntos de conexión intercambiar mensajes con él. El [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) y [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementos forman parte de la <xref:System.ServiceModel.EndpointAddress> y se describen en la [direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) tema. En la subsección Configuración de metadatos de este tema se proporcionan vínculos a temas que explican el uso de extensiones de metadatos.  
  
## <a name="configuring-endpoints"></a>Configuración de puntos de conexión  
 La configuración del cliente está diseñada para permitir que el cliente especificar uno o más extremos, cada uno con su propio nombre, dirección y contrato, con cada referencia a la [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) y [ \< comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementos en la configuración del cliente que se usará para configurar dicho extremo. El archivo de configuración de cliente debe denominarse "App.config" porque se trata del nombre que espera el tiempo de ejecución WCF. El siguiente ejemplo muestra un archivo de configuración de cliente.  
  
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
  
 El atributo opcional `name` identifica de manera única a un extremo de un contrato determinado. Es utilizado por <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> para especificar qué extremo de la configuración del cliente se destina y se debe cargar cuando se crea un canal para el servicio. Hay disponible un nombre de configuración de extremo de comodín "*" e indica al método <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> que debería cargar cualquier configuración de extremo del archivo, suponiendo que haya precisamente uno disponible o, si no fuese así, produjese una excepción. Si se omite este atributo, el extremo correspondiente se usa como el extremo predeterminado asociado al tipo de contrato especificado. El valor predeterminado para el atributo `name` es una cadena vacía que se iguala como cualquier otro nombre.  
  
 Cada extremo debe tener una dirección asociada a él para ubicar e identificar el extremo. El atributo `address` se puede utilizar para especificar la dirección URL que proporciona la ubicación del extremo. Pero la dirección de un extremo de servicio también se puede especificar en código mediante la creación de un Identificador uniforme de recursos (URI) y se agrega al <xref:System.ServiceModel.ServiceHost> utilizando uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>. Para obtener más información, consulte [direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md). Tal y como se indica en la introducción, el [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) y [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementos forman parte de la <xref:System.ServiceModel.EndpointAddress> y también se describen en la [ Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) tema.  
  
 El atributo `binding` indica el tipo de enlace que el extremo espera utilizar al conectarse a un servicio. El tipo debe tener una sección de configuración registrada si se le va a hacer referencia. En el ejemplo anterior, se trata de la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) sección, que indica que el punto de conexión usa un <xref:System.ServiceModel.WSHttpBinding>. Pero puede que haya más de un enlace de un tipo determinado que el punto de conexión puede utilizar. Cada uno de ellos tiene su propio [ \<enlace >](../../../../docs/framework/misc/binding.md) dentro del elemento de tipo (enlace). El atributo `bindingconfiguration` se utiliza para distinguir entre enlaces del mismo tipo. Su valor coincide con el `name` atributo de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento. Para obtener más información acerca de cómo configurar un cliente de enlace con la configuración, consulte [Cómo: especificar un enlace de cliente en configuración](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 El `behaviorConfiguration` atributo se usa para especificar qué [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) de la [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) debe utilizar el punto de conexión. Su valor coincide con el `name` atributo de la [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento. Para obtener un ejemplo de usar la configuración para especificar los comportamientos del cliente, consulte [configurar comportamientos del cliente](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 El atributo `contract` especifica qué contrato expone este extremo. Este valor se asigna al <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> del <xref:System.ServiceModel.ServiceContractAttribute>. El valor predeterminado es el nombre de tipo completo de la clase que implementa el servicio.  
  
### <a name="configuring-metadata"></a>Configuración de metadatos  
 El [ \<metadatos >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento se utiliza para especificar la configuración que se usa para registrar metadatos de las extensiones de importación. Para obtener más información sobre cómo extender el sistema de metadatos, vea [extender el sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## <a name="see-also"></a>Vea también  
 [Puntos de conexión: direcciones, enlaces y contratos](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [Configuración de los comportamientos del cliente](../../../../docs/framework/wcf/configuring-client-behaviors.md)
