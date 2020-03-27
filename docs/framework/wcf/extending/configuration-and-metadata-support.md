---
title: Compatibilidad con metadatos y configuración
ms.date: 03/30/2017
ms.assetid: 27c240cb-8cab-472c-87f8-c864f4978758
ms.openlocfilehash: fb4e1cc51b827f083e580362f57df27ced770179
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345297"
---
# <a name="configuration-and-metadata-support"></a>Compatibilidad con metadatos y configuración
En este tema se describe cómo habilitar la compatibilidad con configuración y metadatos para los enlaces y elementos de enlaces.  
  
## <a name="overview-of-configuration-and-metadata"></a>Información general de configuración y metadatos  
 En este tema se describen las tareas siguientes, que son los elementos opcionales 1, 2 y 4 de la lista de tareas [Canales](developing-channels.md) de desarrollo.  
  
- Habilitación de la compatibilidad con archivos de configuración para un elemento de enlace.  
  
- Habilitación de la compatibilidad con archivos de configuración para un enlace.  
  
- Exportación de WSDL y aserciones de directivas para un elemento de enlace.  
  
- Identificación de WSDL y aserciones de directivas para insertar y configurar su enlace o elemento de enlace.  
  
 Para obtener información acerca de cómo crear enlaces definidos por el usuario y elementos de enlace, vea [crear enlaces definidos por](creating-user-defined-bindings.md) el usuario y [crear un BindingElement](creating-a-bindingelement.md), respectivamente.  
  
## <a name="adding-configuration-support"></a>Agregación de la compatibilidad de configuración  
 Para habilitar la compatibilidad con archivos de configuración para un canal, debe implementar dos secciones de configuración, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, que habilita la compatibilidad de configuración para los elementos de enlace, y <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> y <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, que habilitan la compatibilidad de configuración para los enlaces.  
  
 Una manera más fácil de hacerlo es usar la herramienta de ejemplo [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) para generar código de configuración para los enlaces y elementos de enlace.  
  
### <a name="extending-bindingelementextensionelement"></a>Extender BindingElementExtensionElement  
 El siguiente código de ejemplo se toma del ejemplo [Transport: UDP.](../samples/transport-udp.md) El elemento `UdpTransportElement` es una clase <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> que expone `UdpTransportBindingElement` en el sistema de configuración. Con unas pocas invalidaciones básicas, el ejemplo define el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace. Los usuarios pueden registrar a continuación la sección de extensión en un archivo de configuración de la siguiente manera.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <bindingElementExtensions>  
      <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportElement, UdpTransport" />  
      </bindingElementExtensions>  
    </extensions>  
  </system.serviceModel>  
</configuration>  
```  
  
 Se puede hacer referencia a la extensión desde enlaces personalizados para utilizar UDP como el transporte.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <customBinding>  
       <binding configurationName="UdpCustomBinding">  
         <udpTransport/>  
       </binding>  
      </customBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="adding-configuration-for-a-binding"></a>Agregación de la configuración para un enlace  
 La sección `SampleProfileUdpBindingCollectionElement` es un objeto <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> que expone `SampleProfileUdpBinding` en el sistema de configuración. El volumen de la implementación se delega a `SampleProfileUdpBindingConfigurationElement`, que deriva de <xref:System.ServiceModel.Configuration.StandardBindingElement>. Tiene `SampleProfileUdpBindingConfigurationElement` propiedades que corresponden a `SampleProfileUdpBinding`las propiedades en `ConfigurationElement` , y funciones para asignar desde el enlace. Finalmente, el método `OnApplyConfiguration` es invalidado en el `SampleProfileUdpBinding`, tal y como se muestra en el siguiente código muestra.  
  
```csharp
protected override void OnApplyConfiguration(string configurationName)  
{  
            if (binding == null)  
                throw new ArgumentNullException("binding");  
  
            if (binding.GetType() != typeof(SampleProfileUdpBinding))  
            {  
                var expectedType = typeof(SampleProfileUdpBinding).AssemblyQualifiedName;
                var typePassedIn = binding.GetType().AssemblyQualifiedName;
                throw new ArgumentException($"Invalid type for binding. Expected type: {expectedType}. Type passed in: {typePassedIn}.");  
            }  
            SampleProfileUdpBinding udpBinding = (SampleProfileUdpBinding)binding;  
  
            udpBinding.OrderedSession = this.OrderedSession;  
            udpBinding.ReliableSessionEnabled = this.ReliableSessionEnabled;  
            udpBinding.SessionInactivityTimeout = this.SessionInactivityTimeout;  
            if (this.ClientBaseAddress != null)  
                   udpBinding.ClientBaseAddress = ClientBaseAddress;  
}  
```  
  
 Para registrar este controlador con el sistema de configuración, agregue la siguiente sección al archivo de configuración pertinente.  
  
```xml  
<configuration>  
  <configSections>  
     <sectionGroup name="system.serviceModel">  
         <sectionGroup name="bindings">  
                 <section name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
         </sectionGroup>  
     </sectionGroup>  
  </configSections>  
