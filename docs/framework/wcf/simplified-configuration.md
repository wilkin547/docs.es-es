---
title: Configuración simplificada
description: Obtenga información acerca de la configuración simplificada de los servicios WCF. .NET Framework 4.6.1 proporciona una manera de reducir el tamaño y la complejidad de la configuración del servicio.
ms.date: 03/30/2017
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
ms.openlocfilehash: defaf536d5a5b9f1479271c0976b43e9b1eb5bc4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246043"
---
# <a name="simplified-configuration"></a><span data-ttu-id="c69a7-104">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="c69a7-104">Simplified Configuration</span></span>
<span data-ttu-id="c69a7-105">La configuración de servicios de Windows Communication Foundation (WCF) puede ser una tarea compleja.</span><span class="sxs-lookup"><span data-stu-id="c69a7-105">Configuring Windows Communication Foundation (WCF) services can be a complex task.</span></span> <span data-ttu-id="c69a7-106">Existen muchas opciones diferentes y no siempre es fácil determinar qué configuración es necesaria.</span><span class="sxs-lookup"><span data-stu-id="c69a7-106">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="c69a7-107">Aunque los archivos de configuración aumentan la flexibilidad de los servicios WCF, también son el origen de muchos problemas difíciles de encontrar.</span><span class="sxs-lookup"><span data-stu-id="c69a7-107">While configuration files increase the flexibility of WCF services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] <span data-ttu-id="c69a7-108">aborda estos problemas y proporciona una forma de reducir el tamaño y la complejidad de la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-108">addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="c69a7-109">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="c69a7-109">Simplified Configuration</span></span>  
 <span data-ttu-id="c69a7-110">En los archivos de configuración del servicio WCF, la `system.serviceModel` sección <> contiene un `service` elemento de> de <para cada servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="c69a7-110">In WCF service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="c69a7-111">El `service` elemento <> contiene una colección de `endpoint` elementos de> <que especifican los extremos expuestos para cada servicio y, opcionalmente, un conjunto de comportamientos de servicio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-111">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="c69a7-112">Los elementos de> de <`endpoint` especifican la dirección, el enlace y el contrato expuestos por el extremo y, opcionalmente, la configuración de enlace y los comportamientos de extremo.</span><span class="sxs-lookup"><span data-stu-id="c69a7-112">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="c69a7-113">La `system.serviceModel` sección <> contiene también un elemento de> de <`behaviors` que le permite especificar comportamientos de servicio o de extremo.</span><span class="sxs-lookup"><span data-stu-id="c69a7-113">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="c69a7-114">En el ejemplo siguiente se muestra la `system.serviceModel` sección <> de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c69a7-114">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
        <serviceDebug includeExceptionDetailInFaults="false" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <bindings>  
   <basicHttpBinding>  
      <binding name=MyBindingConfig"  
               maxBufferSize="100"  
               maxReceiveBufferSize="100" />  
   </basicHttpBinding>  
   </bindings>   <services>  
    <service behaviorConfiguration="MyServiceBehavior"  
             name="MyService">  
      <endpoint address=""  
                binding="basicHttpBinding"  
                contract="ICalculator"  
                bindingConfiguration="MyBindingConfig" />  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange"/>  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="c69a7-115">facilita la configuración de un servicio WCF mediante la eliminación del requisito del `service` elemento de> de <.</span><span class="sxs-lookup"><span data-stu-id="c69a7-115">makes configuring a WCF service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="c69a7-116">Si no agrega un <`service`> sección o agrega puntos de conexión en una <`service`> sección y el servicio no define ningún extremo mediante programación, se agrega automáticamente un conjunto de extremos predeterminados al servicio, uno para cada dirección base del servicio y para cada contrato implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-116">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="c69a7-117">En cada uno de estos puntos de conexión, la dirección del punto de conexión corresponde a la dirección base, el esquema de la dirección base determina el enlace y el contrato es el implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-117">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="c69a7-118">Si no necesita especificar ningún extremo o comportamientos del servicio, ni realizar ningún cambio de configuración de enlaces, no necesita especificar ningún archivo de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-118">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="c69a7-119">Si un servicio implementa dos contratos y el host habilita transportes HTTP y TCP, el host de servicio crea cuatro extremos predeterminados, uno para cada contrato al usar cada transporte.</span><span class="sxs-lookup"><span data-stu-id="c69a7-119">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="c69a7-120">Para crear extremos predeterminados, el host de servicio debe conocer qué enlaces hay que utilizar.</span><span class="sxs-lookup"><span data-stu-id="c69a7-120">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="c69a7-121">Esta configuración se especifica en una <`protocolMappings`> sección dentro de la `system.serviceModel` sección <>.</span><span class="sxs-lookup"><span data-stu-id="c69a7-121">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="c69a7-122">La `protocolMappings` sección <> contiene una lista de esquemas de protocolos de transporte asignados a tipos de enlace.</span><span class="sxs-lookup"><span data-stu-id="c69a7-122">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="c69a7-123">El host de servicio usa las direcciones base que se le han transmitido para determinar qué enlace debe usar.</span><span class="sxs-lookup"><span data-stu-id="c69a7-123">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="c69a7-124">En el ejemplo siguiente se usa el `protocolMappings` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="c69a7-124">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="c69a7-125">Al cambiar los elementos de la configuración predeterminada, como los enlaces o los comportamientos, puede afectar a los servicios definidos en los niveles inferiores de la jerarquía de configuración, dado que podrían usar dichos enlaces y comportamientos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c69a7-125">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="c69a7-126">Por lo tanto, siempre que cambien los enlaces y comportamientos predeterminados, es necesario tener en cuenta de que estos cambios podrían afectar a otros servicios de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="c69a7-126">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c69a7-127">Los servicios hospedados en Internet Information Services (IIS) o en el Servicio de activación de procesos de Windows (WAS) usan el directorio virtual como su dirección base.</span><span class="sxs-lookup"><span data-stu-id="c69a7-127">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="c69a7-128">En el ejemplo anterior, un punto de conexión con una dirección base que se inicia con el esquema de "http" utiliza el objeto <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c69a7-128">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="c69a7-129">Un extremo con una dirección base que se inicia con el esquema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c69a7-129">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="c69a7-130">Puede invalidar la configuración en un archivo App.config o Web.config local.</span><span class="sxs-lookup"><span data-stu-id="c69a7-130">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="c69a7-131">Cada elemento dentro de la `protocolMappings` sección <> debe especificar un esquema y un enlace.</span><span class="sxs-lookup"><span data-stu-id="c69a7-131">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="c69a7-132">Opcionalmente, puede especificar un `bindingConfiguration` atributo que especifique una configuración de enlace dentro de la `bindings` sección <> del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c69a7-132">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="c69a7-133">Si no se especifica `bindingConfiguration`, se utiliza la configuración de enlace anónima del tipo de enlace adecuado.</span><span class="sxs-lookup"><span data-stu-id="c69a7-133">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="c69a7-134">Los comportamientos de servicio se configuran para los extremos predeterminados mediante el uso de <anónimas `behavior`> secciones dentro de <`serviceBehaviors` secciones>.</span><span class="sxs-lookup"><span data-stu-id="c69a7-134">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="c69a7-135">Los `behavior` elementos de> de <sin nombre dentro de <`serviceBehaviors`> se usan para configurar los comportamientos del servicio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-135">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="c69a7-136">Por ejemplo, el siguiente archivo de configuración habilita la publicación de metadatos del servicio para todos los servicios dentro del host.</span><span class="sxs-lookup"><span data-stu-id="c69a7-136">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <!-- No <service> tag is necessary. Default endpoints are added to the service -->  
    <!-- The service behavior with name="" is picked up by the service -->  
 </system.serviceModel>  
