---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: 885cfad7be42f7c48b4c061f3293d667eb5d4ad8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103407"
---
# <a name="netpipe"></a><span data-ttu-id="2edb9-102">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="2edb9-102">\<net.pipe></span></span>
<span data-ttu-id="2edb9-103">Especifica la configuración para el Servicio de Activación de Canalización con nombre que administra la duración de la conexión de canalización con nombre y administra solicitudes de activación que llegan sobre las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="2edb9-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
 <span data-ttu-id="2edb9-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="2edb9-104">\<system.serviceModel.activation></span></span>  
<span data-ttu-id="2edb9-105">\<net.pipe></span><span class="sxs-lookup"><span data-stu-id="2edb9-105">\<net.pipe></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2edb9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2edb9-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="2edb9-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="2edb9-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2edb9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2edb9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2edb9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2edb9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2edb9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2edb9-110">Attributes</span></span>  
  
|<span data-ttu-id="2edb9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2edb9-111">Attribute</span></span>|<span data-ttu-id="2edb9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2edb9-112">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="2edb9-113">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="2edb9-113">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="2edb9-114">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="2edb9-114">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="2edb9-115">Un entero que especifica el número máximo de conexiones que pueden esperar para ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="2edb9-115">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="2edb9-116">El valor predeterminado es 100.</span><span class="sxs-lookup"><span data-stu-id="2edb9-116">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="2edb9-117">Un <xref:System.TimeSpan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="2edb9-117">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="2edb9-118">El valor predeterminado es 00:00:10</span><span class="sxs-lookup"><span data-stu-id="2edb9-118">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2edb9-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2edb9-119">Child Elements</span></span>  
  
|<span data-ttu-id="2edb9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2edb9-120">Element</span></span>|<span data-ttu-id="2edb9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="2edb9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2edb9-122">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="2edb9-122">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="2edb9-123">Una colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedidos acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="2edb9-123">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2edb9-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2edb9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2edb9-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2edb9-125">Element</span></span>|<span data-ttu-id="2edb9-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="2edb9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2edb9-127">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="2edb9-127">\<system.serviceModel.activation></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|<span data-ttu-id="2edb9-128">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="2edb9-128">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2edb9-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2edb9-129">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
