---
title: '&lt;NET.TCP&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 9312d5f7544a794f036f0a623df0d537eb96d145
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltnettcpgt"></a><span data-ttu-id="a6ba8-102">&lt;NET.TCP&gt;</span><span class="sxs-lookup"><span data-stu-id="a6ba8-102">&lt;net.tcp&gt;</span></span>
<span data-ttu-id="a6ba8-103">Especifica la configuración del servicio de uso compartido de puertos NET.TCP, que permite que varios procesos compartan el mismo puerto TCP.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-103">Specifies configuration settings for the NET.TCP Port Sharing Service, which allows multiple processes to share the same TCP port.</span></span>  
  
 <span data-ttu-id="a6ba8-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="a6ba8-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="a6ba8-105">\<NET.TCP ></span><span class="sxs-lookup"><span data-stu-id="a6ba8-105">\<net.tcp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ba8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6ba8-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="a6ba8-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="a6ba8-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6ba8-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6ba8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a6ba8-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6ba8-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6ba8-110">Attributes</span></span>  
  
|<span data-ttu-id="a6ba8-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6ba8-111">Attribute</span></span>|<span data-ttu-id="a6ba8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ba8-112">Description</span></span>|  
|---------------|-----------------|  
|`listenBacklog`|<span data-ttu-id="a6ba8-113">Un entero que especifica el número máximo de conexiones pendiente que se acepta desde la conexión compartida, pero todavía no se envían a los servicios de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a6ba8-113">An integer that specifies the maximum outstanding connections that are accepted from the shared connection, but are not yet dispatched to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="a6ba8-114">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-114">The default is 10.</span></span>|  
|`maxPendingAccepts`|<span data-ttu-id="a6ba8-115">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-115">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="a6ba8-116">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-116">The default is 2.</span></span>|  
|`MaxPendingConnections`|<span data-ttu-id="a6ba8-117">Número máximo de conexiones que el agente de escucha puede tener en espera de aceptación por parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-117">The maximum number of connections that the listener can have waiting to be accepted by the application.</span></span> <span data-ttu-id="a6ba8-118">Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-118">When this quota value is exceeded, new incoming connections are dropped rather than waiting to be accepted.</span></span> <span data-ttu-id="a6ba8-119">Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-119">Connection features such as message security can cause a client to open more than one connection.</span></span> <span data-ttu-id="a6ba8-120">Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-120">Service administrators should account for these additional connections when setting this quota value.</span></span> <span data-ttu-id="a6ba8-121">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-121">The default is 10.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="a6ba8-122">Un `TimeSpan` que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-122">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="a6ba8-123">El valor predeterminado es "00:00:10".</span><span class="sxs-lookup"><span data-stu-id="a6ba8-123">The default is "00:00:10".</span></span>|  
|`teredoEnabled`|<span data-ttu-id="a6ba8-124">Un valor booleano que indica si el servicio de uso compartido de puerto utiliza el servicio Microsoft Teredo para realizar escuchas en puertos TCP en nombre de los servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6ba8-124">A Boolean value that indicates whether the port sharing service uses Microsoft Teredo service to listen on TCP ports on behalf of [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services.</span></span> <span data-ttu-id="a6ba8-125">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-125">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6ba8-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6ba8-126">Child Elements</span></span>  
  
|<span data-ttu-id="a6ba8-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6ba8-127">Element</span></span>|<span data-ttu-id="a6ba8-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ba8-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ba8-129">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="a6ba8-129">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="a6ba8-130">Una colección de elementos de configuración que contiene un atributo `securityIdentifier` que especifica cuentas de usuario para los procesos que hospedan servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y se concede el acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-130">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6ba8-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6ba8-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a6ba8-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6ba8-132">Element</span></span>|<span data-ttu-id="a6ba8-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6ba8-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6ba8-134">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="a6ba8-134">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="a6ba8-135">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="a6ba8-135">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6ba8-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6ba8-136">Remarks</span></span>  
 <span data-ttu-id="a6ba8-137">Para obtener más información sobre el uso compartido de puertos, consulte [uso compartido de puertos Net.TCP](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded).</span><span class="sxs-lookup"><span data-stu-id="a6ba8-137">For more information on port sharing, see [Net.TCP Port Sharing](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded).</span></span> <span data-ttu-id="a6ba8-138">Para entender cómo configurar el puerto de servicio de uso compartido, vea [configurar el servicio de uso compartido de puertos Net.TCP](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span><span class="sxs-lookup"><span data-stu-id="a6ba8-138">To understand how to configure the port sharing service, see [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ba8-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ba8-139">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [<span data-ttu-id="a6ba8-140">Uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a6ba8-140">Net.TCP Port Sharing</span></span>](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [<span data-ttu-id="a6ba8-141">Configuración del servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a6ba8-141">Configuring the Net.TCP Port Sharing Service</span></span>](http://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
