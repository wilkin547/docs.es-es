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
# <a name="configuration-and-metadata-support"></a><span data-ttu-id="963c2-102">Compatibilidad con metadatos y configuración</span><span class="sxs-lookup"><span data-stu-id="963c2-102">Configuration and Metadata Support</span></span>
<span data-ttu-id="963c2-103">En este tema se describe cómo habilitar la compatibilidad con configuración y metadatos para los enlaces y elementos de enlaces.</span><span class="sxs-lookup"><span data-stu-id="963c2-103">This topic describes how to enable configuration and metadata support for bindings and binding elements.</span></span>  
  
## <a name="overview-of-configuration-and-metadata"></a><span data-ttu-id="963c2-104">Información general de configuración y metadatos</span><span class="sxs-lookup"><span data-stu-id="963c2-104">Overview of Configuration and Metadata</span></span>  
 <span data-ttu-id="963c2-105">En este tema se describen las tareas siguientes, que son los elementos opcionales 1, 2 y 4 de la lista de tareas [Canales](developing-channels.md) de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="963c2-105">This topic discusses the following tasks, which are optional items 1, 2, and 4 in the [Developing Channels](developing-channels.md) task list.</span></span>  
  
- <span data-ttu-id="963c2-106">Habilitación de la compatibilidad con archivos de configuración para un elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-106">Enabling configuration file support for a binding element.</span></span>  
  
- <span data-ttu-id="963c2-107">Habilitación de la compatibilidad con archivos de configuración para un enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-107">Enabling configuration file support for a binding.</span></span>  
  
- <span data-ttu-id="963c2-108">Exportación de WSDL y aserciones de directivas para un elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-108">Exporting WSDL and policy assertions for a binding element.</span></span>  
  
- <span data-ttu-id="963c2-109">Identificación de WSDL y aserciones de directivas para insertar y configurar su enlace o elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-109">Identifying WSDL and policy assertions to insert and configure your binding or binding element.</span></span>  
  
 <span data-ttu-id="963c2-110">Para obtener información acerca de cómo crear enlaces definidos por el usuario y elementos de enlace, vea [crear enlaces definidos por](creating-user-defined-bindings.md) el usuario y [crear un BindingElement](creating-a-bindingelement.md), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="963c2-110">For information about creating user-defined bindings and binding elements, see [Creating User-Defined Bindings](creating-user-defined-bindings.md) and [Creating a BindingElement](creating-a-bindingelement.md), respectively.</span></span>  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="963c2-111">Agregación de la compatibilidad de configuración</span><span class="sxs-lookup"><span data-stu-id="963c2-111">Adding Configuration Support</span></span>  
 <span data-ttu-id="963c2-112">Para habilitar la compatibilidad con archivos de configuración para un canal, debe implementar dos secciones de configuración, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, que habilita la compatibilidad de configuración para los elementos de enlace, y <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> y <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, que habilitan la compatibilidad de configuración para los enlaces.</span><span class="sxs-lookup"><span data-stu-id="963c2-112">To enable configuration file support for a channel, you must implement two configuration sections, <xref:System.ServiceModel.Configuration.BindingElementExtensionElement?displayProperty=nameWithType>, which enables configuration support for binding elements, and the <xref:System.ServiceModel.Configuration.StandardBindingElement?displayProperty=nameWithType> and <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602?displayProperty=nameWithType>, which enable configuration support for bindings.</span></span>  
  
 <span data-ttu-id="963c2-113">Una manera más fácil de hacerlo es usar la herramienta de ejemplo [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) para generar código de configuración para los enlaces y elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-113">An easier way to do this is to use the [ConfigurationCodeGenerator](../samples/configurationcodegenerator.md) sample tool to generate configuration code for your bindings and binding elements.</span></span>  
  
