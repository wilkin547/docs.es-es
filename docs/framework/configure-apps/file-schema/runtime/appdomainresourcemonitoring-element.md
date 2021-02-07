---
description: 'Más información acerca de: <appDomainResourceMonitoring> elemento'
title: <appDomainResourceMonitoring> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: aee85386e6d0af2ca4fd30c0ad8fe69bae240315
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719297"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="de21d-103">\<appDomainResourceMonitoring> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="de21d-103">\<appDomainResourceMonitoring> Element</span></span>

<span data-ttu-id="de21d-104">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="de21d-104">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="de21d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de21d-105">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de21d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="de21d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="de21d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="de21d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de21d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="de21d-108">Attributes</span></span>  
  
|<span data-ttu-id="de21d-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="de21d-109">Attribute</span></span>|<span data-ttu-id="de21d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="de21d-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="de21d-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="de21d-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="de21d-112">Especifica si el Runtime recopila estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="de21d-112">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="de21d-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="de21d-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="de21d-114">Value</span><span class="sxs-lookup"><span data-stu-id="de21d-114">Value</span></span>|<span data-ttu-id="de21d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="de21d-115">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="de21d-116">Se recopilan las estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="de21d-116">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="de21d-117">No se recopilan las estadísticas de supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="de21d-117">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de21d-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="de21d-118">Child Elements</span></span>  

 <span data-ttu-id="de21d-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="de21d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de21d-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de21d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="de21d-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="de21d-121">Element</span></span>|<span data-ttu-id="de21d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="de21d-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="de21d-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="de21d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="de21d-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="de21d-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de21d-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="de21d-125">Remarks</span></span>  

 <span data-ttu-id="de21d-126">La supervisión de recursos del dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, la interfaz [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) de hospedaje y el seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="de21d-126">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="de21d-127">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación del proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="de21d-127">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="de21d-128">Para habilitar la supervisión desde código administrado, utilice la <xref:System.AppDomain.MonitoringIsEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="de21d-128">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="de21d-129">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="de21d-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de21d-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de21d-130">Example</span></span>  

 <span data-ttu-id="de21d-131">En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="de21d-131">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de21d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="de21d-132">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="de21d-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="de21d-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="de21d-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="de21d-134">Configuration File Schema</span></span>](../index.md)
