---
description: 'Más información sobre: ejemplo de configuración'
title: Ejemplo de configuración
ms.date: 03/30/2017
ms.assetid: 75515b4a-8d70-44c8-99e0-7423df41380e
ms.openlocfilehash: e11237fbc32b203c9b661288dbccab01745928d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778391"
---
# <a name="configuration-sample"></a><span data-ttu-id="fdf32-103">Ejemplo de configuración</span><span class="sxs-lookup"><span data-stu-id="fdf32-103">Configuration Sample</span></span>

<span data-ttu-id="fdf32-104">En este ejemplo se muestra el uso de un archivo de configuración para hacer que un servicio se pueda detectar.</span><span class="sxs-lookup"><span data-stu-id="fdf32-104">This sample demonstrates the use of a configuration file to make a service discoverable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fdf32-105">En este ejemplo se implementa la detección en la configuración.</span><span class="sxs-lookup"><span data-stu-id="fdf32-105">This sample implements discovery in configuration.</span></span> <span data-ttu-id="fdf32-106">Para obtener un ejemplo que implementa la detección en el código, vea [Basic](basic-sample.md).</span><span class="sxs-lookup"><span data-stu-id="fdf32-106">For a sample that implements discovery in code, see [Basic](basic-sample.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fdf32-107">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="fdf32-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fdf32-108">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fdf32-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="fdf32-109">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="fdf32-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fdf32-110">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="fdf32-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Configuration`  
  
## <a name="service-configuration"></a><span data-ttu-id="fdf32-111">Configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="fdf32-111">Service Configuration</span></span>  

 <span data-ttu-id="fdf32-112">El archivo de configuración de este ejemplo muestra dos características:</span><span class="sxs-lookup"><span data-stu-id="fdf32-112">The configuration file in this sample demonstrates two features:</span></span>  
  
- <span data-ttu-id="fdf32-113">Hacer que el servicio se pueda detectar a través de un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> estándar.</span><span class="sxs-lookup"><span data-stu-id="fdf32-113">Making the service discoverable over a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
- <span data-ttu-id="fdf32-114">Ajustar la información relacionada con la detección para el extremo de la aplicación del servicio y ajustar algunos de los valores relacionados con la detección en el extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="fdf32-114">Adjusting discovery-related information for the service’s application endpoint and adjusting some of the discovery-related settings on the standard endpoint.</span></span>  
  
 <span data-ttu-id="fdf32-115">Para habilitar la detección, se deben realizar algunas modificaciones en el archivo de configuración de la aplicación para el servicio:</span><span class="sxs-lookup"><span data-stu-id="fdf32-115">To enable discovery, a few changes must be made in the application configuration file for the service:</span></span>  
  
- <span data-ttu-id="fdf32-116">Un extremo de detección se debe agregar al elemento `<service>`.</span><span class="sxs-lookup"><span data-stu-id="fdf32-116">A discovery endpoint must be added to the `<service>` element.</span></span> <span data-ttu-id="fdf32-117">Se trata de un punto de conexión <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> estándar.</span><span class="sxs-lookup"><span data-stu-id="fdf32-117">This is a standard <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span> <span data-ttu-id="fdf32-118">Este es un punto de conexión del sistema que el tiempo de ejecución asocia al servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="fdf32-118">This is a system endpoint that the runtime associates with the discovery service.</span></span> <span data-ttu-id="fdf32-119">El servicio de descarga realiza escuchas de los mensajes en este extremo.</span><span class="sxs-lookup"><span data-stu-id="fdf32-119">The discovery service listens for messages on this endpoint.</span></span>  
  
- <span data-ttu-id="fdf32-120">Se agrega un comportamiento `<serviceDiscovery>` a la sección `<serviceBehaviors>`.</span><span class="sxs-lookup"><span data-stu-id="fdf32-120">A `<serviceDiscovery>` behavior is added to the `<serviceBehaviors>` section.</span></span> <span data-ttu-id="fdf32-121">Esto permite detectar el servicio en tiempo de ejecución runtime y utiliza el punto de conexión de la detección mencionado previamente para realizar escuchas de `Probe` de detección y mensajes `Resolve`.</span><span class="sxs-lookup"><span data-stu-id="fdf32-121">This enables the service to be discovered at runtime and uses the discovery endpoint mentioned previously to listen for discovery `Probe` and `Resolve` messages.</span></span> <span data-ttu-id="fdf32-122">Con estas dos incorporaciones, el servicio se puede detectar en el punto de conexión de detección especificado.</span><span class="sxs-lookup"><span data-stu-id="fdf32-122">With these two additions, the service is discoverable at the discovery endpoint specified.</span></span>  
  
 <span data-ttu-id="fdf32-123">El siguiente fragmento de código muestra un servicio con un punto de conexión de la aplicación y un punto de conexión de detección definidos:</span><span class="sxs-lookup"><span data-stu-id="fdf32-123">The following config snippet shows a service with an application endpoint and a discovery endpoint defined:</span></span>  
  
