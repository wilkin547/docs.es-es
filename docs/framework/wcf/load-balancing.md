---
description: 'Más información acerca de: equilibrio de carga'
title: Equilibrio de carga
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: 9f7946793fb9a9eec9baf531e4650f68b92151d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732818"
---
# <a name="load-balancing"></a><span data-ttu-id="6d97e-103">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="6d97e-103">Load Balancing</span></span>

<span data-ttu-id="6d97e-104">Una manera de aumentar la capacidad de las aplicaciones de Windows Communication Foundation (WCF) es escalarlas horizontalmente mediante su implementación en una granja de servidores con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="6d97e-104">One way to increase the capacity of Windows Communication Foundation (WCF) applications is to scale them out by deploying them into a load-balanced server farm.</span></span> <span data-ttu-id="6d97e-105">Se puede equilibrar la carga de las aplicaciones WCF mediante técnicas de equilibrio de carga estándar, como equilibradores de carga de software como equilibrio de carga de red de Windows, así como dispositivos de equilibrio de carga basados en hardware.</span><span class="sxs-lookup"><span data-stu-id="6d97e-105">WCF applications can be load balanced using standard load balancing techniques, including software load balancers such as Windows Network Load Balancing as well as hardware-based load balancing appliances.</span></span>  
  
 <span data-ttu-id="6d97e-106">En las secciones siguientes se describen las consideraciones para el equilibrio de carga de aplicaciones WCF compiladas con varios enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="6d97e-106">The following sections discuss considerations for load balancing WCF applications built using various system-provided bindings.</span></span>  
  
## <a name="load-balancing-with-the-basic-http-binding"></a><span data-ttu-id="6d97e-107">Equilibrio de carga con el enlace HTTP básico</span><span class="sxs-lookup"><span data-stu-id="6d97e-107">Load Balancing with the Basic HTTP Binding</span></span>  

 <span data-ttu-id="6d97e-108">Desde la perspectiva del equilibrio de carga, las aplicaciones WCF que se comunican mediante <xref:System.ServiceModel.BasicHttpBinding> no son diferentes de otros tipos comunes de tráfico de red http (contenido HTML estático, páginas ASP.net o servicios web asmx).</span><span class="sxs-lookup"><span data-stu-id="6d97e-108">From the perspective of load balancing, WCF applications that communicate using the <xref:System.ServiceModel.BasicHttpBinding> are no different than other common types of HTTP network traffic (static HTML content, ASP.NET pages, or ASMX Web Services).</span></span> <span data-ttu-id="6d97e-109">Los canales WCF que usan este enlace son sin estado inherentemente y terminan sus conexiones cuando se cierra el canal.</span><span class="sxs-lookup"><span data-stu-id="6d97e-109">WCF channels that use this binding are inherently stateless, and terminate their connections when the channel closes.</span></span> <span data-ttu-id="6d97e-110">Como tal, <xref:System.ServiceModel.BasicHttpBinding> funciona bien con técnicas de equilibrio de carga de HTTP existentes.</span><span class="sxs-lookup"><span data-stu-id="6d97e-110">As such, the <xref:System.ServiceModel.BasicHttpBinding> works well with existing HTTP load balancing techniques.</span></span>  
  
 <span data-ttu-id="6d97e-111">De forma predeterminada, <xref:System.ServiceModel.BasicHttpBinding> envía un encabezado HTTP de conexión en mensajes con un valor `Keep-Alive`, que permite a los clientes establecer conexiones permanentes a los servicios que las admiten.</span><span class="sxs-lookup"><span data-stu-id="6d97e-111">By default, the <xref:System.ServiceModel.BasicHttpBinding> sends a connection HTTP header in messages with a `Keep-Alive` value, which enables clients to establish persistent connections to the services that support them.</span></span> <span data-ttu-id="6d97e-112">Esta configuración proporciona un rendimiento mejorado ya que las conexiones previamente establecidas se pueden reutilizar para enviar los mensajes subsiguientes al mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="6d97e-112">This configuration offers enhanced throughput because previously established connections can be reused to send subsequent messages to the same server.</span></span> <span data-ttu-id="6d97e-113">Sin embargo, la reutilización de la conexión puede hacer que los clientes se asocien con un servidor concreto dentro de la granja con la carga equilibrada, lo que reduce la eficacia del equilibrio de carga por turnos (round-robin).</span><span class="sxs-lookup"><span data-stu-id="6d97e-113">However, connection reuse may cause clients to become strongly associated to a specific server within the load-balanced farm, which reduces the effectiveness of round-robin load balancing.</span></span> <span data-ttu-id="6d97e-114">Si este comportamiento no es adecuado, `Keep-Alive` de HTTP puede estar deshabilitado en el servidor utilizando la propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> con <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6d97e-114">If this behavior is undesirable, HTTP `Keep-Alive` can be disabled on the server using the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property with a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="6d97e-115">En el ejemplo siguiente se muestra cómo hacerlo usando la configuración.</span><span class="sxs-lookup"><span data-stu-id="6d97e-115">The following example shows how to do this using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6d97e-116">Con la configuración simplificada introducida en .NET Framework 4, se puede lograr el mismo comportamiento mediante la siguiente configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="6d97e-116">Using the simplified configuration introduced in .NET Framework 4, the same behavior can be accomplished using the following simplified configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6d97e-117">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="6d97e-117">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a><span data-ttu-id="6d97e-118">Equilibrio de carga con los enlaces WSHttp y WSDualHttp</span><span class="sxs-lookup"><span data-stu-id="6d97e-118">Load Balancing with the WSHttp Binding and the WSDualHttp Binding</span></span>  

 <span data-ttu-id="6d97e-119"><xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> pueden tener la carga equilibrada gracias a las técnicas de equilibrio de carga de HTTP siempre que se hagan algunas modificaciones a la configuración de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6d97e-119">Both the <xref:System.ServiceModel.WSHttpBinding> and the <xref:System.ServiceModel.WSDualHttpBinding> can be load balanced using HTTP load balancing techniques provided several modifications are made to the default binding configuration.</span></span>  
  
