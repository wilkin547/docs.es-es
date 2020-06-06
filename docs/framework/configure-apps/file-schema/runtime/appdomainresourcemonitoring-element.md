---
title: <appDomainResourceMonitoring> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 3c6092b6c34bb13c0ad0e66df2d3b7e65ac3de7e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154381"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="7ee5d-102">\<appDomainResourceMonitoring> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="7ee5d-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="7ee5d-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="7ee5d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ee5d-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ee5d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ee5d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7ee5d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ee5d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ee5d-107">Attributes</span></span>  
  
|<span data-ttu-id="7ee5d-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="7ee5d-108">Attribute</span></span>|<span data-ttu-id="7ee5d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ee5d-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7ee5d-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="7ee5d-111">Especifica si el Runtime recopila estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7ee5d-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="7ee5d-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="7ee5d-113">Value</span><span class="sxs-lookup"><span data-stu-id="7ee5d-113">Value</span></span>|<span data-ttu-id="7ee5d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ee5d-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="7ee5d-115">Se recopilan las estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="7ee5d-116">No se recopilan las estadísticas de supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ee5d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ee5d-117">Child Elements</span></span>  
 <span data-ttu-id="7ee5d-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ee5d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ee5d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="7ee5d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ee5d-120">Element</span></span>|<span data-ttu-id="7ee5d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ee5d-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7ee5d-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7ee5d-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ee5d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ee5d-124">Remarks</span></span>  
 <span data-ttu-id="7ee5d-125">La supervisión de recursos del dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, la interfaz [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) de hospedaje y el seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="7ee5d-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="7ee5d-126">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación del proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="7ee5d-127">Para habilitar la supervisión desde código administrado, utilice la <xref:System.AppDomain.MonitoringIsEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="7ee5d-128">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ee5d-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7ee5d-129">Example</span></span>  
 <span data-ttu-id="7ee5d-130">En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ee5d-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ee5d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ee5d-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7ee5d-132">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="7ee5d-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7ee5d-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7ee5d-133">Configuration File Schema</span></span>](../index.md)