```xml
<services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
          <endpoint name="udpDiscovery"
                    kind="udpDiscoveryEndpoint"
                endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
```  
  
 <span data-ttu-id="fdf32-124">Para beneficiarse de los anuncios, tendrá que agregar un extremo de anuncio.</span><span class="sxs-lookup"><span data-stu-id="fdf32-124">To take advantage of announcements, you will need to add an announcement endpoint.</span></span> <span data-ttu-id="fdf32-125">Para ello, modifique el archivo de configuración según se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdf32-125">To do this, modify the configuration file as shown in the following code.</span></span>  
  
```xml  
<serviceDiscovery>  
            <announcementEndpoints>  
              <endpoint kind="udpAnnouncementEndpoint"/>  
            </announcementEndpoints>  
          </serviceDiscovery>  
```  
  
 <span data-ttu-id="fdf32-126">Al agregar un punto de conexión de anuncio al comportamiento del servicio de detección, se crea un cliente de anuncio predeterminado para el servicio.</span><span class="sxs-lookup"><span data-stu-id="fdf32-126">Adding an announcement endpoint to the discovery service behavior creates a default announcement client for the service.</span></span> <span data-ttu-id="fdf32-127">Esto garantiza que el servicio enviará un anuncio en línea y sin conexión cuando el servicio se abra y se cierre respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fdf32-127">This guarantees that the service will send an online and offline announcement when the service is opened and closed respectively.</span></span>  
  
 <span data-ttu-id="fdf32-128">Este archivo de configuración supera esos pasos sencillos al modificar comportamientos adicionales.</span><span class="sxs-lookup"><span data-stu-id="fdf32-128">This configuration file goes beyond just those simple steps by modifying additional behaviors.</span></span> <span data-ttu-id="fdf32-129">Es posible controlar la información relacionada con la detección utilizando extremos concretos.</span><span class="sxs-lookup"><span data-stu-id="fdf32-129">It is possible to control discovery-related information by using specific endpoints.</span></span> <span data-ttu-id="fdf32-130">Es decir, un usuario puede controlar si se puede detectar un punto de conexión y también puede marcar ese punto de conexión con metadatos XML personalizados y la propiedad <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdf32-130">That is, a user can control whether an endpoint can be discovered and the user can also mark that endpoint with <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Scopes%2A> and custom XML metadata.</span></span> <span data-ttu-id="fdf32-131">Para ello, el usuario debe agregar una propiedad `behaviorConfiguration` al extremo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fdf32-131">To do this, the user must add a `behaviorConfiguration` property to the application endpoint.</span></span> <span data-ttu-id="fdf32-132">En este caso, la siguiente propiedad se agrega al extremo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fdf32-132">In this case, the following property is added to the application endpoint.</span></span>  
  
`behaviorConfiguration="endpointBehaviorConfiguration"`  
  
 <span data-ttu-id="fdf32-133">Ahora, a través del elemento de configuración de comportamiento, puede controlar los atributos relacionados con la detección.</span><span class="sxs-lookup"><span data-stu-id="fdf32-133">Now, through the behavior configuration element, you can control discovery-related attributes.</span></span> <span data-ttu-id="fdf32-134">En este caso, se agregan dos ámbitos al extremo de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fdf32-134">In this case, two scopes are added to the application endpoint.</span></span>  
  
```xml  
<endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>
        </endpointBehaviors>  
```  
  
 <span data-ttu-id="fdf32-135">Para obtener más información sobre los ámbitos, consulte [búsqueda y FindCriteria de detección](../feature-details/discovery-find-and-findcriteria.md).</span><span class="sxs-lookup"><span data-stu-id="fdf32-135">For more information about scopes, see [Discovery Find and FindCriteria](../feature-details/discovery-find-and-findcriteria.md).</span></span>  
  
 <span data-ttu-id="fdf32-136">También puede controlar detalles concretos del punto de conexión de la detección.</span><span class="sxs-lookup"><span data-stu-id="fdf32-136">You can also control specific details of the discovery endpoint.</span></span> <span data-ttu-id="fdf32-137">Esto se hace a través de <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span><span class="sxs-lookup"><span data-stu-id="fdf32-137">This is done through the <xref:System.ServiceModel.Configuration.StandardEndpointsSection>.</span></span> <span data-ttu-id="fdf32-138">En este ejemplo, se modifica la versión del protocolo utilizada además de agregar un atributo `maxResponseDelay` en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="fdf32-138">In this sample, the version of the protocol used is modified as well as adding a `maxResponseDelay` attribute as shown in the following code example.</span></span>  
  
