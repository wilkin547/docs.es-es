---
title: '&lt;UseSmallInternalThreadStacks&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c96537cad59034578d1284f7dc432e5775f3730b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a><span data-ttu-id="aa72a-102">&lt;UseSmallInternalThreadStacks&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="aa72a-102">&lt;UseSmallInternalThreadStacks&gt; Element</span></span>
<span data-ttu-id="aa72a-103">Usan las solicitudes que common language runtime (CLR) reduce la memoria mediante la especificación de tamaños de pila explícitos cuando crea ciertos subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="aa72a-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="aa72a-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="aa72a-104">\<configuration> Element</span></span>  
<span data-ttu-id="aa72a-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="aa72a-105">\<runtime> Element</span></span>  
<span data-ttu-id="aa72a-106">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="aa72a-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa72a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa72a-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa72a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aa72a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aa72a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aa72a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa72a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa72a-110">Attributes</span></span>  
  
|<span data-ttu-id="aa72a-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="aa72a-111">Attribute</span></span>|<span data-ttu-id="aa72a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa72a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa72a-113">enabled</span><span class="sxs-lookup"><span data-stu-id="aa72a-113">enabled</span></span>|<span data-ttu-id="aa72a-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="aa72a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="aa72a-115">Especifica si se solicita que los tamaños de pila explícito de uso CLR en lugar del tamaño de pila predeterminado cuando crea ciertos subprocesos que utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="aa72a-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="aa72a-116">Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="aa72a-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="aa72a-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="aa72a-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="aa72a-118">Valor</span><span class="sxs-lookup"><span data-stu-id="aa72a-118">Value</span></span>|<span data-ttu-id="aa72a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa72a-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="aa72a-120">true</span><span class="sxs-lookup"><span data-stu-id="aa72a-120">true</span></span>|<span data-ttu-id="aa72a-121">Tamaños de pila explícito de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="aa72a-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="aa72a-122">False</span><span class="sxs-lookup"><span data-stu-id="aa72a-122">false</span></span>|<span data-ttu-id="aa72a-123">Usar el tamaño de pila predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aa72a-123">Use the default stack size.</span></span> <span data-ttu-id="aa72a-124">Este es el valor predeterminado para el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa72a-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa72a-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa72a-125">Child Elements</span></span>  
 <span data-ttu-id="aa72a-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aa72a-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa72a-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aa72a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="aa72a-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa72a-128">Element</span></span>|<span data-ttu-id="aa72a-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa72a-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="aa72a-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa72a-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="aa72a-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="aa72a-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa72a-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa72a-132">Remarks</span></span>  
 <span data-ttu-id="aa72a-133">Este elemento de configuración se usa para solicitar el uso de memoria virtual reducida en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aa72a-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa72a-134">Este elemento de configuración es una solicitud a CLR en lugar de un requisito imprescindible.</span><span class="sxs-lookup"><span data-stu-id="aa72a-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="aa72a-135">En el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la solicitud solo se admite para la x86 arquitectura.</span><span class="sxs-lookup"><span data-stu-id="aa72a-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="aa72a-136">Este elemento podría omite por completo en versiones futuras de CLR, o se reemplaza por tamaños de pila explícitos que se usan siempre para los subprocesos internos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="aa72a-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="aa72a-137">Especificar que este elemento de configuración reduce la confiabilidad pero menor uso de memoria virtual si el CLR admite la solicitud, porque el tamaño de pila menor podría provocar pila desborda más frecuente.</span><span class="sxs-lookup"><span data-stu-id="aa72a-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa72a-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa72a-138">Example</span></span>  
 <span data-ttu-id="aa72a-139">En el ejemplo siguiente se muestra cómo solicitar que el CLR use tamaños de pila explícitos para ciertos subprocesos que utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="aa72a-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa72a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa72a-140">See Also</span></span>  
 [<span data-ttu-id="aa72a-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="aa72a-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="aa72a-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="aa72a-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