</configuration>  
```  
  
 A continuación, se [ \<](../../configure-apps/file-schema/wcf/system-servicemodel.md) puede hacer referencia a él desde la sección de configuración system.serviceModel>.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <endpoint configurationName="calculator"  
                address="soap.udp://localhost:8001/"
                bindingConfiguration="CalculatorServer"  
                binding="sampleProfileUdpBinding"
                contract= "Microsoft.ServiceModel.Samples.ICalculatorContract">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="adding-metadata-support-for-a-binding-element"></a>Agregación de compatibilidad con metadatos para un elemento de enlace  
 Para integrar un canal en el sistema de metadatos, debe admitir la importación y exportación de la directiva. Esto permite que herramientas como [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generen clientes del elemento de enlace.  
  
### <a name="adding-wsdl-support"></a>Agregación de la compatibilidad con WSDL  
 El elemento de enlace del transporte en un enlace es el responsable de la exportación e importación de la información de direccionamiento en metadatos. Al utilizar un enlace SOAP, el elemento de enlace del transporte también debería exportar un URI de transporte correcto en los metadatos. El siguiente código de ejemplo se toma del ejemplo [Transport: UDP.](../samples/transport-udp.md)  
  
#### <a name="wsdl-export"></a>Exportación de WSDL  
 Para exportar información `UdpTransportBindingElement` de direccionamiento, implementa la <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interfaz. El método <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> agrega la información de direccionamiento correcta al puerto WSDL.  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 La implementación `UdpTransportBindingElement` del método <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> también exporta un URI de transporte cuando el punto de conexión utiliza un enlace SOAP:  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a>Importación de WSDL  
 Para extender el sistema de importación de WSDL para que administre la importación de las direcciones, agregue la configuración siguiente al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <wsdlImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </wsdlImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 Al ejecutar Svcutil.exe, hay dos opciones para conseguir que Svcutil.exe cargue las extensiones de importación de WSDL:  
  
1. Apunte Svcutil.exe al archivo de configuración\<mediante el archivo /SvcutilConfig:>.  
  
2. Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.  
  
 El tipo `UdpBindingElementImporter` implementa la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>. El método `ImportEndpoint` importa la dirección del puerto del WSDL:  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a>Agregación de compatibilidad de directiva  
 El elemento de enlace personalizado puede exportar aserciones de directiva en el enlace de WSDL para que un extremo de servicio exprese las funciones de ese elemento de enlace. El siguiente código de ejemplo se toma del ejemplo [Transport: UDP.](../samples/transport-udp.md)  
  
#### <a name="policy-export"></a>Exportación de directivas  
 El `UdpTransportBindingElement` tipo <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> se implementa para agregar compatibilidad para la exportación de directivas. Como resultado, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> incluye `UdpTransportBindingElement` en la generación de directiva para cualquier enlace que la incluya.  
  
 En <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, agregue una aserción para UDP y otra aserción si el canal está en modo de multidifusión. Esto se debe a que el modo de multidifusión afecta a cómo se construye la pila de comunicaciones, y, por tanto, debe coordinarse entre ambos lados.  
  
```csharp  
ICollection<XmlElement> bindingAssertions = context.GetBindingAssertions();  
XmlDocument xmlDocument = new XmlDocument();  
bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.TransportAssertion, UdpPolicyStrings.UdpNamespace));  
if (Multicast)  
{  
    bindingAssertions.Add(xmlDocument.CreateElement(  
UdpPolicyStrings.Prefix, UdpPolicyStrings.MulticastAssertion,     UdpPolicyStrings.UdpNamespace));  
}  
```  
  
 Dado que los elementos de enlace de transporte personalizados son responsables de la administración del direccionamiento, la implementación <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> en el `UdpTransportBindingElement` también debe administrar la exportación de las aserciones de directivas WS-Addressing adecuadas para indicar la versión de WS-Addressing que se está utilizando.  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a>Importación de directivas  
 Para extender el sistema de importación de directivas, agregue la siguiente configuración al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <metadata>  
        <policyImporters>  
          <extension type=" Microsoft.ServiceModel.Samples.UdpBindingElementImporter, UdpTransport" />  
        </policyImporters>  
      </metadata>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
 A continuación, implementamos <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> desde nuestra clase registrada (`UdpBindingElementImporter`). En <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine las aserciones en el espacio de nombres adecuado y procese las que se encargan de la generación del transporte y de la comprobación de si es multidifusión. Además, elimine las aserciones que el importador administra desde la lista de aserciones de enlaces. De nuevo, al ejecutar Svcutil.exe, hay dos opciones para la integración:  
  
1. Apunte Svcutil.exe a nuestro archivo de\<configuración mediante el> de archivo /SvcutilConfig:.  
  
2. Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.  
  
### <a name="adding-a-custom-standard-binding-importer"></a>Agregación de un importador de enlace estándar personalizado  
 Svcutil.exe y el tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>, de forma predeterminada, reconocen e importan los enlaces proporcionados por el sistema. De lo contrario, el enlace se importa como una instancia <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>. Para permitir que Svcutil.exe y <xref:System.ServiceModel.Description.WsdlImporter> importen el `SampleProfileUdpBinding`, el `UdpBindingElementImporter` actúa también como un importador de enlaces estándar personalizado.  
  
 Un importador de enlace `ImportEndpoint` estándar personalizado <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> implementa el <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> método en la interfaz para examinar la instancia importada de metadatos para ver si podría haber sido generada por un enlace estándar específico.  
  
```csharp  
if (context.Endpoint.Binding is CustomBinding)  
{  
    Binding binding;  
    if (transportBindingElement is UdpTransportBindingElement)  
    {  
        //if TryCreate is true, the CustomBinding will be replace by a SampleProfileUdpBinding in the  
        //generated config file for better typed generation.  
        if (SampleProfileUdpBinding.TryCreate(bindingElements, out binding))  
        {  
            binding.Name = context.Endpoint.Binding.Name;  
            binding.Namespace = context.Endpoint.Binding.Namespace;  
            context.Endpoint.Binding = binding;  
        }  
    }  
}  
```  
  
 Generalmente, la implementación de un importador de enlaces estándar personalizado, implica la comprobación de las propiedades de los elementos de enlace importados para comprobar que solo las propiedades que pudo establecer el enlace estándar han cambiado y el resto propiedades son sus valores predeterminados. Una estrategia básica para implementar un importador de enlace estándar consiste en crear una instancia de enlace estándar, propagar las propiedades desde los elementos de enlace a la instancia de enlace estándar que admite enlaces estándar y, a continuación, comparar los elementos de enlace desde el enlace estándar con los elementos de enlace importados.
