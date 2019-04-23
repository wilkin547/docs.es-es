---
title: <UseSmallInternalThreadStacks> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9833d768b84faaf6e1dcf8c9cb8b00b92adc3d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144834"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="72de4-102">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="72de4-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="72de4-103">Usan las solicitudes que common language runtime (CLR) Reduzca la memoria mediante la especificación de tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="72de4-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="72de4-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="72de4-104">\<configuration> Element</span></span>  
<span data-ttu-id="72de4-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="72de4-105">\<runtime> Element</span></span>  
<span data-ttu-id="72de4-106">\<UseSmallInternalThreadStacks > elemento</span><span class="sxs-lookup"><span data-stu-id="72de4-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72de4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72de4-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72de4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="72de4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="72de4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="72de4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72de4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="72de4-110">Attributes</span></span>  
  
|<span data-ttu-id="72de4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="72de4-111">Attribute</span></span>|<span data-ttu-id="72de4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="72de4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72de4-113">enabled</span><span class="sxs-lookup"><span data-stu-id="72de4-113">enabled</span></span>|<span data-ttu-id="72de4-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="72de4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="72de4-115">Especifica si se solicita que los tamaños de pila explícitos de uso CLR en lugar del tamaño de pila predeterminado al crear determinados subprocesos que utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="72de4-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="72de4-116">Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="72de4-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="72de4-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="72de4-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="72de4-118">Valor</span><span class="sxs-lookup"><span data-stu-id="72de4-118">Value</span></span>|<span data-ttu-id="72de4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="72de4-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72de4-120">true</span><span class="sxs-lookup"><span data-stu-id="72de4-120">true</span></span>|<span data-ttu-id="72de4-121">Solicitar los tamaños de pila explícito.</span><span class="sxs-lookup"><span data-stu-id="72de4-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="72de4-122">False</span><span class="sxs-lookup"><span data-stu-id="72de4-122">false</span></span>|<span data-ttu-id="72de4-123">Use el tamaño de pila predeterminado.</span><span class="sxs-lookup"><span data-stu-id="72de4-123">Use the default stack size.</span></span> <span data-ttu-id="72de4-124">Este es el valor predeterminado para el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72de4-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72de4-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="72de4-125">Child Elements</span></span>  
 <span data-ttu-id="72de4-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="72de4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72de4-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="72de4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="72de4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="72de4-128">Element</span></span>|<span data-ttu-id="72de4-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="72de4-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="72de4-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72de4-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="72de4-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="72de4-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72de4-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="72de4-132">Remarks</span></span>  
 <span data-ttu-id="72de4-133">Este elemento de configuración se utiliza para solicitar el uso de memoria virtual reducido en un proceso, ya que los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="72de4-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="72de4-134">Este elemento de configuración es una solicitud a CLR en lugar de un requisito imprescindible.</span><span class="sxs-lookup"><span data-stu-id="72de4-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="72de4-135">En el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], la solicitud solo se admite para la x86 arquitectura.</span><span class="sxs-lookup"><span data-stu-id="72de4-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="72de4-136">Este elemento podría omite completamente en futuras versiones de CLR, o reemplazado por los tamaños de pila explícitos que se utilizan siempre para los subprocesos internos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="72de4-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="72de4-137">Especificando que este elemento de configuración transacciones de confiabilidad para su uso de memoria virtual más pequeño si CLR respeta la solicitud, porque los tamaños de pila más pequeños podrían hacer que stack desborda es más probable.</span><span class="sxs-lookup"><span data-stu-id="72de4-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72de4-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72de4-138">Example</span></span>  
 <span data-ttu-id="72de4-139">El ejemplo siguiente muestra cómo solicitar que el CLR use tamaños de pila explícitos para determinados subprocesos que utiliza internamente.</span><span class="sxs-lookup"><span data-stu-id="72de4-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="72de4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="72de4-140">See also</span></span>

- [<span data-ttu-id="72de4-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="72de4-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="72de4-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="72de4-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