### <a name="extending-bindingelementextensionelement"></a><span data-ttu-id="963c2-114">Extender BindingElementExtensionElement</span><span class="sxs-lookup"><span data-stu-id="963c2-114">Extending BindingElementExtensionElement</span></span>  
 <span data-ttu-id="963c2-115">El siguiente código de ejemplo se toma del ejemplo [Transport: UDP.](../samples/transport-udp.md)</span><span class="sxs-lookup"><span data-stu-id="963c2-115">The following example code is taken from the [Transport: UDP](../samples/transport-udp.md) sample.</span></span> <span data-ttu-id="963c2-116">El elemento `UdpTransportElement` es una clase <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> que expone `UdpTransportBindingElement` en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="963c2-116">The `UdpTransportElement` is a <xref:System.ServiceModel.Configuration.BindingElementExtensionElement> that exposes `UdpTransportBindingElement` to the configuration system.</span></span> <span data-ttu-id="963c2-117">Con unas pocas invalidaciones básicas, el ejemplo define el nombre de la sección de configuración, el tipo del elemento de enlace y cómo crear el elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-117">With a few basic overrides, the sample defines the configuration section name, the type of the binding element and how to create the binding element.</span></span> <span data-ttu-id="963c2-118">Los usuarios pueden registrar a continuación la sección de extensión en un archivo de configuración de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="963c2-118">Users can then register the extension section in a configuration file as follows.</span></span>  
  
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
  
 <span data-ttu-id="963c2-119">Se puede hacer referencia a la extensión desde enlaces personalizados para utilizar UDP como el transporte.</span><span class="sxs-lookup"><span data-stu-id="963c2-119">The extension can be referenced from custom bindings to use UDP as the transport.</span></span>  
  
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
  
### <a name="adding-configuration-for-a-binding"></a><span data-ttu-id="963c2-120">Agregación de la configuración para un enlace</span><span class="sxs-lookup"><span data-stu-id="963c2-120">Adding Configuration for a Binding</span></span>  
 <span data-ttu-id="963c2-121">La sección `SampleProfileUdpBindingCollectionElement` es un objeto <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> que expone `SampleProfileUdpBinding` en el sistema de configuración.</span><span class="sxs-lookup"><span data-stu-id="963c2-121">The section `SampleProfileUdpBindingCollectionElement` is a <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> that exposes `SampleProfileUdpBinding` to the configuration system.</span></span> <span data-ttu-id="963c2-122">El volumen de la implementación se delega a `SampleProfileUdpBindingConfigurationElement`, que deriva de <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="963c2-122">The bulk of the implementation is delegated to the `SampleProfileUdpBindingConfigurationElement`, which derives from <xref:System.ServiceModel.Configuration.StandardBindingElement>.</span></span> <span data-ttu-id="963c2-123">Tiene `SampleProfileUdpBindingConfigurationElement` propiedades que corresponden a `SampleProfileUdpBinding`las propiedades en `ConfigurationElement` , y funciones para asignar desde el enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-123">The `SampleProfileUdpBindingConfigurationElement` has properties that correspond to the properties on `SampleProfileUdpBinding`, and functions to map from the `ConfigurationElement` binding.</span></span> <span data-ttu-id="963c2-124">Finalmente, el método `OnApplyConfiguration` es invalidado en el `SampleProfileUdpBinding`, tal y como se muestra en el siguiente código muestra.</span><span class="sxs-lookup"><span data-stu-id="963c2-124">Finally, the `OnApplyConfiguration` method is overridden in the `SampleProfileUdpBinding`, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="963c2-125">Para registrar este controlador con el sistema de configuración, agregue la siguiente sección al archivo de configuración pertinente.</span><span class="sxs-lookup"><span data-stu-id="963c2-125">To register this handler with the configuration system, add the following section to the relevant configuration file.</span></span>  
  
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
  
 <span data-ttu-id="963c2-126">A continuación, se [ \<](../../configure-apps/file-schema/wcf/system-servicemodel.md) puede hacer referencia a él desde la sección de configuración system.serviceModel>.</span><span class="sxs-lookup"><span data-stu-id="963c2-126">It can then be referenced from the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) configuration section.</span></span>  
  
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
  
