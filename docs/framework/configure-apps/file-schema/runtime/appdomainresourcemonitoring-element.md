---
title: '&lt;appDomainResourceMonitoring&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32ffe48e7a65ab4ca2250eee65d188c0c7270c11
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611339"
---
# <a name="ltappdomainresourcemonitoringgt-element"></a><span data-ttu-id="c437f-102">&lt;appDomainResourceMonitoring&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="c437f-102">&lt;appDomainResourceMonitoring&gt; Element</span></span>
<span data-ttu-id="c437f-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="c437f-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="c437f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c437f-104">\<configuration></span></span>  
<span data-ttu-id="c437f-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="c437f-105">\<runtime></span></span>  
<span data-ttu-id="c437f-106">\<appDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="c437f-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c437f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c437f-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c437f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c437f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c437f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c437f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c437f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c437f-110">Attributes</span></span>  
  
|<span data-ttu-id="c437f-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="c437f-111">Attribute</span></span>|<span data-ttu-id="c437f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c437f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c437f-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c437f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c437f-114">Especifica si el tiempo de ejecución recopila estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c437f-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c437f-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="c437f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c437f-116">Valor</span><span class="sxs-lookup"><span data-stu-id="c437f-116">Value</span></span>|<span data-ttu-id="c437f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c437f-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="c437f-118">Se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c437f-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="c437f-119">No se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c437f-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c437f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c437f-120">Child Elements</span></span>  
 <span data-ttu-id="c437f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c437f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c437f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c437f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c437f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c437f-123">Element</span></span>|<span data-ttu-id="c437f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="c437f-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c437f-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c437f-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c437f-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c437f-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c437f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c437f-127">Remarks</span></span>  
 <span data-ttu-id="c437f-128">Supervisión de recursos de dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, el hospedaje [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaz y seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="c437f-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="c437f-129">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación en el proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="c437f-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="c437f-130">Para habilitar la supervisión desde código administrado, utilice el <xref:System.AppDomain.MonitoringIsEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c437f-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="c437f-131">Este elemento de configuración solo está disponible en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c437f-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c437f-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c437f-132">Example</span></span>  
 <span data-ttu-id="c437f-133">El ejemplo siguiente muestra cómo se habilita la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c437f-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c437f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c437f-134">See Also</span></span>  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="c437f-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c437f-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="c437f-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c437f-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
