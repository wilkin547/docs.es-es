---
description: 'Más información acerca de: <UseSmallInternalThreadStacks> elemento'
title: <UseSmallInternalThreadStacks> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: eeb253025b32f862926c7315004b1854b8eef928
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639970"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="34630-103">\<UseSmallInternalThreadStacks> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="34630-103">\<UseSmallInternalThreadStacks> Element</span></span>

<span data-ttu-id="34630-104">Solicita que el Common Language Runtime (CLR) reduzca el uso de memoria especificando tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="34630-104">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**  
  
## <a name="syntax"></a><span data-ttu-id="34630-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34630-105">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34630-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="34630-106">Attributes and Elements</span></span>  

 <span data-ttu-id="34630-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="34630-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34630-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="34630-108">Attributes</span></span>  
  
|<span data-ttu-id="34630-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="34630-109">Attribute</span></span>|<span data-ttu-id="34630-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="34630-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34630-111">enabled</span><span class="sxs-lookup"><span data-stu-id="34630-111">enabled</span></span>|<span data-ttu-id="34630-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="34630-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="34630-113">Especifica si se debe solicitar que CLR use tamaños de pila explícitos en lugar del tamaño de pila predeterminado cuando crea determinados subprocesos que usa internamente.</span><span class="sxs-lookup"><span data-stu-id="34630-113">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="34630-114">Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="34630-114">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="34630-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="34630-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="34630-116">Value</span><span class="sxs-lookup"><span data-stu-id="34630-116">Value</span></span>|<span data-ttu-id="34630-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="34630-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34630-118">true</span><span class="sxs-lookup"><span data-stu-id="34630-118">true</span></span>|<span data-ttu-id="34630-119">Solicitar tamaños de pila explícitos.</span><span class="sxs-lookup"><span data-stu-id="34630-119">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="34630-120">false</span><span class="sxs-lookup"><span data-stu-id="34630-120">false</span></span>|<span data-ttu-id="34630-121">Use el tamaño de pila predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34630-121">Use the default stack size.</span></span> <span data-ttu-id="34630-122">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="34630-122">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34630-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="34630-123">Child Elements</span></span>  

 <span data-ttu-id="34630-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="34630-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34630-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="34630-125">Parent Elements</span></span>  
  
|<span data-ttu-id="34630-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="34630-126">Element</span></span>|<span data-ttu-id="34630-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="34630-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34630-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34630-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34630-129">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="34630-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34630-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34630-130">Remarks</span></span>  

 <span data-ttu-id="34630-131">Este elemento de configuración se usa para solicitar el uso reducido de la memoria virtual en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34630-131">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="34630-132">Este elemento de configuración es una solicitud a CLR en lugar de un requisito absoluto.</span><span class="sxs-lookup"><span data-stu-id="34630-132">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="34630-133">En el .NET Framework 4, la solicitud solo se admite para la arquitectura x86.</span><span class="sxs-lookup"><span data-stu-id="34630-133">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="34630-134">Este elemento podría omitirse completamente en versiones futuras de CLR o reemplazarse por tamaños de pila explícitos que siempre se usan para los subprocesos internos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="34630-134">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="34630-135">Si se especifica este elemento de configuración, la confiabilidad se usa para reducir el uso de memoria virtual si CLR respeta la solicitud, ya que los tamaños de pila más pequeños podrían provocar desbordamientos de la pila con mayor probabilidad.</span><span class="sxs-lookup"><span data-stu-id="34630-135">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34630-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34630-136">Example</span></span>  

 <span data-ttu-id="34630-137">En el ejemplo siguiente se muestra cómo solicitar que CLR use tamaños de pila explícitos para determinados subprocesos que usa internamente.</span><span class="sxs-lookup"><span data-stu-id="34630-137">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34630-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="34630-138">See also</span></span>

- [<span data-ttu-id="34630-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="34630-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34630-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="34630-140">Configuration File Schema</span></span>](../index.md)
