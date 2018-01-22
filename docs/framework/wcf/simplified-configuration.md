---
title: "Configuración simplificada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dcbe1f84-437c-495f-9324-2bc09fd79ea9
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 334dfce44b1f0a7b6b38f509f2f0a346ef90630f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="simplified-configuration"></a><span data-ttu-id="a13b5-102">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="a13b5-102">Simplified Configuration</span></span>
<span data-ttu-id="a13b5-103">Configurar los servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] puede ser una tarea compleja.</span><span class="sxs-lookup"><span data-stu-id="a13b5-103">Configuring [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] services can be a complex task.</span></span> <span data-ttu-id="a13b5-104">Existen muchas opciones diferentes y no siempre es fácil determinar qué configuración es necesaria.</span><span class="sxs-lookup"><span data-stu-id="a13b5-104">There are many different options and it is not always easy to determine what settings are required.</span></span> <span data-ttu-id="a13b5-105">Aunque los archivos de configuración aumentan la flexibilidad de los servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], también son el origen de muchos problemas difíciles de detectar.</span><span class="sxs-lookup"><span data-stu-id="a13b5-105">While configuration files increase the flexibility of [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, they also are the source for many hard to find problems.</span></span> [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]<span data-ttu-id="a13b5-106"> aborda estos problemas y proporciona una forma de reducir el tamaño y la complejidad de la configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-106"> addresses these problems and provides a way to reduce the size and complexity of service configuration.</span></span>  
  
## <a name="simplified-configuration"></a><span data-ttu-id="a13b5-107">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="a13b5-107">Simplified Configuration</span></span>  
 <span data-ttu-id="a13b5-108">En los archivos de configuración de servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], la sección <`system.serviceModel`> contiene un elemento <`service`> para cada servicio hospedado.</span><span class="sxs-lookup"><span data-stu-id="a13b5-108">In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service configuration files, the <`system.serviceModel`> section contains a <`service`> element for each service hosted.</span></span> <span data-ttu-id="a13b5-109">El elemento `service` contiene una recopilación de elementos <`endpoint`> que especifican los extremos expuestos para cada servicio y, opcionalmente, un conjunto de comportamientos del servicio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-109">The <`service`> element contains a collection of <`endpoint`> elements that specify the endpoints exposed for each service and optionally a set of service behaviors.</span></span> <span data-ttu-id="a13b5-110">Los elementos <`endpoint`> especifican la dirección, el enlace y el contrato expuestos por el extremo y, opcionalmente, la configuración de enlace y los comportamientos de los extremos.</span><span class="sxs-lookup"><span data-stu-id="a13b5-110">The <`endpoint`> elements specify the address, binding, and contract exposed by the endpoint, and optionally binding configuration and endpoint behaviors.</span></span> <span data-ttu-id="a13b5-111">La sección <`system.serviceModel`> también contiene un elemento <`behaviors`> que le permite especificar los comportamientos de los servicios o los extremos.</span><span class="sxs-lookup"><span data-stu-id="a13b5-111">The <`system.serviceModel`> section also contains a <`behaviors`> element that allows you to specify service or endpoint behaviors.</span></span> <span data-ttu-id="a13b5-112">En el ejemplo siguiente, se muestra la sección <`system.serviceModel`> de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a13b5-112">The following example shows the <`system.serviceModel`> section of a configuration file.</span></span>  
  
