---
title: <appDomainResourceMonitoring> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
ms.openlocfilehash: 9ecf2e382b5d483377df871835793219b3f74760
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170277"
---
# <a name="appdomainresourcemonitoring-element"></a><span data-ttu-id="8921e-102">\<appDomainResourceMonitoring> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="8921e-102">\<appDomainResourceMonitoring> Element</span></span>

<span data-ttu-id="8921e-103">Indica el runtime para recopilar estadísticas de todos los dominios de aplicación en el proceso mientras dura este.</span><span class="sxs-lookup"><span data-stu-id="8921e-103">Instructs the runtime to collect statistics on all application domains in the process for the life of the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainResourceMonitoring>**  
  
## <a name="syntax"></a><span data-ttu-id="8921e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8921e-104">Syntax</span></span>  
  
```xml  
<appDomainResourceMonitoring
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8921e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8921e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8921e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8921e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8921e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8921e-107">Attributes</span></span>  
  
|<span data-ttu-id="8921e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8921e-108">Attribute</span></span>|<span data-ttu-id="8921e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8921e-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8921e-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8921e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="8921e-111">Especifica si el Runtime recopila estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8921e-111">Specifies whether the runtime collects statistics for application domain resource monitoring.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8921e-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="8921e-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="8921e-113">Value</span><span class="sxs-lookup"><span data-stu-id="8921e-113">Value</span></span>|<span data-ttu-id="8921e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8921e-114">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="8921e-115">Se recopilan las estadísticas para la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8921e-115">Statistics for application domain resource monitoring are collected.</span></span>|  
|`false`|<span data-ttu-id="8921e-116">No se recopilan las estadísticas de supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8921e-116">Statistics for application domain resource monitoring are not collected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8921e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8921e-117">Child Elements</span></span>  

 <span data-ttu-id="8921e-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8921e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8921e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8921e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8921e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8921e-120">Element</span></span>|<span data-ttu-id="8921e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8921e-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8921e-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8921e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8921e-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8921e-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8921e-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8921e-124">Remarks</span></span>  

 <span data-ttu-id="8921e-125">La supervisión de recursos del dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, la interfaz [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) de hospedaje y el seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="8921e-125">Application domain resource monitoring is available through the managed application domain class, the hosting [ICLRAppDomainResourceMonitor](../../../unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interface, and event tracing for Windows (ETW).</span></span> <span data-ttu-id="8921e-126">Cuando se habilita la supervisión, se recopilan estadísticas para todos los dominios de aplicación del proceso durante la vida del proceso.</span><span class="sxs-lookup"><span data-stu-id="8921e-126">When monitoring is enabled, statistics are collected for all application domains in the process for the life of the process.</span></span>  
  
 <span data-ttu-id="8921e-127">Para habilitar la supervisión desde código administrado, utilice la <xref:System.AppDomain.MonitoringIsEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8921e-127">To enable monitoring from managed code, use the <xref:System.AppDomain.MonitoringIsEnabled%2A> property.</span></span>  
  
 <span data-ttu-id="8921e-128">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8921e-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8921e-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8921e-129">Example</span></span>  

 <span data-ttu-id="8921e-130">En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8921e-130">The following example shows how to enable application domain resource monitoring.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8921e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8921e-131">See also</span></span>

- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8921e-132">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8921e-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8921e-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8921e-133">Configuration File Schema</span></span>](../index.md)
