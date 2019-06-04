---
title: <appDomainResourceMonitoring> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad0ae023215eeb1f42f9351369ee77d41d537b88
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487730"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="b15c0-102">\<appDomainResourceMonitoring > elemento</span><span class="sxs-lookup"><span data-stu-id="b15c0-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="b15c0-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="b15c0-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="b15c0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b15c0-104">\<configuration></span></span>  
<span data-ttu-id="b15c0-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b15c0-105">\<runtime></span></span>  
<span data-ttu-id="b15c0-106">\<appDomainResourceMonitoring></span><span class="sxs-lookup"><span data-stu-id="b15c0-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15c0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b15c0-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b15c0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b15c0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b15c0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b15c0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b15c0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b15c0-110">Attributes</span></span>  
  
|<span data-ttu-id="b15c0-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="b15c0-111">Attribute</span></span>|<span data-ttu-id="b15c0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b15c0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b15c0-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b15c0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b15c0-114">Especifica si el tiempo de ejecución recopila estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b15c0-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b15c0-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="b15c0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b15c0-116">Valor</span><span class="sxs-lookup"><span data-stu-id="b15c0-116">Value</span></span>|<span data-ttu-id="b15c0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b15c0-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b15c0-118">Se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b15c0-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="b15c0-119">No se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b15c0-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b15c0-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b15c0-120">Child Elements</span></span>  
 <span data-ttu-id="b15c0-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b15c0-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b15c0-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b15c0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b15c0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b15c0-123">Element</span></span>|<span data-ttu-id="b15c0-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b15c0-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b15c0-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b15c0-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b15c0-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b15c0-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b15c0-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b15c0-127">Remarks</span></span>  
 <span data-ttu-id="b15c0-128">Supervisión de recursos de dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, el hospedaje [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaz y seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b15c0-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="b15c0-129">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación en el proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="b15c0-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="b15c0-130">Para habilitar la supervisión desde código administrado, utilice el <xref:System.AppDomain.MonitoringIsEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b15c0-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="b15c0-131">Este elemento de configuración está disponible solo en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b15c0-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b15c0-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b15c0-132">Example</span></span>  
 <span data-ttu-id="b15c0-133">El ejemplo siguiente muestra cómo se habilita la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b15c0-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b15c0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b15c0-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b15c0-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b15c0-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b15c0-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b15c0-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
