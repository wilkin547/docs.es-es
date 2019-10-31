---
title: <appDomainResourceMonitoring> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 991833500cae4d96e9c28f7e94ca366e9b976a9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118254"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="a86e3-102">\<elemento > appDomainResourceMonitoring</span><span class="sxs-lookup"><span data-stu-id="a86e3-102">\<appDomainResourceMonitoring> Element</span></span>
<span data-ttu-id="a86e3-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="a86e3-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
<span data-ttu-id="a86e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a86e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a86e3-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a86e3-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a86e3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainResourceMonitoring >**</span><span class="sxs-lookup"><span data-stu-id="a86e3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a86e3-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a86e3-107">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a86e3-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a86e3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a86e3-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a86e3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a86e3-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a86e3-110">Attributes</span></span>  
  
|<span data-ttu-id="a86e3-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a86e3-111">Attribute</span></span>|<span data-ttu-id="a86e3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a86e3-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a86e3-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a86e3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a86e3-114">Especifica si el Runtime recopila estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a86e3-114">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a86e3-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a86e3-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a86e3-116">Valor</span><span class="sxs-lookup"><span data-stu-id="a86e3-116">Value</span></span>|<span data-ttu-id="a86e3-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a86e3-117">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="a86e3-118">Se recopilan las estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a86e3-118">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="a86e3-119">No se recopilan las estadísticas de supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a86e3-119">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a86e3-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a86e3-120">Child Elements</span></span>  
 <span data-ttu-id="a86e3-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a86e3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a86e3-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a86e3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a86e3-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="a86e3-123">Element</span></span>|<span data-ttu-id="a86e3-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="a86e3-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a86e3-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a86e3-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a86e3-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a86e3-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a86e3-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a86e3-127">Remarks</span></span>  
 <span data-ttu-id="a86e3-128">La supervisión de recursos del dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, la interfaz [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) de hospedaje y el seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="a86e3-128">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="a86e3-129">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación del proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="a86e3-129">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="a86e3-130">Para habilitar la supervisión desde código administrado, utilice la propiedad <xref:System.AppDomain.MonitoringIsEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="a86e3-130">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="a86e3-131">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a86e3-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a86e3-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a86e3-132">Example</span></span>  
 <span data-ttu-id="a86e3-133">En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a86e3-133">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a86e3-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a86e3-134">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a86e3-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a86e3-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a86e3-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a86e3-136">Configuration File Schema</span></span>](../index.md)