```  
<system.serviceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="MyServiceBehavior">  
        <serviceMetadata httpGetEnabled="true">  
        <serviceDebug includeExceptionDetailInFaults="false">  
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
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<span data-ttu-id="a13b5-113"> facilita la configuración de un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] eliminando el requisito del elemento <`service`>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-113"> makes configuring a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service easier by removing the requirement for the <`service`> element.</span></span> <span data-ttu-id="a13b5-114">Si no agrega ninguna sección <`service`> ni ningún extremo en una sección <`service`> y el servicio no define ningún extremo mediante programación, entonces se agrega automáticamente al servicio un conjunto de extremos predeterminados, uno para cada dirección base del servicio y para cada contrato implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-114">If you do not add a <`service`>  section or add any endpoints in a <`service`> section and your service does not programmatically define any endpoints, then a set of default endpoints are automatically added to your service, one for each service base address and for each contract implemented by your service.</span></span> <span data-ttu-id="a13b5-115">En cada uno de estos extremos, la dirección del extremo corresponde a la dirección base, el esquema de la dirección base determina el enlace y el contrato es el implementado por el servicio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-115">In each of these endpoints, the endpoint address corresponds to the base address, the binding is determined by the base address scheme and the contract is the one implemented by your service.</span></span> <span data-ttu-id="a13b5-116">Si no necesita especificar ningún extremo o comportamientos del servicio, ni realizar ningún cambio de configuración de enlaces, no necesita especificar ningún archivo de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-116">If you do not need to specify any endpoints or service behaviors or make any binding setting changes, you do not need to specify a service configuration file at all.</span></span> <span data-ttu-id="a13b5-117">Si un servicio implementa dos contratos y el host habilita transportes HTTP y TCP, el host de servicio crea cuatro extremos predeterminados, uno para cada contrato al usar cada transporte.</span><span class="sxs-lookup"><span data-stu-id="a13b5-117">If a service implements two contracts and the host enables both HTTP and TCP transports the service host creates four default endpoints, one for each contract using each transport.</span></span> <span data-ttu-id="a13b5-118">Para crear extremos predeterminados, el host de servicio debe conocer qué enlaces hay que utilizar.</span><span class="sxs-lookup"><span data-stu-id="a13b5-118">To create default endpoints the service host must know what bindings to use.</span></span> <span data-ttu-id="a13b5-119">Esta configuración se especifica en una sección <`protocolMappings`> dentro de la sección <`system.serviceModel`>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-119">These settings are specified in a <`protocolMappings`> section within the <`system.serviceModel`> section.</span></span> <span data-ttu-id="a13b5-120">La sección <`protocolMappings`> contiene una lista de esquemas de protocolos de transporte asignada a los tipos de enlaces.</span><span class="sxs-lookup"><span data-stu-id="a13b5-120">The <`protocolMappings`> section contains a list of transport protocol schemes mapped to binding types.</span></span> <span data-ttu-id="a13b5-121">El host de servicio usa las direcciones base que se le han transmitido para determinar qué enlace debe usar.</span><span class="sxs-lookup"><span data-stu-id="a13b5-121">The service host uses the base addresses passed to it to determine which binding to use.</span></span> <span data-ttu-id="a13b5-122">El ejemplo siguiente usa el elemento <`protocolMappings`>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-122">The following example uses the <`protocolMappings`> element.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a13b5-123">Al cambiar los elementos de la configuración predeterminada, como los enlaces o los comportamientos, puede afectar a los servicios definidos en los niveles inferiores de la jerarquía de configuración, dado que podrían usar dichos enlaces y comportamientos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a13b5-123">Changing default configuration elements, such as bindings or behaviors, might affect services defined in lower levels of the configuration hierarchy, since they might be using these default bindings and behaviors.</span></span> <span data-ttu-id="a13b5-124">Por lo tanto, siempre que cambien los enlaces y comportamientos predeterminados, es necesario tener en cuenta de que estos cambios podrían afectar a otros servicios de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="a13b5-124">Thus, whoever changes default bindings and behaviors needs to be aware that these changes might affect other services in the hierarchy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a13b5-125">Los servicios hospedados en Internet Information Services (IIS) o en el Servicio de activación de procesos de Windows (WAS) usan el directorio virtual como su dirección base.</span><span class="sxs-lookup"><span data-stu-id="a13b5-125">Services hosted under Internet Information Services (IIS) or Windows Process Activation Service (WAS) use the virtual directory as their base address.</span></span>  
  
```xml  
<protocolMapping>  
  <add scheme="http"     binding="basicHttpBinding" bindingConfiguration="MyBindingConfiguration"/>  
  <add scheme="net.tcp"  binding="netTcpBinding"/>  
  <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
  <add scheme="net.msmq" binding="netMSMQBinding"/>  
