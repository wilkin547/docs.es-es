---
title: <gcServer> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd91cf0179ef9731c456b41fdc865e3eacdb33eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132813"
---
# <a name="gcserver-element"></a><span data-ttu-id="1c073-102">\<gcServer > elemento</span><span class="sxs-lookup"><span data-stu-id="1c073-102">\<gcServer> Element</span></span>
<span data-ttu-id="1c073-103">Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c073-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
 <span data-ttu-id="1c073-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1c073-104">\<configuration></span></span>  
<span data-ttu-id="1c073-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1c073-105">\<runtime></span></span>  
<span data-ttu-id="1c073-106">\<gcServer></span><span class="sxs-lookup"><span data-stu-id="1c073-106">\<gcServer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c073-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c073-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c073-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1c073-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1c073-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1c073-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c073-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c073-110">Attributes</span></span>  
  
|<span data-ttu-id="1c073-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1c073-111">Attribute</span></span>|<span data-ttu-id="1c073-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c073-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1c073-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1c073-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1c073-114">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c073-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1c073-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="1c073-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1c073-116">Valor</span><span class="sxs-lookup"><span data-stu-id="1c073-116">Value</span></span>|<span data-ttu-id="1c073-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c073-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1c073-118">No ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c073-118">Does not run server garbage collection.</span></span> <span data-ttu-id="1c073-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1c073-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1c073-120">Ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c073-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c073-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1c073-121">Child Elements</span></span>  
 <span data-ttu-id="1c073-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1c073-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c073-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c073-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1c073-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c073-124">Element</span></span>|<span data-ttu-id="1c073-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c073-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1c073-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c073-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1c073-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1c073-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c073-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c073-128">Remarks</span></span>  
 <span data-ttu-id="1c073-129">Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador.</span><span class="sxs-lookup"><span data-stu-id="1c073-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="1c073-130">El elemento `<gcServer>` se usa para controlar el tipo de recolección de elementos no utilizados que CLR realiza.</span><span class="sxs-lookup"><span data-stu-id="1c073-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="1c073-131">Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="1c073-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="1c073-132">Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida.</span><span class="sxs-lookup"><span data-stu-id="1c073-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="1c073-133">En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c073-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="1c073-134">La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores.</span><span class="sxs-lookup"><span data-stu-id="1c073-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="1c073-135">Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="1c073-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c073-136">En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="1c073-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="1c073-137">A partir de [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], la recolección de elementos no utilizados de servidor es simultánea.</span><span class="sxs-lookup"><span data-stu-id="1c073-137">Starting with the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], server garbage collection is concurrent.</span></span> <span data-ttu-id="1c073-138">Para usar la recolección no simultánea server, establezca el `<gcServer>` elemento `true` y [ \<gcConcurrent > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) a `false`.</span><span class="sxs-lookup"><span data-stu-id="1c073-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c073-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c073-139">Example</span></span>  
 <span data-ttu-id="1c073-140">En el ejemplo siguiente se habilita la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="1c073-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c073-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c073-141">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1c073-142">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1c073-142">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1c073-143">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1c073-143">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="1c073-144">Para deshabilitar la recopilación de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="1c073-144">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
