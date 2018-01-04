---
title: "Configuración de enlaces para servicios Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: binding configuration [WCF]
ms.assetid: 99a85fd8-f7eb-4a84-a93e-7721b37d415c
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b11810e0a39c5b6091a63ef33e5abfccb95b7555
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-bindings-for-windows-communication-foundation-services"></a><span data-ttu-id="964d1-102">Configuración de enlaces para servicios Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="964d1-102">Configuring Bindings for Windows Communication Foundation Services</span></span>
<span data-ttu-id="964d1-103">Con frecuencia al crear una aplicación desea delegar las decisiones al administrador tras la implementación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="964d1-103">When creating an application, you often want to defer decisions to the administrator after the deployment of the application.</span></span> <span data-ttu-id="964d1-104">Por ejemplo, a menudo no hay manera de conocer de antemano qué será una dirección de servicio o un URI.</span><span class="sxs-lookup"><span data-stu-id="964d1-104">For example, there is often no way of knowing in advance what a service address, or Uniform Resource Identifier (URI), will be.</span></span> <span data-ttu-id="964d1-105">En lugar de incluir una dirección en el código, es preferible permitir a un administrador hacerlo después de crear un servicio.</span><span class="sxs-lookup"><span data-stu-id="964d1-105">Instead of hard-coding an address, it is preferable to allow an administrator to do so after creating a service.</span></span> <span data-ttu-id="964d1-106">Esta flexibilidad se logra a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="964d1-106">This flexibility is accomplished through configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="964d1-107">Use la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) con la `/config` conmutador que se va a crear rápidamente archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="964d1-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) with the `/config` switch to quickly create configuration files.</span></span>  
  