```xml  
<standardEndpoints>  
   <udpDiscoveryEndpoint>  
      <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />
   </udpDiscoveryEndpoint>  
</standardEndpoints>  
```  
  
 <span data-ttu-id="fdf32-139">Lo siguiente es el archivo de configuración completo usado en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fdf32-139">The following is the complete configuration file used in this example:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
  
      <services>  
        <service name="Microsoft.Samples.Discovery.CalculatorService"  
                 behaviorConfiguration="calculatorServiceBehavior">  
          <endpoint address=""  
                    binding="wsHttpBinding"  
                    contract="Microsoft.Samples.Discovery.ICalculatorService"  
                    behaviorConfiguration="endpointBehaviorConfiguration" />  
         <!-- Define the discovery endpoint -->
<endpoint name="udpDiscovery" kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration"/>        </service>  
      </services>  
  
      <behaviors>  
  
        <serviceBehaviors>  
          <behavior name="calculatorServiceBehavior">  
  
            <!-- Add an announcement endpoint -->  
            <serviceDiscovery>  
              <announcementEndpoints>  
                <endpoint kind="udpAnnouncementEndpoint"/>  
              </announcementEndpoints>  
            </serviceDiscovery>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="endpointBehaviorConfiguration">  
            <!-- Add scopes used to identify the service -->  
            <endpointDiscovery>  
              <scopes>  
                <add scope="http://www.example.com/calculator"/>  
                <add scope="ldap:///ou=engineering,o=examplecom,c=us"/>  
              </scopes>  
            </endpointDiscovery>  
  
          </behavior>
        </endpointBehaviors>  
  
      </behaviors>  
  
      <standardEndpoints>  
        <udpDiscoveryEndpoint>  
         <!-- Configure the UDP discovery endpoint -->  
          <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11" maxResponseDelay="00:00:00.600" />
        </udpDiscoveryEndpoint>  
      </standardEndpoints>  
  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client-configuration"></a><span data-ttu-id="fdf32-140">Configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="fdf32-140">Client Configuration</span></span>  

 <span data-ttu-id="fdf32-141">En el archivo de configuración de la aplicación para el cliente, para la detección se usa el `standardEndpoint` de tipo `dynamicEndpoint`, según se muestra en el fragmento de configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="fdf32-141">In the application configuration file for the client, a `standardEndpoint` of type `dynamicEndpoint` is used to utilize discovery as shown in the following config snippet.</span></span>  
  
```xml  
<client>  
   <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
   <endpoint name="calculatorEndpoint"  
             binding="wsHttpBinding"  
             contract="ICalculatorService"  
             kind ="dynamicEndpoint"  
             endpointConfiguration="dynamicEndpointConfiguration">  
   </endpoint>  
</client>  
```  
  
 <span data-ttu-id="fdf32-142">Cuando un cliente utiliza un `dynamicEndpoint`, el tiempo de ejecución realiza la detección automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fdf32-142">When a client is using a `dynamicEndpoint`, the runtime performs discovery automatically.</span></span> <span data-ttu-id="fdf32-143">Durante la detección se usan varias opciones de configuración, como las definidas en la sección `discoveryClientSettings`, que especifica el tipo de extremo de detección que se usará:</span><span class="sxs-lookup"><span data-stu-id="fdf32-143">Various settings are used during discovery, such as those defined in the  `discoveryClientSettings` section, which specifies the type of discovery endpoint to use:</span></span>  
  
```xml  
<endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
```  
  
 <span data-ttu-id="fdf32-144">Los criterios de búsqueda que se usan para buscar servicios:</span><span class="sxs-lookup"><span data-stu-id="fdf32-144">The find criteria used to search for services:</span></span>  
  
```xml  
<!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
<findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
   <scopes>  
      <add scope="http://www.microsoft.com/building42/floor1"/>  
   </scopes>  
   <!-- These extensions are sent from the client to the service as part of the probe message -->  
   <extensions>  
      <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
   </extensions>  
</findCriteria>  
```  
  
 <span data-ttu-id="fdf32-145">Este ejemplo extiende esta característica y modifica el objeto <xref:System.ServiceModel.Discovery.FindCriteria> utilizado por el cliente, así como algunas propiedades del `updDiscoveryEndpoint` estándar que se usa en la detección.</span><span class="sxs-lookup"><span data-stu-id="fdf32-145">This sample extends this feature and modifies the <xref:System.ServiceModel.Discovery.FindCriteria> used by the client, as well as some properties of the standard `updDiscoveryEndpoint` used for discovery.</span></span> <span data-ttu-id="fdf32-146">Los <xref:System.ServiceModel.Discovery.FindCriteria> se modifican para utilizar un ámbito y un algoritmo `scopeMatchBy` concreto, así como los criterios de terminación personalizados.</span><span class="sxs-lookup"><span data-stu-id="fdf32-146">The <xref:System.ServiceModel.Discovery.FindCriteria> are modified to use a scope and a specific `scopeMatchBy` algorithm, as well as custom termination criteria.</span></span> <span data-ttu-id="fdf32-147">Además, el ejemplo también muestra el modo en que un cliente puede enviar elementos XML mediante mensajes `Probe`.</span><span class="sxs-lookup"><span data-stu-id="fdf32-147">Furthermore, the sample also shows how a client can send XML elements using `Probe` messages.</span></span> <span data-ttu-id="fdf32-148">Por último, se realizan algunos cambios en <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, como la versión del protocolo utilizado y los valores específicos del UDP, como se muestra en el siguiente archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="fdf32-148">Lastly, some changes are made to the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, such as the version of the protocol used and UDP-specific settings as shown in the following configuration file.</span></span>  
  
