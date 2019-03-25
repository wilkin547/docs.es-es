---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 692c4cf6688bfc2f9b99f065f4b16711f7f08063
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412050"
---
# <a name="nettcp"></a><span data-ttu-id="805e4-102">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="805e4-102">\<net.tcp></span></span>
<span data-ttu-id="805e4-103">Especifica la configuración del servicio de uso compartido de puertos NET.TCP, que permite que varios procesos compartan el mismo puerto TCP.</span><span class="sxs-lookup"><span data-stu-id="805e4-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="805e4-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="805e4-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="805e4-105">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="805e4-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805e4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="805e4-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="805e4-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="805e4-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="805e4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="805e4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="805e4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="805e4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="805e4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="805e4-110">Attributes</span></span>  
  
|<span data-ttu-id="805e4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="805e4-111">Attribute</span></span>|<span data-ttu-id="805e4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="805e4-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="805e4-113">Un entero que especifica las conexiones pendientes máximas que se aceptan desde la conexión compartida, pero todavía no se envían a los servicios de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="805e4-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="805e4-114">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="805e4-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="805e4-115">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="805e4-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="805e4-116">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="805e4-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="805e4-117">Número máximo de conexiones que el agente de escucha puede tener en espera de aceptación por parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="805e4-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="805e4-118">Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas.</span><span class="sxs-lookup"><span data-stu-id="805e4-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="805e4-119">Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión.</span><span class="sxs-lookup"><span data-stu-id="805e4-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="805e4-120">Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota.</span><span class="sxs-lookup"><span data-stu-id="805e4-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="805e4-121">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="805e4-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="805e4-122">Un <xref:System.TimeSpan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="805e4-122">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="805e4-123">El valor predeterminado es "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="805e4-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="805e4-124">Un valor booleano que indica si el servicio de uso compartido de puerto utiliza el servicio Microsoft Teredo para realizar escuchas en puertos TCP en nombre de los servicios de WCF.</span><span class="sxs-lookup"><span data-stu-id="805e4-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of WCF services.</span></span> <span data-ttu-id="805e4-125">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="805e4-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="805e4-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="805e4-126">Child Elements</span></span>  
  
|<span data-ttu-id="805e4-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="805e4-127">Element</span></span>|<span data-ttu-id="805e4-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="805e4-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="805e4-129">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="805e4-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="805e4-130">Una colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedidos acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="805e4-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="805e4-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="805e4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="805e4-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="805e4-132">Element</span></span>|<span data-ttu-id="805e4-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="805e4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="805e4-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="805e4-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="805e4-135">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="805e4-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="805e4-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="805e4-136">Remarks</span></span>  
 <span data-ttu-id="805e4-137">Para obtener más información sobre el uso compartido de puertos, consulte [uso compartido de puertos Net.TCP](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span><span class="sxs-lookup"><span data-stu-id="805e4-137">For more information on port sharing, see [Net.TCP Port Sharing](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md).</span></span> <span data-ttu-id="805e4-138">Para comprender cómo configurar el puerto de servicio de uso compartido, consulte [configurar el servicio de uso compartido de puertos Net.TCP](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="805e4-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805e4-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="805e4-139">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [<span data-ttu-id="805e4-140">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="805e4-140">Net.TCP Port Sharing</span></span>](../../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)
- [<span data-ttu-id="805e4-141">Configuración del servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="805e4-141">Configuring the Net.TCP Port Sharing Service</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
