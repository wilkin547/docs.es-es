---
description: 'Más información acerca de: <net. TCP>'
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: b7b36e0309139508011e5abceab97cc6f6f9a53d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786946"
---
# \<net.tcp>

<span data-ttu-id="2eee8-103">Especifica la configuración del servicio de uso compartido de puertos NET.TCP, que permite que varios procesos compartan el mismo puerto TCP.</span><span class="sxs-lookup"><span data-stu-id="2eee8-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
## <a name="syntax"></a><span data-ttu-id="2eee8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2eee8-104">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.tcp listenBacklog="Integer"
             maxPendingAccepts="Integer"
             maxPendingConnections="Integer"
             receiveTimeout="TimeSpan"
             teredoEnabled="Boolean">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18"/>
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19"/>
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20"/>
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only)-->
        <add securityIdentifier="S-1-5-32-568"/>
      </allowAccounts>
    </net.tcp>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="2eee8-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="2eee8-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2eee8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2eee8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2eee8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2eee8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2eee8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2eee8-108">Attributes</span></span>  
  
|<span data-ttu-id="2eee8-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="2eee8-109">Attribute</span></span>|<span data-ttu-id="2eee8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2eee8-110">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="2eee8-111">Un entero que especifica las conexiones pendientes máximas que se aceptan desde la conexión compartida, pero que todavía no se envían a los servicios Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2eee8-111">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="2eee8-112">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="2eee8-112">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="2eee8-113">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="2eee8-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="2eee8-114">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="2eee8-114">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="2eee8-115">Número máximo de conexiones que el agente de escucha puede tener en espera de aceptación por parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2eee8-115">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="2eee8-116">Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas.</span><span class="sxs-lookup"><span data-stu-id="2eee8-116">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="2eee8-117">Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión.</span><span class="sxs-lookup"><span data-stu-id="2eee8-117">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="2eee8-118">Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota.</span><span class="sxs-lookup"><span data-stu-id="2eee8-118">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="2eee8-119">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="2eee8-119">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="2eee8-120">Un <xref:System.TimeSpan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="2eee8-120">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="2eee8-121">El valor predeterminado es "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="2eee8-121">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="2eee8-122">Valor booleano que indica si el servicio de uso compartido de puertos utiliza el servicio Microsoft Teredo para realizar escuchas en puertos TCP en nombre de los servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="2eee8-122">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="2eee8-123">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="2eee8-123">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2eee8-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2eee8-124">Child Elements</span></span>  
  
|<span data-ttu-id="2eee8-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2eee8-125">Element</span></span>|<span data-ttu-id="2eee8-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="2eee8-126">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="2eee8-127">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="2eee8-127">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2eee8-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2eee8-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2eee8-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="2eee8-129">Element</span></span>|<span data-ttu-id="2eee8-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="2eee8-130">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="2eee8-131">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="2eee8-131">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2eee8-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2eee8-132">Remarks</span></span>  

 <span data-ttu-id="2eee8-133">Para obtener más información sobre el uso compartido de puertos, consulte [uso compartido de puertos net. TCP](../../../wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="2eee8-133">For more information on port sharing, see [Net.TCP Port Sharing](../../../wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="2eee8-134">Para saber cómo configurar el servicio de uso compartido de puertos, vea [configurar el servicio de uso compartido de puertos net. TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="2eee8-134">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eee8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="2eee8-135">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="2eee8-136">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="2eee8-136">Net.TCP Port Sharing</span></span>](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="2eee8-137">Configuración del servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="2eee8-137">Configuring the Net.TCP Port Sharing Service</span></span>](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