</protocolMapping>  
```  
  
 <span data-ttu-id="a13b5-126">En el ejemplo anterior, un extremo con una dirección base que se inicia con el esquema de "http" utiliza el objeto <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-126">In the previous example, an endpoint with a base address that starts with the "http" scheme uses the <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="a13b5-127">Un extremo con una dirección base que se inicia con el esquema "net.tcp" usa <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-127">An endpoint with a base address that starts with the "net.tcp" scheme uses the <xref:System.ServiceModel.NetTcpBinding>.</span></span> <span data-ttu-id="a13b5-128">Puede invalidar la configuración en un archivo App.config o Web.config local.</span><span class="sxs-lookup"><span data-stu-id="a13b5-128">You can override settings in a local App.config or Web.config file.</span></span>  
  
 <span data-ttu-id="a13b5-129">Cada elemento dentro de la sección <`protocolMappings`> debe especificar un esquema y un enlace.</span><span class="sxs-lookup"><span data-stu-id="a13b5-129">Each element within the <`protocolMappings`> section must specify a scheme and a binding.</span></span> <span data-ttu-id="a13b5-130">Opcionalmente, puede indicar un atributo `bindingConfiguration` que especifique una configuración de enlace dentro de la sección <`bindings`> del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a13b5-130">Optionally it can specify a `bindingConfiguration` attribute that specifies a binding configuration within the <`bindings`> section of the configuration file.</span></span> <span data-ttu-id="a13b5-131">Si no se especifica `bindingConfiguration`, se utiliza la configuración de enlace anónima del tipo de enlace adecuado.</span><span class="sxs-lookup"><span data-stu-id="a13b5-131">If no `bindingConfiguration` is specified, the anonymous binding configuration of the appropriate binding type is used.</span></span>  
  
 <span data-ttu-id="a13b5-132">Los comportamientos del servicio se configuran para los extremos predeterminados mediante secciones <`behavior`> anónimas dentro de secciones <`serviceBehaviors`>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-132">Service behaviors are configured for the default endpoints by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span> <span data-ttu-id="a13b5-133">Todos los elementos <`behavior`> sin nombre dentro de <`serviceBehaviors`> se utilizan para configurar comportamientos del servicio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-133">Any unnamed <`behavior`> elements within <`serviceBehaviors`> are used to configure service behaviors.</span></span> <span data-ttu-id="a13b5-134">Por ejemplo, el siguiente archivo de configuración habilita la publicación de metadatos del servicio para todos los servicios dentro del host.</span><span class="sxs-lookup"><span data-stu-id="a13b5-134">For example, the following configuration file enables service metadata publishing for all services within the host.</span></span>  
  
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
  
 <span data-ttu-id="a13b5-135">Los comportamientos de los extremos se configuran mediante secciones <`behavior`> anónimas dentro de secciones <`serviceBehaviors`>.</span><span class="sxs-lookup"><span data-stu-id="a13b5-135">Endpoint behaviors are configured by using anonymous <`behavior`> sections within <`serviceBehaviors`> sections.</span></span>  
  
 <span data-ttu-id="a13b5-136">El siguiente ejemplo es un archivo de configuración equivalente al del principio de este tema que utiliza el modelo de configuración simplificado.</span><span class="sxs-lookup"><span data-stu-id="a13b5-136">The following example is a configuration file equivalent to the one at the beginning of this topic that uses the simplified configuration model.</span></span>  
  
```xml  
<system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="false"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>    <bindings>  
       <basicHttpBinding>  
          <binding maxBufferSize="100"  
                   maxReceiveBufferSize="100" />  
       </basicHttpBinding>  
    </bindings>    <!-- No <service> tag is necessary. Default endpoints will be added to the service -->  
    <!-- The service behavior with name="" will be picked up by the service -->  
    <protocolMapping>  
      <add scheme="http"     binding="basicHttpBinding" / </protocolMapping>  
  </system.serviceModel>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="a13b5-137">Esta característica se relaciona únicamente con la configuración de servicio de WCF, no con la configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="a13b5-137">This feature relates only to WCF service configuration, not client configuration.</span></span> <span data-ttu-id="a13b5-138">La mayoría de las veces, la configuración de cliente de WCF se generará mediante una herramienta como svcutil.exe o la adición de una referencia de servicio desde Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a13b5-138">Most times, WCF client configuration will be generated by a tool such as svcutil.exe or adding a service reference from Visual Studio.</span></span> <span data-ttu-id="a13b5-139">Si está configurando manualmente un cliente WCF debe agregar una \<cliente > elemento a la configuración y especificar los extremos que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="a13b5-139">If you are manually configuring a WCF client you will need to add a \<client> element to the configuration and specify any endpoints you wish to call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13b5-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a13b5-140">See Also</span></span>  
 [<span data-ttu-id="a13b5-141">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a13b5-141">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [<span data-ttu-id="a13b5-142">Configuración de enlaces para los servicios</span><span class="sxs-lookup"><span data-stu-id="a13b5-142">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [<span data-ttu-id="a13b5-143">Configuración de enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a13b5-143">Configuring System-Provided Bindings</span></span>](../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a13b5-144">Configuración de servicios</span><span class="sxs-lookup"><span data-stu-id="a13b5-144">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="a13b5-145">Configurar aplicaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="a13b5-145">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [<span data-ttu-id="a13b5-146">Configuración de servicios WCF en el código</span><span class="sxs-lookup"><span data-stu-id="a13b5-146">Configuring WCF Services in Code</span></span>](../../../docs/framework/wcf/configuring-wcf-services-in-code.md)
