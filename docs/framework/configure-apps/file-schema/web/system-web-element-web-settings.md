---
title: Elemento <system.web> (configuración web)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152846"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="c80d0-102">\<system.web> Element (Configuración web)</span><span class="sxs-lookup"><span data-stu-id="c80d0-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="c80d0-103">Contiene información sobre cómo la capa de hospedaje de ASP.NET administra el comportamiento de todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="c80d0-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="c80d0-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="c80d0-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c80d0-105">&nbsp;&nbsp;**\<system.web>**</span><span class="sxs-lookup"><span data-stu-id="c80d0-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c80d0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c80d0-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c80d0-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c80d0-107">Attributes and Elements</span></span>  

<span data-ttu-id="c80d0-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c80d0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c80d0-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c80d0-109">Attributes</span></span>  

<span data-ttu-id="c80d0-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c80d0-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c80d0-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c80d0-111">Child Elements</span></span>  
  
|<span data-ttu-id="c80d0-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c80d0-112">Element</span></span>|<span data-ttu-id="c80d0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c80d0-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c80d0-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="c80d0-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="c80d0-115">Especifica la configuración de los grupos de aplicaciones IIS en un archivo aspnet.config.</span><span class="sxs-lookup"><span data-stu-id="c80d0-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c80d0-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c80d0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c80d0-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c80d0-117">Element</span></span>|<span data-ttu-id="c80d0-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c80d0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c80d0-119">\<configuración></span><span class="sxs-lookup"><span data-stu-id="c80d0-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="c80d0-120">Especifica el elemento raíz en cada archivo de configuración que usan las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c80d0-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c80d0-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c80d0-121">Remarks</span></span>  

<span data-ttu-id="c80d0-122">El `system.web` elemento y `applicationPool` su elemento secundario se agregaron a .NET Framework a partir de .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="c80d0-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="c80d0-123">Al ejecutar IIS 7.0 o versiones posteriores en modo integrado, esta combinación de elementos le permite configurar cómo ASP.NET administra los subprocesos y cómo pone en cola las solicitudes cuando se hospeda ASP.NET en un grupo de aplicaciones IIS.</span><span class="sxs-lookup"><span data-stu-id="c80d0-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="c80d0-124">Si ejecuta IIS 7.0 o versiones posteriores en modo clásico o ISAPI, se omite esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c80d0-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c80d0-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c80d0-125">Example</span></span>  

<span data-ttu-id="c80d0-126">En el ejemplo siguiente se muestra cómo configurar ASP.NET comportamiento de todo el proceso en el archivo aspnet.config cuando ASP.NET se hospeda en un grupo de aplicaciones IIS.</span><span class="sxs-lookup"><span data-stu-id="c80d0-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="c80d0-127">En el ejemplo se supone que IIS se ejecuta en modo integrado y que la aplicación usa .NET Framework 3.5 SP1 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="c80d0-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="c80d0-128">Este comportamiento no se produce en versiones de .NET Framework anteriores a .NET Framework 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="c80d0-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="c80d0-129">Los valores del ejemplo son los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c80d0-129">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="c80d0-130">Información de elemento</span><span class="sxs-lookup"><span data-stu-id="c80d0-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c80d0-131">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c80d0-131">Namespace</span></span>||  
|<span data-ttu-id="c80d0-132">Nombre del esquema</span><span class="sxs-lookup"><span data-stu-id="c80d0-132">Schema Name</span></span>||  
|<span data-ttu-id="c80d0-133">Archivo de validación</span><span class="sxs-lookup"><span data-stu-id="c80d0-133">Validation File</span></span>||  
|<span data-ttu-id="c80d0-134">Puede estar vacío</span><span class="sxs-lookup"><span data-stu-id="c80d0-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="c80d0-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c80d0-135">See also</span></span>

- [<span data-ttu-id="c80d0-136">\<ApplicationPool> Element (Configuración web)</span><span class="sxs-lookup"><span data-stu-id="c80d0-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
