---
description: 'Más información acerca de: <net. Pipe>'
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: d95aebc62ab92b91c1633a99d8311b55bfaaf0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684079"
---
# \<net.pipe>

<span data-ttu-id="8bab6-103">Especifica la configuración para el Servicio de Activación de Canalización con nombre que administra la duración de la conexión de canalización con nombre y administra solicitudes de activación que llegan sobre las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="8bab6-103">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="8bab6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bab6-104">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="8bab6-105">Tipo</span><span class="sxs-lookup"><span data-stu-id="8bab6-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bab6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8bab6-106">Attributes and Elements</span></span>  

 <span data-ttu-id="8bab6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8bab6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bab6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8bab6-108">Attributes</span></span>  
  
|<span data-ttu-id="8bab6-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="8bab6-109">Attribute</span></span>|<span data-ttu-id="8bab6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bab6-110">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="8bab6-111">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="8bab6-111">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="8bab6-112">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="8bab6-112">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="8bab6-113">Un entero que especifica el número máximo de conexiones que pueden esperar para ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="8bab6-113">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="8bab6-114">El valor predeterminado es 100.</span><span class="sxs-lookup"><span data-stu-id="8bab6-114">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="8bab6-115">Un <xref:System.TimeSpan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="8bab6-115">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="8bab6-116">El valor predeterminado es 00:00:10</span><span class="sxs-lookup"><span data-stu-id="8bab6-116">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bab6-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8bab6-117">Child Elements</span></span>  
  
|<span data-ttu-id="8bab6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bab6-118">Element</span></span>|<span data-ttu-id="8bab6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bab6-119">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="8bab6-120">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="8bab6-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bab6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8bab6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8bab6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bab6-122">Element</span></span>|<span data-ttu-id="8bab6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bab6-123">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="8bab6-124">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="8bab6-124">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bab6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bab6-125">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