```  
  
 <span data-ttu-id="c69a7-137">Los comportamientos de extremo se configuran mediante <anónimas `behavior`> secciones dentro de <`serviceBehaviors` secciones de>.</span><span class="sxs-lookup"><span data-stu-id="c69a7-137">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="c69a7-138">El siguiente ejemplo es un archivo de configuración equivalente al del principio de este tema que utiliza el modelo de configuración simplificado.</span><span class="sxs-lookup"><span data-stu-id="c69a7-138">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <serviceMetadata httpGetEnabled="true" />
          <serviceDebug includeExceptionDetailInFaults="false" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <bindings>
       <basicHttpBinding>
          <binding maxBufferSize="100"
                   maxReceiveBufferSize="100" />
       </basicHttpBinding>
    </bindings>
    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->
    <!-- The service behavior with name="" will be picked up by the service -->
    <protocolMapping>
      <add scheme="http" binding="basicHttpBinding" />
  </protocolMapping>
  </system.serviceModel>
```  
  
> [!IMPORTANT]
> <span data-ttu-id="c69a7-139">Esta característica se relaciona únicamente con la configuración de servicio de WCF, no con la configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="c69a7-139">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="c69a7-140">La mayoría de las veces, la configuración de cliente de WCF se generará mediante una herramienta como svcutil.exe o la adición de una referencia de servicio desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c69a7-140">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="c69a7-141">Si está configurando manualmente un cliente de WCF, deberá agregar un \<client> elemento a la configuración y especificar los extremos que desee llamar.</span><span class="sxs-lookup"><span data-stu-id="c69a7-141">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69a7-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="c69a7-142">See also</span></span>

- [<span data-ttu-id="c69a7-143">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c69a7-143">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="c69a7-144">Configuración de enlaces para los servicios</span><span class="sxs-lookup"><span data-stu-id="c69a7-144">Configuring Bindings for Services</span></span>](configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="c69a7-145">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c69a7-145">Configuring System-Provided Bindings</span></span>](./feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c69a7-146">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="c69a7-146">Configuring Services</span></span>](configuring-services.md)
- [<span data-ttu-id="c69a7-147">Configuración de servicios WCF</span><span class="sxs-lookup"><span data-stu-id="c69a7-147">Configuring WCF services</span></span>](configuring-services.md)
- [<span data-ttu-id="c69a7-148">Configurar servicios WCF en el código</span><span class="sxs-lookup"><span data-stu-id="c69a7-148">Configuring WCF Services in Code</span></span>](configuring-wcf-services-in-code.md)
