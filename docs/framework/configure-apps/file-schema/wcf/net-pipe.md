---
title: <net.pipe>
ms.date: 03/30/2017
ms.assetid: 6a0f0318-f8f6-466c-9fae-199d7274a82e
ms.openlocfilehash: d070b822cefeef3c281d5b0e47411f4c624dd83f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204611"
---
# \<net.pipe>

<span data-ttu-id="ce1a3-102">Especifica la configuración para el Servicio de Activación de Canalización con nombre que administra la duración de la conexión de canalización con nombre y administra solicitudes de activación que llegan sobre las canalizaciones con nombre.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-102">Specifies configuration settings for the Named Pipe Activation Service, which manages the lifetime of the named pipe connection, and handles activation requests that arrive over named pipes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.pipe>**  
  
## <a name="syntax"></a><span data-ttu-id="ce1a3-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce1a3-103">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="ce1a3-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="ce1a3-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce1a3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ce1a3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ce1a3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce1a3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce1a3-107">Attributes</span></span>  
  
|<span data-ttu-id="ce1a3-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ce1a3-108">Attribute</span></span>|<span data-ttu-id="ce1a3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce1a3-109">Description</span></span>|  
|---------------|-----------------|  
|`maxPendingAccepts`|<span data-ttu-id="ce1a3-110">Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-110">An integer that specifies the maximum outstanding concurrent accepting threads on the listening endpoint for the sharing service.</span></span> <span data-ttu-id="ce1a3-111">El valor predeterminado es 2.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-111">The default is 2.</span></span>|  
|`maxPendingConnections`|<span data-ttu-id="ce1a3-112">Un entero que especifica el número máximo de conexiones que pueden esperar para ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-112">An integer that specifies the maximum number of connections that can wait for dispatch.</span></span> <span data-ttu-id="ce1a3-113">El valor predeterminado es 100.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-113">The default is 100.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ce1a3-114">Un <xref:System.TimeSpan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-114">A <xref:System.TimeSpan> that specifies the timeout for reading the framing data and performing connection dispatching from the underlining connections.</span></span> <span data-ttu-id="ce1a3-115">El valor predeterminado es 00:00:10</span><span class="sxs-lookup"><span data-stu-id="ce1a3-115">The default is "00:00:10"</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce1a3-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ce1a3-116">Child Elements</span></span>  
  
|<span data-ttu-id="ce1a3-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce1a3-117">Element</span></span>|<span data-ttu-id="ce1a3-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce1a3-118">Description</span></span>|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|<span data-ttu-id="ce1a3-119">Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-119">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce1a3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ce1a3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ce1a3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce1a3-121">Element</span></span>|<span data-ttu-id="ce1a3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce1a3-122">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|<span data-ttu-id="ce1a3-123">Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="ce1a3-123">Contains configuration settings for the listener process SMSvcHost.exe.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce1a3-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce1a3-124">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection>
