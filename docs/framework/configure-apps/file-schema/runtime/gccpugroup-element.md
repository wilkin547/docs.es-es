---
title: '&lt;GCCpuGroup&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21ab18cded2b9a16fe2520547287198d3cfe6b74
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416779"
---
# <a name="ltgccpugroupgt-element"></a><span data-ttu-id="69ca9-102">&lt;GCCpuGroup&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="69ca9-102">&lt;GCCpuGroup&gt; Element</span></span>
<span data-ttu-id="69ca9-103">Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="69ca9-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>  
  
 <span data-ttu-id="69ca9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="69ca9-104">\<configuration></span></span>  
<span data-ttu-id="69ca9-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="69ca9-105">\<runtime></span></span>  
<span data-ttu-id="69ca9-106">\<GCCpuGroup ></span><span class="sxs-lookup"><span data-stu-id="69ca9-106">\<GCCpuGroup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69ca9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69ca9-107">Syntax</span></span>  
  
```xml  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69ca9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69ca9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69ca9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69ca9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69ca9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="69ca9-110">Attributes</span></span>  
  
|<span data-ttu-id="69ca9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="69ca9-111">Attribute</span></span>|<span data-ttu-id="69ca9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="69ca9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="69ca9-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="69ca9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="69ca9-114">Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="69ca9-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="69ca9-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="69ca9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="69ca9-116">Valor</span><span class="sxs-lookup"><span data-stu-id="69ca9-116">Value</span></span>|<span data-ttu-id="69ca9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="69ca9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="69ca9-118">La recolección de elementos no utilizados no admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="69ca9-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="69ca9-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="69ca9-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="69ca9-120">La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="69ca9-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69ca9-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69ca9-121">Child Elements</span></span>  
 <span data-ttu-id="69ca9-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="69ca9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69ca9-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69ca9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="69ca9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="69ca9-124">Element</span></span>|<span data-ttu-id="69ca9-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="69ca9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="69ca9-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69ca9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="69ca9-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="69ca9-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69ca9-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69ca9-128">Remarks</span></span>  
 <span data-ttu-id="69ca9-129">Cuando un equipo tiene varios grupos de CPU y está habilitada la recolección de elementos no utilizados de servidor (consulte la [ \<gcServer >](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) elemento), habilitar este elemento extiende la recolección en todos los grupos de CPU y toma todos los núcleos en cuenta al crear y equilibra montones.</span><span class="sxs-lookup"><span data-stu-id="69ca9-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69ca9-130">Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="69ca9-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="69ca9-131">Para habilitar el runtime pueda distribuir subprocesos de usuario en todos los grupos de CPU, también debe habilitar la [< Thread_UseAllCpuGroups >](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="69ca9-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [<Thread_UseAllCpuGroups>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69ca9-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69ca9-132">Example</span></span>  
 <span data-ttu-id="69ca9-133">En el ejemplo siguiente se muestra cómo habilitar la recolección de elementos no utilizados para varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="69ca9-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="69ca9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="69ca9-134">See Also</span></span>  
 [<span data-ttu-id="69ca9-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="69ca9-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="69ca9-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="69ca9-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="69ca9-137">Cómo: deshabilitar la recolección de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="69ca9-137">How to: Disable Concurrent Garbage Collection</span></span>](https://msdn.microsoft.com/library/ba2c6c67-5778-497c-9fac-5f793b5500c7)  
 [<span data-ttu-id="69ca9-138">Recolección de estación de trabajo y servidor</span><span class="sxs-lookup"><span data-stu-id="69ca9-138">Workstation and server garbage collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
