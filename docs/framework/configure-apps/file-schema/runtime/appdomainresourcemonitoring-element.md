---
title: '&lt;appDomainResourceMonitoring&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58caa7458d96ca7bb9088b607a83b2d6be667cae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainresourcemonitoringgt-element"></a><span data-ttu-id="45588-102">&lt;appDomainResourceMonitoring&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="45588-102">&lt;appDomainResourceMonitoring&gt; Element</span></span>
<span data-ttu-id="45588-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="45588-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="45588-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="45588-104">\<configuration></span></span>  
<span data-ttu-id="45588-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="45588-105">\<runtime></span></span>  
<span data-ttu-id="45588-106">\<appDomainResourceMonitoring ></span><span class="sxs-lookup"><span data-stu-id="45588-106">\<appDomainResourceMonitoring></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45588-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45588-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45588-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="45588-108">Attributes and Elements</span></span>  
 <span data-ttu-id="45588-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="45588-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45588-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="45588-110">Attributes</span></span>  
  
|<span data-ttu-id="45588-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="45588-111">Attribute</span></span>|<span data-ttu-id="45588-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="45588-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="45588-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="45588-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="45588-114">Especifica si el tiempo de ejecución recopila estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="45588-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="45588-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="45588-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="45588-116">Valor</span><span class="sxs-lookup"><span data-stu-id="45588-116">Value</span></span>|<span data-ttu-id="45588-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="45588-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="45588-118">Se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="45588-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="45588-119">No se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="45588-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45588-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="45588-120">Child Elements</span></span>  
 <span data-ttu-id="45588-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="45588-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45588-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="45588-122">Parent Elements</span></span>  
  
|<span data-ttu-id="45588-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="45588-123">Element</span></span>|<span data-ttu-id="45588-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="45588-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="45588-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="45588-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="45588-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="45588-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45588-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45588-127">Remarks</span></span>  
 <span data-ttu-id="45588-128">Supervisión de recursos de dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, el hospedaje [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfaz y seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="45588-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="45588-129">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación en el proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="45588-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="45588-130">Para habilitar la supervisión desde código administrado, utilice la <xref:System.AppDomain.MonitoringIsEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="45588-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="45588-131">Este elemento de configuración solo está disponible en la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="45588-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45588-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45588-132">Example</span></span>  
 <span data-ttu-id="45588-133">En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="45588-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="45588-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="45588-134">See Also</span></span>  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="45588-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="45588-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="45588-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="45588-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
