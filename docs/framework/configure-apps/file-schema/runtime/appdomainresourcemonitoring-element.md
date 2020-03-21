---
title: <appDomainResourceMonitoring> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154381"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="8844b-102">\<appDomainResourceMonitoring> Element</span><span class="sxs-lookup"><span data-stu-id="8844b-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="8844b-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="8844b-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="8844b-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8844b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8844b-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="8844b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="8844b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span><span class="sxs-lookup"><span data-stu-id="8844b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8844b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8844b-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8844b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8844b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8844b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8844b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8844b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8844b-110">Attributes</span></span>  
  
|<span data-ttu-id="8844b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="8844b-111">Attribute</span></span>|<span data-ttu-id="8844b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8844b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8844b-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8844b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8844b-114">Especifica si el tiempo de ejecución recopila estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8844b-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8844b-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="8844b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8844b-116">Value</span><span class="sxs-lookup"><span data-stu-id="8844b-116">Value</span></span>|<span data-ttu-id="8844b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8844b-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="8844b-118">Se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8844b-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="8844b-119">No se recopilan estadísticas para la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8844b-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8844b-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8844b-120">Child Elements</span></span>  
 <span data-ttu-id="8844b-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8844b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8844b-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8844b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8844b-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8844b-123">Element</span></span>|<span data-ttu-id="8844b-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="8844b-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8844b-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8844b-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8844b-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8844b-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8844b-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8844b-127">Remarks</span></span>  
 <span data-ttu-id="8844b-128">La supervisión de recursos de dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, la interfaz [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) de hospedaje y el seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="8844b-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="8844b-129">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación en el proceso durante la vida útil del proceso.</span><span class="sxs-lookup"><span data-stu-id="8844b-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="8844b-130">Para habilitar la supervisión desde <xref:System.AppDomain.MonitoringIsEnabled%2A> código administrado, use la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8844b-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="8844b-131">Este elemento de configuración solo está disponible en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8844b-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8844b-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8844b-132">Example</span></span>  
 <span data-ttu-id="8844b-133">En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8844b-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8844b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8844b-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8844b-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8844b-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8844b-136">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8844b-136">Configuration File Schema</span></span>](../index.md)