## <a name="adding-metadata-support-for-a-binding-element"></a><span data-ttu-id="963c2-127">Agregación de compatibilidad con metadatos para un elemento de enlace</span><span class="sxs-lookup"><span data-stu-id="963c2-127">Adding Metadata Support for a Binding Element</span></span>  
 <span data-ttu-id="963c2-128">Para integrar un canal en el sistema de metadatos, debe admitir la importación y exportación de la directiva.</span><span class="sxs-lookup"><span data-stu-id="963c2-128">To integrate a channel into the metadata system, it must support both the import and export of policy.</span></span> <span data-ttu-id="963c2-129">Esto permite que herramientas como [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generen clientes del elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-129">This allows tools such as [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate clients of the binding element.</span></span>  
  
### <a name="adding-wsdl-support"></a><span data-ttu-id="963c2-130">Agregación de la compatibilidad con WSDL</span><span class="sxs-lookup"><span data-stu-id="963c2-130">Adding WSDL Support</span></span>  
 <span data-ttu-id="963c2-131">El elemento de enlace del transporte en un enlace es el responsable de la exportación e importación de la información de direccionamiento en metadatos.</span><span class="sxs-lookup"><span data-stu-id="963c2-131">The transport binding element in a binding is responsible for exporting and importing addressing information in metadata.</span></span> <span data-ttu-id="963c2-132">Al utilizar un enlace SOAP, el elemento de enlace del transporte también debería exportar un URI de transporte correcto en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="963c2-132">When using a SOAP binding, the transport binding element should also export a correct transport URI in metadata.</span></span> <span data-ttu-id="963c2-133">El siguiente código de ejemplo se toma del ejemplo [Transport: UDP.](../samples/transport-udp.md)</span><span class="sxs-lookup"><span data-stu-id="963c2-133">The following example code is taken from the [Transport: UDP](../samples/transport-udp.md) sample.</span></span>  
  
#### <a name="wsdl-export"></a><span data-ttu-id="963c2-134">Exportación de WSDL</span><span class="sxs-lookup"><span data-stu-id="963c2-134">WSDL Export</span></span>  
 <span data-ttu-id="963c2-135">Para exportar información `UdpTransportBindingElement` de direccionamiento, implementa la <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interfaz.</span><span class="sxs-lookup"><span data-stu-id="963c2-135">To export addressing information, the `UdpTransportBindingElement` implements the <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="963c2-136">El método <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> agrega la información de direccionamiento correcta al puerto WSDL.</span><span class="sxs-lookup"><span data-stu-id="963c2-136">The <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A?displayProperty=nameWithType> method adds the correct addressing information to the WSDL port.</span></span>  
  
```csharp  
if (context.WsdlPort != null)  
{  
    AddAddressToWsdlPort(context.WsdlPort, context.Endpoint.Address, encodingBindingElement.MessageVersion.Addressing);  
}  
```  
  
 <span data-ttu-id="963c2-137">La implementación `UdpTransportBindingElement` del método <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> también exporta un URI de transporte cuando el punto de conexión utiliza un enlace SOAP:</span><span class="sxs-lookup"><span data-stu-id="963c2-137">The `UdpTransportBindingElement` implementation of the <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportEndpoint%2A> method also exports a transport URI when the endpoint uses a SOAP binding:</span></span>  
  
```csharp  
WsdlNS.SoapBinding soapBinding = GetSoapBinding(context, exporter);  
if (soapBinding != null)  
{  
    soapBinding.Transport = UdpPolicyStrings.UdpNamespace;  
}  
```  
  
#### <a name="wsdl-import"></a><span data-ttu-id="963c2-138">Importación de WSDL</span><span class="sxs-lookup"><span data-stu-id="963c2-138">WSDL Import</span></span>  
 <span data-ttu-id="963c2-139">Para extender el sistema de importación de WSDL para que administre la importación de las direcciones, agregue la configuración siguiente al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="963c2-139">To extend the WSDL import system to handle importing the addresses, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
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
  
 <span data-ttu-id="963c2-140">Al ejecutar Svcutil.exe, hay dos opciones para conseguir que Svcutil.exe cargue las extensiones de importación de WSDL:</span><span class="sxs-lookup"><span data-stu-id="963c2-140">When running Svcutil.exe, there are two options for getting Svcutil.exe to load the WSDL import extensions:</span></span>  
  
1. <span data-ttu-id="963c2-141">Apunte Svcutil.exe al archivo de configuración\<mediante el archivo /SvcutilConfig:>.</span><span class="sxs-lookup"><span data-stu-id="963c2-141">Point Svcutil.exe to the configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="963c2-142">Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="963c2-142">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
 <span data-ttu-id="963c2-143">El tipo `UdpBindingElementImporter` implementa la interfaz <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="963c2-143">The `UdpBindingElementImporter` type implements the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="963c2-144">El método `ImportEndpoint` importa la dirección del puerto del WSDL:</span><span class="sxs-lookup"><span data-stu-id="963c2-144">The `ImportEndpoint` method imports the address from the WSDL port:</span></span>  
  
```csharp  
BindingElementCollection bindingElements = context.Endpoint.Binding.CreateBindingElements();  
TransportBindingElement transportBindingElement = bindingElements.Find<TransportBindingElement>();  
if (transportBindingElement is UdpTransportBindingElement)  
{  
    ImportAddress(context);  
}  
```  
  
### <a name="adding-policy-support"></a><span data-ttu-id="963c2-145">Agregación de compatibilidad de directiva</span><span class="sxs-lookup"><span data-stu-id="963c2-145">Adding Policy Support</span></span>  
 <span data-ttu-id="963c2-146">El elemento de enlace personalizado puede exportar aserciones de directiva en el enlace de WSDL para que un extremo de servicio exprese las funciones de ese elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="963c2-146">The custom binding element can export policy assertions in the WSDL binding for a service endpoint to express the capabilities of that binding element.</span></span> <span data-ttu-id="963c2-147">El siguiente código de ejemplo se toma del ejemplo [Transport: UDP.](../samples/transport-udp.md)</span><span class="sxs-lookup"><span data-stu-id="963c2-147">The following example code is taken from the [Transport: UDP](../samples/transport-udp.md) sample.</span></span>  
  
#### <a name="policy-export"></a><span data-ttu-id="963c2-148">Exportación de directivas</span><span class="sxs-lookup"><span data-stu-id="963c2-148">Policy Export</span></span>  
 <span data-ttu-id="963c2-149">El `UdpTransportBindingElement` tipo <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> se implementa para agregar compatibilidad para la exportación de directivas.</span><span class="sxs-lookup"><span data-stu-id="963c2-149">The `UdpTransportBindingElement` type implements <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> to add support for exporting policy.</span></span> <span data-ttu-id="963c2-150">Como resultado, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> incluye `UdpTransportBindingElement` en la generación de directiva para cualquier enlace que la incluya.</span><span class="sxs-lookup"><span data-stu-id="963c2-150">As a result, <xref:System.ServiceModel.Description.MetadataExporter?displayProperty=nameWithType> includes `UdpTransportBindingElement` in the generation of policy for any binding that includes it.</span></span>  
  
 <span data-ttu-id="963c2-151">En <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, agregue una aserción para UDP y otra aserción si el canal está en modo de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="963c2-151">In <xref:System.ServiceModel.Description.IPolicyExportExtension.ExportPolicy%2A?displayProperty=nameWithType>, add an assertion for UDP and another assertion if the channel is in multicast mode.</span></span> <span data-ttu-id="963c2-152">Esto se debe a que el modo de multidifusión afecta a cómo se construye la pila de comunicaciones, y, por tanto, debe coordinarse entre ambos lados.</span><span class="sxs-lookup"><span data-stu-id="963c2-152">This is because multicast mode affects how the communication stack is constructed, and thus must be coordinated between both sides.</span></span>  
  
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
  
 <span data-ttu-id="963c2-153">Dado que los elementos de enlace de transporte personalizados son responsables de la administración del direccionamiento, la implementación <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> en el `UdpTransportBindingElement` también debe administrar la exportación de las aserciones de directivas WS-Addressing adecuadas para indicar la versión de WS-Addressing que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="963c2-153">Because custom transport binding elements are responsible for handling addressing, the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> implementation on the `UdpTransportBindingElement` must also handle exporting the appropriate WS-Addressing policy assertions to indicate the version of WS-Addressing being used.</span></span>  
  
```csharp  
AddWSAddressingAssertion(context, encodingBindingElement.MessageVersion.Addressing);  
```  
  
#### <a name="policy-import"></a><span data-ttu-id="963c2-154">Importación de directivas</span><span class="sxs-lookup"><span data-stu-id="963c2-154">Policy Import</span></span>  
 <span data-ttu-id="963c2-155">Para extender el sistema de importación de directivas, agregue la siguiente configuración al archivo de configuración para Svcutil.exe tal y como se muestra en el archivo Svcutil.exe.config:</span><span class="sxs-lookup"><span data-stu-id="963c2-155">To extend the policy import system, add the following configuration to the configuration file for Svcutil.exe as shown in the Svcutil.exe.config file:</span></span>  
  
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
  
 <span data-ttu-id="963c2-156">A continuación, implementamos <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> desde nuestra clase registrada (`UdpBindingElementImporter`).</span><span class="sxs-lookup"><span data-stu-id="963c2-156">Then we implement <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> from our registered class (`UdpBindingElementImporter`).</span></span> <span data-ttu-id="963c2-157">En <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine las aserciones en el espacio de nombres adecuado y procese las que se encargan de la generación del transporte y de la comprobación de si es multidifusión.</span><span class="sxs-lookup"><span data-stu-id="963c2-157">In <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType>, examine the assertions in the appropriate namespace and process the ones for generating the transport and checking if it is multicast.</span></span> <span data-ttu-id="963c2-158">Además, elimine las aserciones que el importador administra desde la lista de aserciones de enlaces.</span><span class="sxs-lookup"><span data-stu-id="963c2-158">In addition, remove the assertions that the importer handles from the list of binding assertions.</span></span> <span data-ttu-id="963c2-159">De nuevo, al ejecutar Svcutil.exe, hay dos opciones para la integración:</span><span class="sxs-lookup"><span data-stu-id="963c2-159">Again, when running Svcutil.exe, there are two options for integration:</span></span>  
  
1. <span data-ttu-id="963c2-160">Apunte Svcutil.exe a nuestro archivo de\<configuración mediante el> de archivo /SvcutilConfig:.</span><span class="sxs-lookup"><span data-stu-id="963c2-160">Point Svcutil.exe to our configuration file using the /SvcutilConfig:\<file>.</span></span>  
  
2. <span data-ttu-id="963c2-161">Agregue la sección de configuración a Svcutil.exe.config en el mismo directorio como Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="963c2-161">Add the configuration section to Svcutil.exe.config in the same directory as Svcutil.exe.</span></span>  
  
### <a name="adding-a-custom-standard-binding-importer"></a><span data-ttu-id="963c2-162">Agregación de un importador de enlace estándar personalizado</span><span class="sxs-lookup"><span data-stu-id="963c2-162">Adding a Custom Standard Binding Importer</span></span>  
 <span data-ttu-id="963c2-163">Svcutil.exe y el tipo <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>, de forma predeterminada, reconocen e importan los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="963c2-163">Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> type, by default, recognize and import system-provided bindings.</span></span> <span data-ttu-id="963c2-164">De lo contrario, el enlace se importa como una instancia <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="963c2-164">Otherwise, the binding gets imported as a <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="963c2-165">Para permitir que Svcutil.exe y <xref:System.ServiceModel.Description.WsdlImporter> importen el `SampleProfileUdpBinding`, el `UdpBindingElementImporter` actúa también como un importador de enlaces estándar personalizado.</span><span class="sxs-lookup"><span data-stu-id="963c2-165">To enable Svcutil.exe and the <xref:System.ServiceModel.Description.WsdlImporter> to import the `SampleProfileUdpBinding` the `UdpBindingElementImporter` also acts as a custom standard binding importer.</span></span>  
  
 <span data-ttu-id="963c2-166">Un importador de enlace `ImportEndpoint` estándar personalizado <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> implementa el <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> método en la interfaz para examinar la instancia importada de metadatos para ver si podría haber sido generada por un enlace estándar específico.</span><span class="sxs-lookup"><span data-stu-id="963c2-166">A custom standard binding importer implements the `ImportEndpoint` method on the <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> interface to examine the <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> instance imported from metadata to see if it could have been generated by specific standard binding.</span></span>  
  
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
  
 <span data-ttu-id="963c2-167">Generalmente, la implementación de un importador de enlaces estándar personalizado, implica la comprobación de las propiedades de los elementos de enlace importados para comprobar que solo las propiedades que pudo establecer el enlace estándar han cambiado y el resto propiedades son sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="963c2-167">Generally, implementing a custom standard binding importer involves checking the properties of the imported binding elements to verify that only properties that could have been set by the standard binding have changed and all other properties are their defaults.</span></span> <span data-ttu-id="963c2-168">Una estrategia básica para implementar un importador de enlace estándar consiste en crear una instancia de enlace estándar, propagar las propiedades desde los elementos de enlace a la instancia de enlace estándar que admite enlaces estándar y, a continuación, comparar los elementos de enlace desde el enlace estándar con los elementos de enlace importados.</span><span class="sxs-lookup"><span data-stu-id="963c2-168">A basic strategy for implementing a standard binding importer is to create an instance of the standard binding, propagate the properties from the binding elements to the standard binding instance that the standard binding supports, and the compare the binding elements from the standard binding with the imported binding elements.</span></span>
