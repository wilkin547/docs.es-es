---
title: <UseSmallInternalThreadStacks> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515ea076c5eaead50b41e45e415725d0439914bc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252208"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="83b73-102">\<UseSmallInternalThreadStacks >, elemento</span><span class="sxs-lookup"><span data-stu-id="83b73-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="83b73-103">Solicita que el Common Language Runtime (CLR) reduzca el uso de memoria especificando tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="83b73-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
<span data-ttu-id="83b73-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="83b73-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="83b73-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="83b73-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="83b73-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseSmallInternalThreadStacks>**</span><span class="sxs-lookup"><span data-stu-id="83b73-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b73-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83b73-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83b73-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83b73-108">Attributes and Elements</span></span>  
 <span data-ttu-id="83b73-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83b73-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83b73-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="83b73-110">Attributes</span></span>  
  
|<span data-ttu-id="83b73-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="83b73-111">Attribute</span></span>|<span data-ttu-id="83b73-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83b73-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83b73-113">enabled</span><span class="sxs-lookup"><span data-stu-id="83b73-113">enabled</span></span>|<span data-ttu-id="83b73-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="83b73-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="83b73-115">Especifica si se debe solicitar que CLR use tamaños de pila explícitos en lugar del tamaño de pila predeterminado cuando crea determinados subprocesos que usa internamente.</span><span class="sxs-lookup"><span data-stu-id="83b73-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="83b73-116">Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="83b73-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="83b73-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="83b73-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="83b73-118">Valor</span><span class="sxs-lookup"><span data-stu-id="83b73-118">Value</span></span>|<span data-ttu-id="83b73-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83b73-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="83b73-120">true</span><span class="sxs-lookup"><span data-stu-id="83b73-120">true</span></span>|<span data-ttu-id="83b73-121">Solicitar tamaños de pila explícitos.</span><span class="sxs-lookup"><span data-stu-id="83b73-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="83b73-122">false</span><span class="sxs-lookup"><span data-stu-id="83b73-122">false</span></span>|<span data-ttu-id="83b73-123">Use el tamaño de pila predeterminado.</span><span class="sxs-lookup"><span data-stu-id="83b73-123">Use the default stack size.</span></span> <span data-ttu-id="83b73-124">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="83b73-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83b73-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83b73-125">Child Elements</span></span>  
 <span data-ttu-id="83b73-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83b73-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83b73-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83b73-127">Parent Elements</span></span>  
  
|<span data-ttu-id="83b73-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="83b73-128">Element</span></span>|<span data-ttu-id="83b73-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83b73-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83b73-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83b73-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="83b73-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="83b73-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83b73-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83b73-132">Remarks</span></span>  
 <span data-ttu-id="83b73-133">Este elemento de configuración se usa para solicitar el uso reducido de la memoria virtual en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="83b73-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="83b73-134">Este elemento de configuración es una solicitud a CLR en lugar de un requisito absoluto.</span><span class="sxs-lookup"><span data-stu-id="83b73-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="83b73-135">En el .NET Framework 4, la solicitud solo se admite para la arquitectura x86.</span><span class="sxs-lookup"><span data-stu-id="83b73-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="83b73-136">Este elemento podría omitirse completamente en versiones futuras de CLR o reemplazarse por tamaños de pila explícitos que siempre se usan para los subprocesos internos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="83b73-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="83b73-137">Si se especifica este elemento de configuración, la confiabilidad se usa para reducir el uso de memoria virtual si CLR respeta la solicitud, ya que los tamaños de pila más pequeños podrían provocar desbordamientos de la pila con mayor probabilidad.</span><span class="sxs-lookup"><span data-stu-id="83b73-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83b73-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83b73-138">Example</span></span>  
 <span data-ttu-id="83b73-139">En el ejemplo siguiente se muestra cómo solicitar que CLR use tamaños de pila explícitos para determinados subprocesos que usa internamente.</span><span class="sxs-lookup"><span data-stu-id="83b73-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83b73-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b73-140">See also</span></span>

- [<span data-ttu-id="83b73-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="83b73-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83b73-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="83b73-142">Configuration File Schema</span></span>](../index.md)