- <span data-ttu-id="6d97e-120">Desactivar el establecimiento del contexto de seguridad o usar sesiones de seguridad con estado.</span><span class="sxs-lookup"><span data-stu-id="6d97e-120">Turn off Security Context Establishment or use stateful security sessions.</span></span> <span data-ttu-id="6d97e-121">El establecimiento del contexto de seguridad se puede desactivar estableciendo la <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> propiedad de <xref:System.ServiceModel.WSHttpBinding> en `false` .</span><span class="sxs-lookup"><span data-stu-id="6d97e-121">Security Context Establishment can be turned off by setting the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property on the <xref:System.ServiceModel.WSHttpBinding> to `false`.</span></span> <span data-ttu-id="6d97e-122">Si está utilizando <xref:System.ServiceModel.WSDualHttpBinding> o se requieren sesiones de seguridad, es posible usar sesiones de seguridad con estado como se describe en [sesiones seguras](./feature-details/secure-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="6d97e-122">If you are using <xref:System.ServiceModel.WSDualHttpBinding> or security sessions are required, it is possible to use stateful security sessions as described in [Secure Sessions](./feature-details/secure-sessions.md).</span></span> <span data-ttu-id="6d97e-123">Las sesiones de seguridad con estado permiten al servicio permanecer sin estado, ya que todo el estado de la sesión de seguridad se transmite con cada solicitud como parte del token de seguridad de protección.</span><span class="sxs-lookup"><span data-stu-id="6d97e-123">Stateful security sessions enable the service to remain stateless, as all of the state for the security session is transmitted with each request as a part of the protection security token.</span></span> <span data-ttu-id="6d97e-124">Para habilitar una sesión de seguridad con estado, debe usar <xref:System.ServiceModel.Channels.CustomBinding> o definido por el usuario <xref:System.ServiceModel.Channels.Binding> , ya que los valores de configuración necesarios no se exponen en el proporcionado por el sistema <xref:System.ServiceModel.WSHttpBinding> y en <xref:System.ServiceModel.WSDualHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="6d97e-124">To enable a stateful security session, you must use a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding>, as the necessary configuration settings are not exposed on the system-provided <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.WSDualHttpBinding>.</span></span>

- <span data-ttu-id="6d97e-125">Si desactiva el establecimiento del contexto de seguridad, también debe desactivar la negociación de credenciales de servicio.</span><span class="sxs-lookup"><span data-stu-id="6d97e-125">If you turn off Security Context Establishment, you also need to turn off Service Credential Negotiation.</span></span> <span data-ttu-id="6d97e-126">Para desactivarla, establezca la <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential> propiedad en <xref:System.ServiceModel.WSHttpBinding> `false` .</span><span class="sxs-lookup"><span data-stu-id="6d97e-126">To turn it off, set the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential> property on the <xref:System.ServiceModel.WSHttpBinding> to `false`.</span></span> <span data-ttu-id="6d97e-127">Para deshabilitar la negociación de credenciales de servicio, es posible que tenga que especificar explícitamente la identidad del punto de conexión en el cliente.</span><span class="sxs-lookup"><span data-stu-id="6d97e-127">To disable Service Credential Negotiation, you may need to explicitly specify the endpoint identity on the client.</span></span>
  
- <span data-ttu-id="6d97e-128">No utilice las sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="6d97e-128">Do not use reliable sessions.</span></span> <span data-ttu-id="6d97e-129">Esta característica está desactivada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6d97e-129">This feature is off by default.</span></span>  
  
## <a name="load-balancing-the-nettcp-binding"></a><span data-ttu-id="6d97e-130">Equilibrio de carga del enlace Net.TCP</span><span class="sxs-lookup"><span data-stu-id="6d97e-130">Load Balancing the Net.TCP Binding</span></span>  

 <span data-ttu-id="6d97e-131">Puede equilibrarse la carga de <xref:System.ServiceModel.NetTcpBinding> mediante técnicas de equilibrio de carga de nivel IP.</span><span class="sxs-lookup"><span data-stu-id="6d97e-131">The <xref:System.ServiceModel.NetTcpBinding> can be load balanced using IP-layer load balancing techniques.</span></span> <span data-ttu-id="6d97e-132">Sin embargo, <xref:System.ServiceModel.NetTcpBinding> agrupa de forma predeterminada las conexiones TCP para reducir la latencia de conexión.</span><span class="sxs-lookup"><span data-stu-id="6d97e-132">However, the <xref:System.ServiceModel.NetTcpBinding> pools TCP connections by default to reduce connection latency.</span></span> <span data-ttu-id="6d97e-133">Ésta es una optimización que interfiere con el mecanismo básico del equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="6d97e-133">This is an optimization that interferes with the basic mechanism of load balancing.</span></span> <span data-ttu-id="6d97e-134">El valor de configuración principal para optimizar <xref:System.ServiceModel.NetTcpBinding> es el tiempo de espera de la concesión, que forma parte de la configuración del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="6d97e-134">The primary configuration value for optimizing the <xref:System.ServiceModel.NetTcpBinding> is the lease timeout, which is part of the Connection Pool Settings.</span></span> <span data-ttu-id="6d97e-135">La agrupación de conexiones produce conexiones de cliente que se asociarán a servidores concretos dentro de la granja.</span><span class="sxs-lookup"><span data-stu-id="6d97e-135">Connection pooling causes client connections to become associated to specific servers within the farm.</span></span> <span data-ttu-id="6d97e-136">Como la duración de esas conexiones aumenta (un factor controlado por el valor de tiempo de espera de la concesión), la distribución de carga en varios servidores de la granja pasa a estar sin equilibrar.</span><span class="sxs-lookup"><span data-stu-id="6d97e-136">As the lifetime of those connections increase (a factor controlled by the lease timeout setting), the load distribution across various servers in the farm becomes unbalanced.</span></span> <span data-ttu-id="6d97e-137">Como resultado, aumentará el tiempo medio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6d97e-137">As a result the average call time increases.</span></span> <span data-ttu-id="6d97e-138">Así, al utilizar <xref:System.ServiceModel.NetTcpBinding> en escenarios con carga equilibrada, considere reducir el tiempo de espera de concesión predeterminado utilizado por el enlace.</span><span class="sxs-lookup"><span data-stu-id="6d97e-138">So when using the <xref:System.ServiceModel.NetTcpBinding> in load-balanced scenarios, consider reducing the default lease timeout used by the binding.</span></span> <span data-ttu-id="6d97e-139">Un tiempo de espera de concesión de 30 segundos es un punto de inicio razonable para los escenarios con carga equilibrada, aunque el valor óptimo depende de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6d97e-139">A 30-second lease timeout is a reasonable starting point for load-balanced scenarios, although the optimal value is application-dependent.</span></span> <span data-ttu-id="6d97e-140">Para obtener más información sobre el tiempo de espera de concesión de canal y otras cuotas de transporte, consulte [cuotas de transporte](./feature-details/transport-quotas.md).</span><span class="sxs-lookup"><span data-stu-id="6d97e-140">For more information about the channel lease timeout and other transport quotas, see [Transport Quotas](./feature-details/transport-quotas.md).</span></span>  
  
 <span data-ttu-id="6d97e-141">Para obtener el máximo rendimiento en escenarios con carga equilibrada, considere utilizar <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> o <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span><span class="sxs-lookup"><span data-stu-id="6d97e-141">For best performance in load-balanced scenarios, consider using <xref:System.ServiceModel.NetTcpSecurity> (either <xref:System.ServiceModel.SecurityMode.Transport> or <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d97e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d97e-142">See also</span></span>

- [<span data-ttu-id="6d97e-143">Procedimientos recomendados de hospedaje de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="6d97e-143">Internet Information Services Hosting Best Practices</span></span>](./feature-details/internet-information-services-hosting-best-practices.md)