## <a name="major-sections"></a><span data-ttu-id="964d1-108">Secciones principales</span><span class="sxs-lookup"><span data-stu-id="964d1-108">Major Sections</span></span>  
 <span data-ttu-id="964d1-109">El esquema de configuración [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] incluye las tres secciones principales siguientes (`serviceModel`, `bindings`y `services`):</span><span class="sxs-lookup"><span data-stu-id="964d1-109">The [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] configuration scheme includes the following three major sections (`serviceModel`, `bindings`, and `services`):</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <bindings>  
        </bindings>  
        <services>  
        </services>  
        <behaviors>  
        </behaviors>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="servicemodel-elements"></a><span data-ttu-id="964d1-110">Elementos ServiceModel</span><span class="sxs-lookup"><span data-stu-id="964d1-110">ServiceModel Elements</span></span>  
 <span data-ttu-id="964d1-111">Puede usar la sección limitada por la `system.ServiceModel` elemento para definir un tipo de servicio con uno o más extremos, así como los valores para un servicio.</span><span class="sxs-lookup"><span data-stu-id="964d1-111">You can use the section bounded by the `system.ServiceModel` element to configure a service type with one or more endpoints, as well as settings for a service.</span></span> <span data-ttu-id="964d1-112">Cada punto de conexión se puede configurar a continuación con una dirección, un contrato y un enlace.</span><span class="sxs-lookup"><span data-stu-id="964d1-112">Each endpoint can then be configured with an address, a contract, and a binding.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="964d1-113">puntos de conexión, consulte [información general de creación de punto de conexión](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="964d1-113"> endpoints, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="964d1-114">Si no se especifica ningún punto de conexión, el tiempo de ejecución agrega puntos de conexión predeterminados.</span><span class="sxs-lookup"><span data-stu-id="964d1-114">If no endpoints are specified, the runtime adds default endpoints.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="964d1-115"> los puntos de conexión, enlaces y comportamientos predeterminados, consulte [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="964d1-115"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="964d1-116">Un enlace especifica transportes (HTTP, TCP, canalizaciones, Message Queuing) y protocolos (seguridad, confiabilidad, flujos de transacción) y está compuesto de elementos de enlace, cada uno de los cuales especifica un aspecto sobre cómo un punto de conexión se comunica con el mundo.</span><span class="sxs-lookup"><span data-stu-id="964d1-116">A binding specifies transports (HTTP, TCP, pipes, Message Queuing) and protocols (Security, Reliability, Transaction flows) and consists of binding elements, each of which specifies an aspect of how an endpoint communicates with the world.</span></span>  
  
 <span data-ttu-id="964d1-117">Por ejemplo, si se especifica la [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento indica que se utiliza HTTP como transporte para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="964d1-117">For example, specifying the [\<basicHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element indicates to use HTTP as the transport for an endpoint.</span></span> <span data-ttu-id="964d1-118">Se utiliza para conectar el punto de conexión en tiempo de ejecución cuando se abre el servicio utilizando este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="964d1-118">This is used to wire up the endpoint at run time when the service using this endpoint is opened.</span></span>  
  
 <span data-ttu-id="964d1-119">Hay dos tipos de enlaces: predefinidos y personalizados.</span><span class="sxs-lookup"><span data-stu-id="964d1-119">There are two kinds of bindings: predefined and custom.</span></span> <span data-ttu-id="964d1-120">Los enlaces predefinidos contienen combinaciones útiles de elementos que se utilizan en escenarios comunes.</span><span class="sxs-lookup"><span data-stu-id="964d1-120">Predefined bindings contain useful combinations of elements that are used in common scenarios.</span></span> <span data-ttu-id="964d1-121">Para obtener una lista de los enlaces predefinidos tipos que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona, consulte [enlaces proporcionados](../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="964d1-121">For a list of predefined binding types that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] provides, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="964d1-122">Si ninguna colección de enlace predefinido tiene la combinación correcta de características que una aplicación de servicio necesita, puede construir enlaces personalizados para satisfacer los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="964d1-122">If no predefined binding collection has the correct combination of features that a service application needs, you can construct custom bindings to meet the application's requirements.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="964d1-123">enlaces personalizados, consulte [ \<customBinding >](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="964d1-123"> custom bindings, see [\<customBinding>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
 <span data-ttu-id="964d1-124">Los cuatro ejemplos siguientes muestran las configuraciones de enlace más comunes utilizadas para preparar un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="964d1-124">The following four examples illustrate the most common binding configurations used for setting up a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span>  
  
#### <a name="specifying-an-endpoint-to-use-a-binding-type"></a><span data-ttu-id="964d1-125">Especificar un punto de conexión para usar un tipo de enlace</span><span class="sxs-lookup"><span data-stu-id="964d1-125">Specifying an Endpoint to Use a Binding Type</span></span>  
 <span data-ttu-id="964d1-126">El primer ejemplo muestra cómo especificar un extremo configurado con una dirección, un contrato y un enlace.</span><span class="sxs-lookup"><span data-stu-id="964d1-126">The first example illustrates how to specify an endpoint configured with an address, a contract, and a binding.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <!—- This section is optional with the default configuration introduced  
       in .NET Framework 4. -->  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
```  
  
 <span data-ttu-id="964d1-127">En este ejemplo, el atributo de `name` indica para qué tipo de servicio es la configuración.</span><span class="sxs-lookup"><span data-stu-id="964d1-127">In this example, the `name` attribute indicates which service type the configuration is for.</span></span> <span data-ttu-id="964d1-128">Al crear un servicio en su código con el contrato `HelloWorld`, se inicializa con todos los extremos definidos en la configuración del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="964d1-128">When you create a service in your code with the `HelloWorld` contract, it is initialized with all of the endpoints defined in the example configuration.</span></span> <span data-ttu-id="964d1-129">Si el ensamblado implementa sólo un contrato de servicio, el `name` atributo se puede omitir porque el servicio utiliza el tipo solo está disponible.</span><span class="sxs-lookup"><span data-stu-id="964d1-129">If the assembly implements only one service contract, the `name` attribute can be omitted because the service uses the only available type.</span></span> <span data-ttu-id="964d1-130">El atributo toma una cadena, que debe tener el formato `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span><span class="sxs-lookup"><span data-stu-id="964d1-130">The attribute takes a string, which must be in the format `Namespace.Class, AssemblyName, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null`</span></span>  
  
 <span data-ttu-id="964d1-131">El atributo `address` especifica el URI que otros extremos utilizan para comunicarse con servicio.</span><span class="sxs-lookup"><span data-stu-id="964d1-131">The `address` attribute specifies the URI that other endpoints use to communicate to the service.</span></span> <span data-ttu-id="964d1-132">El URI puede ser una ruta de acceso absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="964d1-132">The URI can be either an absolute or relative path.</span></span> <span data-ttu-id="964d1-133">Si se proporciona una dirección relativa, se espera que el host proporcione una dirección base que sea adecuada para el esquema de transporte usado en el enlace.</span><span class="sxs-lookup"><span data-stu-id="964d1-133">If a relative address is provided, the host is expected to provide a base address that is appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="964d1-134">Si no se configura una dirección, se supone que la dirección base es la dirección para ese punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="964d1-134">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span>  
  
 <span data-ttu-id="964d1-135">El atributo `contract` especifica el contrato que este extremo está exponiendo.</span><span class="sxs-lookup"><span data-stu-id="964d1-135">The `contract` attribute specifies the contract this endpoint is exposing.</span></span> <span data-ttu-id="964d1-136">El tipo de implementación de servicio debe implementar el tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="964d1-136">The service implementation type must implement the contract type.</span></span> <span data-ttu-id="964d1-137">Si una implementación de servicio implementa un tipo de contrato único, entonces se puede omitir esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="964d1-137">If a service implementation implements a single contract type, then this property can be omitted.</span></span>  
  
 <span data-ttu-id="964d1-138">El atributo `binding` selecciona un enlace predefinido o personalizado para utilizarlo para este extremo concreto.</span><span class="sxs-lookup"><span data-stu-id="964d1-138">The `binding` attribute selects a predefined or custom binding to use for this specific endpoint.</span></span> <span data-ttu-id="964d1-139">Un extremo que no selecciona explícitamente un enlace utiliza la selección de enlace predeterminada, que es `BasicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="964d1-139">An endpoint that does not explicitly select a binding uses the default binding selection, which is `BasicHttpBinding`.</span></span>  
  
#### <a name="modifying-a-predefined-binding"></a><span data-ttu-id="964d1-140">Modificar un enlace predefinido</span><span class="sxs-lookup"><span data-stu-id="964d1-140">Modifying a Predefined Binding</span></span>  
 <span data-ttu-id="964d1-141">En el ejemplo siguiente, se modifica un enlace predefinido.</span><span class="sxs-lookup"><span data-stu-id="964d1-141">In the following example, a predefined binding is modified.</span></span> <span data-ttu-id="964d1-142">Se puede utilizar a continuación para configurar cualquier punto de conexión en el servicio.</span><span class="sxs-lookup"><span data-stu-id="964d1-142">It can then be used to configure any endpoint in the service.</span></span> <span data-ttu-id="964d1-143">El enlace se modifica estableciendo el valor <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> en 1 segundo.</span><span class="sxs-lookup"><span data-stu-id="964d1-143">The binding is modified by setting the <xref:System.ServiceModel.Configuration.IBindingConfigurationElement.ReceiveTimeout%2A> value to 1 second.</span></span> <span data-ttu-id="964d1-144">Observe que la propiedad devuelve un objeto <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="964d1-144">Note that the property returns a <xref:System.TimeSpan> object.</span></span>  
  
 <span data-ttu-id="964d1-145">Ese enlace alterado se encuentra en la sección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="964d1-145">That altered binding is found in the bindings section.</span></span> <span data-ttu-id="964d1-146">Este enlace alterado se puede usar al crear cualquier extremo estableciendo el atributo `binding` en el elemento `endpoint`.</span><span class="sxs-lookup"><span data-stu-id="964d1-146">This altered binding can now be used when creating any endpoint by setting the `binding` attribute in the `endpoint` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="964d1-147">Si asigna un nombre determinado al enlace, el atributo `bindingConfiguration` especificado en el extremo de servicio debe coincidir con él.</span><span class="sxs-lookup"><span data-stu-id="964d1-147">If you give a particular name to the binding, the `bindingConfiguration` specified in the service endpoint must match with it.</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
  <endpoint   
      address="/HelloWorld2/"  
      contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
      binding="basicHttpBinding" />
</service>  
<bindings>  
    <basicHttpBinding   
        receiveTimeout="00:00:01"  
    />  
</bindings>  
```  
  
## <a name="configuring-a-behavior-to-apply-to-a-service"></a><span data-ttu-id="964d1-148">Configurar un comportamiento para aplicarlo a un servicio</span><span class="sxs-lookup"><span data-stu-id="964d1-148">Configuring a Behavior to Apply to a Service</span></span>  
 <span data-ttu-id="964d1-149">En el ejemplo siguiente, un comportamiento concreto se configura para el tipo de servicio.</span><span class="sxs-lookup"><span data-stu-id="964d1-149">In the following example, a specific behavior is configured for the service type.</span></span> <span data-ttu-id="964d1-150">El `ServiceMetadataBehavior` elemento se utiliza para habilitar la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para consultar el servicio y generar documentos de lenguaje de descripción de servicios Web (WSDL) de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="964d1-150">The `ServiceMetadataBehavior` element is used to enable the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to query the service and generate Web Services Description Language (WSDL) documents from the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="964d1-151">Si asigna un nombre determinado al comportamiento, el atributo `behaviorConfiguration` especificado en el servicio o en la sección de extremo debe coincidir con él.</span><span class="sxs-lookup"><span data-stu-id="964d1-151">If you give a particular name to the behavior, the `behaviorConfiguration` specified in the service or endpoint section must match it.</span></span>  
  
```xml  
<behaviors>  
    <behavior>  
        <ServiceMetadata httpGetEnabled="true" />   
    </behavior>  
</behaviors>  
<services>  
    <service   
       name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">
       <endpoint   
          address="http://computer:8080/Hello"  
          contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
          binding="basicHttpBinding" />
    </service>  
</services>  
```  
  
 <span data-ttu-id="964d1-152">La configuración anterior permite a un cliente llamar y obtener los metadatos del servicio con tipo "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="964d1-152">The preceding configuration enables a client to call and get the metadata of the "HelloWorld" typed service.</span></span>  
  
 `svcutil /config:Client.exe.config http://computer:8080/Hello?wsdl`  
  
## <a name="specifying-a-service-with-two-endpoints-using-different-binding-values"></a><span data-ttu-id="964d1-153">Especificar un servicio con dos puntos de conexión usando valores de enlace diferentes</span><span class="sxs-lookup"><span data-stu-id="964d1-153">Specifying a Service with Two Endpoints Using Different Binding Values</span></span>  
 <span data-ttu-id="964d1-154">En este último ejemplo, dos extremos se configuran para el tipo de servicio `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="964d1-154">In this last example, two endpoints are configured for the `HelloWorld` service type.</span></span> <span data-ttu-id="964d1-155">Cada punto de conexión utiliza un personalizado diferente `bindingConfiguration` atributo del mismo tipo de enlace (cada uno modifica el `basicHttpBinding`).</span><span class="sxs-lookup"><span data-stu-id="964d1-155">Each endpoint uses a different customized  `bindingConfiguration` attribute of the same binding type (each modifies the `basicHttpBinding`).</span></span>  
  
```xml  
<service name="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null">  
    <endpoint  
        address="http://computer:8080/Hello1"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="shortTimeout" />
    <endpoint  
        address="http://computer:8080/Hello2"  
        contract="HelloWorld, IndigoConfig, Version=2.0.0.0, Culture=neutral, PublicKeyToken=null"  
        binding="basicHttpBinding"  
        bindingConfiguration="Secure" />
</service>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure">  
        <Security mode="Transport" />  
     </basicHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="964d1-156">Puede obtener el mismo comportamiento usando la configuración predeterminada si agrega una sección `protocolMapping` y configura los enlaces, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="964d1-156">You can get the same behavior using the default configuration by adding a `protocolMapping` section and configuring the bindings as demonstrated in the following example.</span></span>  
  
```xml  
<protocolMapping>  
    <add scheme="http" binding="basicHttpBinding" bindingConfiguration="shortTimeout" />  
    <add scheme="https" binding="basicHttpBinding" bindingConfiguration="Secure" />  
</protocolMapping>  
<bindings>  
    <basicHttpBinding   
        name="shortTimeout"  
        timeout="00:00:00:01"   
     />  
     <basicHttpBinding   
        name="Secure" />  
        <Security mode="Transport" />  
</bindings>  
```  
  
## <a name="see-also"></a><span data-ttu-id="964d1-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="964d1-157">See Also</span></span>  
 [<span data-ttu-id="964d1-158">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="964d1-158">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="964d1-159">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="964d1-159">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="964d1-160">Información general sobre la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="964d1-160">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="964d1-161">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="964d1-161">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