```xml  
<udpDiscoveryEndpoint>
        <!-- Specify the discovery protocol version and UDP transport settings. -->
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>
      </udpDiscoveryEndpoint>  
```  
  
 <span data-ttu-id="fdf32-149">Lo siguiente es el archivo de configuración de cliente completo usado en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fdf32-149">The following is the complete client configuration used in the sample.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
  
    <client>  
      <!--  Create an endpoint, make kind="dynamicEndpoint" and use the endpointConfiguration to change settings of DynamicEndpoint -->  
      <endpoint name="calculatorEndpoint"  
                binding="wsHttpBinding"  
                contract="ICalculatorService"  
                kind ="dynamicEndpoint"  
                endpointConfiguration="dynamicEndpointConfiguration">  
      </endpoint>  
    </client>  
  
    <standardEndpoints>  
  
      <dynamicEndpoint>
        <standardEndpoint name="dynamicEndpointConfiguration">  
          <discoveryClientSettings>  
            <!-- Controls where the discovery happens. In this case, Probe message is sent over UdpDiscoveryEndpoint. -->  
            <endpoint kind="udpDiscoveryEndpoint" endpointConfiguration="adhocDiscoveryEndpointConfiguration" />  
  
            <!-- Add Scopes, ScopeMatchBy, Extensions and termination criteria in FindCriteria -->  
            <findCriteria scopeMatchBy="http://schemas.microsoft.com/ws/2008/06/discovery/rfc" duration="00:00:10" maxResults="1">  
              <scopes>  
                <add scope="http://www.microsoft.com/building42/floor1"/>  
              </scopes>  
              <!-- These extensions are sent from the client to the service as part of the probe message -->  
              <extensions>  
                <CustomMetadata>This is custom metadata that is sent to the service along with the client's find request.</CustomMetadata>  
              </extensions>  
            </findCriteria>  
          </discoveryClientSettings>  
        </standardEndpoint>
      </dynamicEndpoint>  
  
      <udpDiscoveryEndpoint>
        <!-- Specify the discovery protocol version and UDP transport settings. -->
        <standardEndpoint name="adhocDiscoveryEndpointConfiguration" discoveryVersion="WSDiscovery11">  
          <transportSettings duplicateMessageHistoryLength="2048"  
                             maxPendingMessageCount="5"  
                             maxReceivedMessageSize="8192"  
                             maxBufferPoolSize="262144"/>  
        </standardEndpoint>
      </udpDiscoveryEndpoint>  
  
    </standardEndpoints>  
  
  </system.serviceModel>
</configuration>
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="fdf32-150">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdf32-150">To use this sample</span></span>  
  
1. <span data-ttu-id="fdf32-151">Este ejemplo utiliza los extremos HTTP y para ejecutarlo, se deben agregar las ACL de dirección URL apropiadas.</span><span class="sxs-lookup"><span data-stu-id="fdf32-151">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="fdf32-152">Para obtener más información, consulte [configuración de http y https](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="fdf32-152">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="fdf32-153">Al ejecutar el siguiente comando con privilegios elevados, se deberían agregar las ACL adecuadas.</span><span class="sxs-lookup"><span data-stu-id="fdf32-153">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="fdf32-154">Puede que desee sustituir su dominio y nombre de usuario para los siguientes argumentos si el comando no funciona como debería.</span><span class="sxs-lookup"><span data-stu-id="fdf32-154">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2. <span data-ttu-id="fdf32-155">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="fdf32-155">Build the solution.</span></span>  
  
3. <span data-ttu-id="fdf32-156">Ejecute el ejecutable de servicio desde el directorio de compilación.</span><span class="sxs-lookup"><span data-stu-id="fdf32-156">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="fdf32-157">Ejecute la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="fdf32-157">Run the client executable.</span></span> <span data-ttu-id="fdf32-158">Observe que el cliente puede localizar el servicio.</span><span class="sxs-lookup"><span data-stu-id="fdf32-158">Note that the client is able to locate the service.</span></span>  
