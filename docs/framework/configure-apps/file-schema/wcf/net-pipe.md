---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: ddd25d3d25f4c4be1a9e26d444fa799a55c9cccc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283288"
---
# <a name="netpipe"></a><span data-ttu-id="4c82e-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="4c82e-102">\<net.pipe></span></span>
<span data-ttu-id="4c82e-103">Especifica la configuración para el Servicio de Activación de Canalización con nombre que administra la duración de la conexión de canalización con nombre y administra solicitudes de activación que llegan sobre las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="4c82e-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="4c82e-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4c82e-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="4c82e-105">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="4c82e-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c82e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c82e-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <net.pipe maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              receiveTimeout="TimeSpan">
      <allowAccounts>
        <!-- LocalSystem account -->
        <add securityIdentifier="S-1-5-18" />
        <!-- LocalService account -->
        <add securityIdentifier="S-1-5-19" />
        <!-- Administrators account -->
        <add securityIdentifier="S-1-5-20" />
        <!-- Network Service account -->
        <add securityIdentifier="S-1-5-32-544" />
        <!-- IIS_IUSRS account (Vista only) -->
        <add securityIdentifier="S-1-5-32-568" />
      </allowAccounts>
    </net.pipe>
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a><span data-ttu-id="4c82e-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="4c82e-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c82e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4c82e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4c82e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4c82e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c82e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4c82e-110">Attributes</span></span>  
  
|<span data-ttu-id="4c82e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4c82e-111">Attribute</span></span>|<span data-ttu-id="4c82e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c82e-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="4c82e-113">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="4c82e-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="4c82e-114">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="4c82e-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="4c82e-115">Un entero que especifica el número máximo de conexiones que pueden esperar para ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="4c82e-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="4c82e-116">El valor predeterminado es 100.</span><span class="sxs-lookup"><span data-stu-id="4c82e-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="4c82e-117">Un `TimeSpan` que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="4c82e-117">A `TimeSpan` that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="4c82e-118">El valor predeterminado es 00:00:10</span><span class="sxs-lookup"><span data-stu-id="4c82e-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c82e-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4c82e-119">Child Elements</span></span>  
  
|<span data-ttu-id="4c82e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c82e-120">Element</span></span>|<span data-ttu-id="4c82e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c82e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c82e-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="4c82e-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="4c82e-123">Una colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedidos acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="4c82e-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c82e-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4c82e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4c82e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c82e-125">Element</span></span>|<span data-ttu-id="4c82e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c82e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c82e-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="4c82e-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="4c82e-128">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="4c82e-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c82e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c82e-129">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
