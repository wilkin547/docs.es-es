---
title: Equilibrio de carga
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: a43546b9cbb95cd16c1d94372e786acd103ea0bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921958"
---
# <a name="load-balancing"></a><span data-ttu-id="f50c2-102">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="f50c2-102">Load Balancing</span></span>
<span data-ttu-id="f50c2-103">Una manera de aumentar la capacidad de las aplicaciones de Windows Communication Foundation (WCF) es escalarlas implementándolas en una granja de servidores con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="f50c2-103">One way to increase the capacity of Windows Communication Foundation (WCF) applications is to scale them out by deploying them into a load-balanced server farm.</span></span> <span data-ttu-id="f50c2-104">Aplicaciones WCF pueden ser el equilibrio de carga mediante técnicas, incluidos los equilibradores de carga de software como Windows Network Load Balancing de equilibrio de carga estándar, así como dispositivos de equilibrio de carga basado en hardware.</span><span class="sxs-lookup"><span data-stu-id="f50c2-104">WCF applications can be load balanced using standard load balancing techniques, including software load balancers such as Windows Network Load Balancing as well as hardware-based load balancing appliances.</span></span>  
  
 <span data-ttu-id="f50c2-105">Las secciones siguientes describen consideraciones para las aplicaciones de WCF compiladas con varios enlaces proporcionados por el sistema de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="f50c2-105">The following sections discuss considerations for load balancing WCF applications built using various system-provided bindings.</span></span>  
  
