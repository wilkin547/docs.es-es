---
title: <UseSmallInternalThreadStacks> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 2fd776ce8605e6dcf288dcb3852ded16638a1873
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73114919"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="3a201-102">\<UseSmallInternalThreadStacks> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="3a201-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="3a201-103">Solicita que el Common Language Runtime (CLR) reduzca el uso de memoria especificando tamaños de pila explícitos al crear determinados subprocesos que utiliza internamente, en lugar de usar el tamaño de pila predeterminado para esos subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3a201-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**  
  
## <a name="syntax"></a><span data-ttu-id="3a201-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a201-104">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a201-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a201-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3a201-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a201-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a201-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a201-107">Attributes</span></span>  
  
|<span data-ttu-id="3a201-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="3a201-108">Attribute</span></span>|<span data-ttu-id="3a201-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a201-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a201-110">enabled</span><span class="sxs-lookup"><span data-stu-id="3a201-110">enabled</span></span>|<span data-ttu-id="3a201-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3a201-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="3a201-112">Especifica si se debe solicitar que CLR use tamaños de pila explícitos en lugar del tamaño de pila predeterminado cuando crea determinados subprocesos que usa internamente.</span><span class="sxs-lookup"><span data-stu-id="3a201-112">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="3a201-113">Los tamaños de pila explícitos son menores que el tamaño de pila predeterminado de 1 MB.</span><span class="sxs-lookup"><span data-stu-id="3a201-113">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3a201-114">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="3a201-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="3a201-115">Value</span><span class="sxs-lookup"><span data-stu-id="3a201-115">Value</span></span>|<span data-ttu-id="3a201-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a201-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3a201-117">true</span><span class="sxs-lookup"><span data-stu-id="3a201-117">true</span></span>|<span data-ttu-id="3a201-118">Solicitar tamaños de pila explícitos.</span><span class="sxs-lookup"><span data-stu-id="3a201-118">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="3a201-119">false</span><span class="sxs-lookup"><span data-stu-id="3a201-119">false</span></span>|<span data-ttu-id="3a201-120">Use el tamaño de pila predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3a201-120">Use the default stack size.</span></span> <span data-ttu-id="3a201-121">Este es el valor predeterminado para el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3a201-121">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a201-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a201-122">Child Elements</span></span>  
 <span data-ttu-id="3a201-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a201-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a201-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a201-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3a201-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a201-125">Element</span></span>|<span data-ttu-id="3a201-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a201-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3a201-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3a201-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3a201-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3a201-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a201-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a201-129">Remarks</span></span>  
 <span data-ttu-id="3a201-130">Este elemento de configuración se usa para solicitar el uso reducido de la memoria virtual en un proceso, porque los tamaños de subproceso explícitos que usa CLR para sus subprocesos internos, si se respeta la solicitud, son menores que el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3a201-130">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3a201-131">Este elemento de configuración es una solicitud a CLR en lugar de un requisito absoluto.</span><span class="sxs-lookup"><span data-stu-id="3a201-131">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="3a201-132">En el .NET Framework 4, la solicitud solo se admite para la arquitectura x86.</span><span class="sxs-lookup"><span data-stu-id="3a201-132">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="3a201-133">Este elemento podría omitirse completamente en versiones futuras de CLR o reemplazarse por tamaños de pila explícitos que siempre se usan para los subprocesos internos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="3a201-133">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="3a201-134">Si se especifica este elemento de configuración, la confiabilidad se usa para reducir el uso de memoria virtual si CLR respeta la solicitud, ya que los tamaños de pila más pequeños podrían provocar desbordamientos de la pila con mayor probabilidad.</span><span class="sxs-lookup"><span data-stu-id="3a201-134">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a201-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a201-135">Example</span></span>  
 <span data-ttu-id="3a201-136">En el ejemplo siguiente se muestra cómo solicitar que CLR use tamaños de pila explícitos para determinados subprocesos que usa internamente.</span><span class="sxs-lookup"><span data-stu-id="3a201-136">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a201-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a201-137">See also</span></span>

- [<span data-ttu-id="3a201-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3a201-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3a201-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3a201-139">Configuration File Schema</span></span>](../index.md)
