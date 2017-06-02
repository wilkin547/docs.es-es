---
title: "Configuraci&#243;n del cliente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Configuraci&#243;n del cliente
Puede utilizar la configuración de cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para especificar la dirección, enlace, comportamiento y contrato, las propiedades "ABC" del extremo del cliente, que los clientes utilizan para conectarse a los extremos del servicio.  El elemento [\<cliente\>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) tiene un elemento [\<endpoint\>](http://msdn.microsoft.com/es-es/13aa23b7-2f08-4add-8dbf-a99f8127c017) cuyos atributos se usan para configurar los ABC del extremo.  Estos atributos se discuten en la sección “Configuración de extremos” de este tema.  
  
 El elemento [\<endpoint\>](http://msdn.microsoft.com/es-es/13aa23b7-2f08-4add-8dbf-a99f8127c017) también contiene un elemento [\<metadatos\>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) que se usa para especificar la configuración para importar y exportar metadatos, un elemento [\<encabezados\>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) que contiene una colección de encabezados de dirección personalizados y un elemento [\<identidad\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) que permita la autenticación de un extremo por otros extremos que intercambias mensajes con él.  Los elementos [\<encabezados\>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) e [\<identidad\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) forman parte de <xref:System.ServiceModel.EndpointAddress> y se tratan en el tema [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).  En la subsección Configuración de metadatos de este tema se proporcionan vínculos a temas que explican el uso de extensiones de metadatos.  
  
## Configuración de extremos  
 La configuración del cliente está diseñada para permitir que el cliente especifique uno o varios extremos, cada uno con su propio nombre, dirección y contrato, y con cada uno haciendo referencia a los elementos [\<enlaces\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) y [\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) de la configuración de cliente que se usará para configurar dicho extremo.  El archivo de configuración del cliente debería llamarse "App.config", porque se trata del nombre que el tiempo de ejecución de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espera.  El siguiente ejemplo muestra un archivo de configuración de cliente.  
  
```  
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
  
 El atributo opcional `name` identifica de manera única a un extremo de un contrato determinado.  Es utilizado por <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> para especificar qué extremo de la configuración del cliente se destina y se debe cargar cuando se crea un canal para el servicio.  Hay disponible un nombre de configuración de extremo de comodín "\*" e indica al método <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> que debería cargar cualquier configuración de extremo del archivo, suponiendo que haya precisamente uno disponible o, si no fuese así, produjese una excepción.  Si se omite este atributo, el extremo correspondiente se usa como el extremo predeterminado asociado al tipo de contrato especificado.  El valor predeterminado para el atributo `name` es una cadena vacía que se iguala como cualquier otro nombre.  
  
 Cada extremo debe tener una dirección asociada a él para ubicar e identificar el extremo.  El atributo `address` se puede utilizar para especificar la dirección URL que proporciona la ubicación del extremo.  Pero la dirección de un extremo de servicio también se puede especificar en código mediante la creación de un Identificador uniforme de recursos \(URI\) y se agrega al <xref:System.ServiceModel.ServiceHost> utilizando uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).  Como indica la introducción, los elementos [\<encabezados\>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) e [\<identidad\>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) forman parte de <xref:System.ServiceModel.EndpointAddress> y también se tratan en el tema [Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).  
  
 El atributo `binding` indica el tipo de enlace que el extremo espera utilizar al conectarse a un servicio.  El tipo debe tener una sección de configuración registrada si se le va a hacer referencia.  En el ejemplo anterior, esta es la sección [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), que indica que el extremo usa un <xref:System.ServiceModel.WSHttpBinding>.  Pero puede que haya más de un enlace de un tipo determinado que el extremo puede utilizar.  Cada uno de ellos tiene su propio elemento [\<enlace\>](../../../../docs/framework/misc/binding.md) dentro del elemento de tipo \(enlace\).  El atributo `bindingconfiguration` se utiliza para distinguir entre enlaces del mismo tipo.  Su valor coincide con el atributo `name` del elemento [\<enlace\>](../../../../docs/framework/misc/binding.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo configurar un enlace de cliente con la configuración, consulte [Cómo: Especificar un enlace de cliente en la configuración](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).  
  
 El atributo `behaviorConfiguration` se usa para especificar qué [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) de [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) debe usar el extremo.  Su valor coincide con el atributo `name` del elemento [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).  Para obtener un ejemplo del uso de la configuración para especificar comportamientos del cliente, consulte [Configuración de los comportamientos del cliente](../../../../docs/framework/wcf/configuring-client-behaviors.md).  
  
 El atributo `contract` especifica qué contrato expone este extremo.  Este valor se asigna al <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> del <xref:System.ServiceModel.ServiceContractAttribute>.  El valor predeterminado es el nombre de tipo completo de la clase que implementa el servicio.  
  
### Configuración de metadatos  
 El elemento [\<metadatos\>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) se usa para especificar la configuración para registrar las extensiones de importación de metadatos.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] extender el sistema de metadatos, consulte [Extensión del sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).  
  
## Vea también  
 [Extremos: direcciones, enlaces y contratos](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)   
 [Configuración de los comportamientos del cliente](../../../../docs/framework/wcf/configuring-client-behaviors.md)