## <a name="load-balancing-with-the-basic-http-binding"></a><span data-ttu-id="f50c2-106">Equilibrio de carga con el enlace HTTP básico</span><span class="sxs-lookup"><span data-stu-id="f50c2-106">Load Balancing with the Basic HTTP Binding</span></span>  
 <span data-ttu-id="f50c2-107">Desde la perspectiva del equilibrio de carga, las aplicaciones WCF que se comunican mediante el <xref:System.ServiceModel.BasicHttpBinding> no son diferentes de otros tipos comunes de HTTP (estáticos contenido HTML, páginas ASP.NET o servicios Web ASMX) el tráfico de red.</span><span class="sxs-lookup"><span data-stu-id="f50c2-107">From the perspective of load balancing, WCF applications that communicate using the <xref:System.ServiceModel.BasicHttpBinding> are no different than other common types of HTTP network traffic (static HTML content, ASP.NET pages, or ASMX Web Services).</span></span> <span data-ttu-id="f50c2-108">Los canales WCF que usan este enlace son inherentemente sin estado y terminan sus conexiones cuando se cierra el canal.</span><span class="sxs-lookup"><span data-stu-id="f50c2-108">WCF channels that use this binding are inherently stateless, and terminate their connections when the channel closes.</span></span> <span data-ttu-id="f50c2-109">Como tal, <xref:System.ServiceModel.BasicHttpBinding> funciona bien con técnicas de equilibrio de carga de HTTP existentes.</span><span class="sxs-lookup"><span data-stu-id="f50c2-109">As such, the <xref:System.ServiceModel.BasicHttpBinding> works well with existing HTTP load balancing techniques.</span></span>  
  
 <span data-ttu-id="f50c2-110">De forma predeterminada, <xref:System.ServiceModel.BasicHttpBinding> envía un encabezado HTTP de conexión en mensajes con un valor `Keep-Alive`, que permite a los clientes establecer conexiones permanentes a los servicios que las admiten.</span><span class="sxs-lookup"><span data-stu-id="f50c2-110">By default, the <xref:System.ServiceModel.BasicHttpBinding> sends a connection HTTP header in messages with a `Keep-Alive` value, which enables clients to establish persistent connections to the services that support them.</span></span> <span data-ttu-id="f50c2-111">Esta configuración proporciona un rendimiento mejorado ya que las conexiones previamente establecidas se pueden reutilizar para enviar los mensajes subsiguientes al mismo servidor.</span><span class="sxs-lookup"><span data-stu-id="f50c2-111">This configuration offers enhanced throughput because previously established connections can be reused to send subsequent messages to the same server.</span></span> <span data-ttu-id="f50c2-112">Sin embargo, la reutilización de la conexión puede hacer que los clientes se asocien con un servidor concreto dentro de la granja con la carga equilibrada, lo que reduce la eficacia del equilibrio de carga por turnos (round-robin).</span><span class="sxs-lookup"><span data-stu-id="f50c2-112">However, connection reuse may cause clients to become strongly associated to a specific server within the load-balanced farm, which reduces the effectiveness of round-robin load balancing.</span></span> <span data-ttu-id="f50c2-113">Si este comportamiento no es adecuado, `Keep-Alive` de HTTP puede estar deshabilitado en el servidor utilizando la propiedad <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> con <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f50c2-113">If this behavior is undesirable, HTTP `Keep-Alive` can be disabled on the server using the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property with a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="f50c2-114">En el ejemplo siguiente se muestra cómo hacerlo usando la configuración.</span><span class="sxs-lookup"><span data-stu-id="f50c2-114">The following example shows how to do this using configuration.</span></span>  
  
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
  
 <span data-ttu-id="f50c2-115">Si se usa la configuración simplificada presentada en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], se puede lograr el mismo comportamiento mediante la siguiente configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="f50c2-115">Using the simplified configuration introduced in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], the same behavior can be accomplished using the following simplified configuration.</span></span>  
  
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
  
 <span data-ttu-id="f50c2-116">Para obtener más información sobre los puntos de conexión, enlaces y comportamientos predeterminados, vea [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="f50c2-116">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a><span data-ttu-id="f50c2-117">Equilibrio de carga con los enlaces WSHttp y WSDualHttp</span><span class="sxs-lookup"><span data-stu-id="f50c2-117">Load Balancing with the WSHttp Binding and the WSDualHttp Binding</span></span>  
 <span data-ttu-id="f50c2-118"><xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> pueden tener la carga equilibrada gracias a las técnicas de equilibrio de carga de HTTP siempre que se hagan algunas modificaciones a la configuración de enlace predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f50c2-118">Both the <xref:System.ServiceModel.WSHttpBinding> and the <xref:System.ServiceModel.WSDualHttpBinding> can be load balanced using HTTP load balancing techniques provided several modifications are made to the default binding configuration.</span></span>  
  
-   <span data-ttu-id="f50c2-119">Desactive el establecimiento del contexto de seguridad: puede lograrse definiendo la propiedad <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> de <xref:System.ServiceModel.WSHttpBinding> en `false`.</span><span class="sxs-lookup"><span data-stu-id="f50c2-119">Turn off Security Context Establishment: this can be accomplished by the setting the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property on the <xref:System.ServiceModel.WSHttpBinding> to `false`.</span></span> <span data-ttu-id="f50c2-120">Como alternativa, si son necesarias las sesiones de seguridad, es posible usar las sesiones de seguridad con estado, como se describe en el [sesiones seguras](../../../docs/framework/wcf/feature-details/secure-sessions.md) tema.</span><span class="sxs-lookup"><span data-stu-id="f50c2-120">Alternatively, if security sessions are required, it is possible to use stateful security sessions as described in the [Secure Sessions](../../../docs/framework/wcf/feature-details/secure-sessions.md) topic.</span></span> <span data-ttu-id="f50c2-121">Las sesiones de seguridad con estado permiten al servicio seguir estando sin estado ya que se transmitirá todo el estado para la sesión de seguridad con cada solicitud como parte del token de seguridad de protección.</span><span class="sxs-lookup"><span data-stu-id="f50c2-121">Stateful security sessions enable the service to remain stateless as all of the state for the security session is transmitted with each request as a part of the protection security token.</span></span> <span data-ttu-id="f50c2-122">Tenga en cuenta que para habilitar una sesión de seguridad con estado, es necesario utilizar <xref:System.ServiceModel.Channels.CustomBinding> o <xref:System.ServiceModel.Channels.Binding> definido por el usuario ya que no se exponen los valores de configuración necesarios en <xref:System.ServiceModel.WSHttpBinding> y <xref:System.ServiceModel.WSDualHttpBinding> que son proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="f50c2-122">Note that to enable a stateful security session, it is necessary to use a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding> as the necessary configuration settings are not exposed on <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.WSDualHttpBinding> that are provided by the system.</span></span>  
  
-   <span data-ttu-id="f50c2-123">No utilice las sesiones confiables.</span><span class="sxs-lookup"><span data-stu-id="f50c2-123">Do not use reliable sessions.</span></span> <span data-ttu-id="f50c2-124">Esta característica está desactivada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f50c2-124">This feature is off by default.</span></span>  
  
## <a name="load-balancing-the-nettcp-binding"></a><span data-ttu-id="f50c2-125">Equilibrio de carga del enlace Net.TCP</span><span class="sxs-lookup"><span data-stu-id="f50c2-125">Load Balancing the Net.TCP Binding</span></span>  
 <span data-ttu-id="f50c2-126">Puede equilibrarse la carga de <xref:System.ServiceModel.NetTcpBinding> mediante técnicas de equilibrio de carga de nivel IP.</span><span class="sxs-lookup"><span data-stu-id="f50c2-126">The <xref:System.ServiceModel.NetTcpBinding> can be load balanced using IP-layer load balancing techniques.</span></span> <span data-ttu-id="f50c2-127">Sin embargo, <xref:System.ServiceModel.NetTcpBinding> agrupa de forma predeterminada las conexiones TCP para reducir la latencia de conexión.</span><span class="sxs-lookup"><span data-stu-id="f50c2-127">However, the <xref:System.ServiceModel.NetTcpBinding> pools TCP connections by default to reduce connection latency.</span></span> <span data-ttu-id="f50c2-128">Ésta es una optimización que interfiere con el mecanismo básico del equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="f50c2-128">This is an optimization that interferes with the basic mechanism of load balancing.</span></span> <span data-ttu-id="f50c2-129">El valor de configuración principal para optimizar <xref:System.ServiceModel.NetTcpBinding> es el tiempo de espera de la concesión, que forma parte de la configuración del grupo de conexiones.</span><span class="sxs-lookup"><span data-stu-id="f50c2-129">The primary configuration value for optimizing the <xref:System.ServiceModel.NetTcpBinding> is the lease timeout, which is part of the Connection Pool Settings.</span></span> <span data-ttu-id="f50c2-130">La agrupación de conexiones produce conexiones de cliente que se asociarán a servidores concretos dentro de la granja.</span><span class="sxs-lookup"><span data-stu-id="f50c2-130">Connection pooling causes client connections to become associated to specific servers within the farm.</span></span> <span data-ttu-id="f50c2-131">Como la duración de esas conexiones aumenta (un factor controlado por el valor de tiempo de espera de la concesión), la distribución de carga en varios servidores de la granja pasa a estar sin equilibrar.</span><span class="sxs-lookup"><span data-stu-id="f50c2-131">As the lifetime of those connections increase (a factor controlled by the lease timeout setting), the load distribution across various servers in the farm becomes unbalanced.</span></span> <span data-ttu-id="f50c2-132">Como resultado, aumentará el tiempo medio de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f50c2-132">As a result the average call time increases.</span></span> <span data-ttu-id="f50c2-133">Así, al utilizar <xref:System.ServiceModel.NetTcpBinding> en escenarios con carga equilibrada, considere reducir el tiempo de espera de concesión predeterminado utilizado por el enlace.</span><span class="sxs-lookup"><span data-stu-id="f50c2-133">So when using the <xref:System.ServiceModel.NetTcpBinding> in load-balanced scenarios, consider reducing the default lease timeout used by the binding.</span></span> <span data-ttu-id="f50c2-134">Un tiempo de espera de concesión de 30 segundos es un punto de inicio razonable para los escenarios con carga equilibrada, aunque el valor óptimo depende de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f50c2-134">A 30-second lease timeout is a reasonable starting point for load-balanced scenarios, although the optimal value is application-dependent.</span></span> <span data-ttu-id="f50c2-135">Para obtener más información sobre el tiempo de espera de concesión de canal y otras cuotas de transporte, vea [las cuotas de transporte](../../../docs/framework/wcf/feature-details/transport-quotas.md).</span><span class="sxs-lookup"><span data-stu-id="f50c2-135">For more information about the channel lease timeout and other transport quotas, see [Transport Quotas](../../../docs/framework/wcf/feature-details/transport-quotas.md).</span></span>  
  
 <span data-ttu-id="f50c2-136">Para obtener el máximo rendimiento en escenarios con carga equilibrada, considere utilizar <xref:System.ServiceModel.NetTcpSecurity> (<xref:System.ServiceModel.SecurityMode.Transport> o <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span><span class="sxs-lookup"><span data-stu-id="f50c2-136">For best performance in load-balanced scenarios, consider using <xref:System.ServiceModel.NetTcpSecurity> (either <xref:System.ServiceModel.SecurityMode.Transport> or <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50c2-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f50c2-137">See also</span></span>

- [<span data-ttu-id="f50c2-138">Procedimientos recomendados de hospedaje de Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="f50c2-138">Internet Information Services Hosting Best Practices</span></span>](../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
