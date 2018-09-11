---
title: '&lt;Inicio&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4d39dc28082fbed932a60228ac216f2f700c2e9f
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44366064"
---
# <a name="ltstartupgt-element"></a><span data-ttu-id="5cf73-102">&lt;Inicio&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="5cf73-102">&lt;startup&gt; Element</span></span>
<span data-ttu-id="5cf73-103">Especifica la información de inicio de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="5cf73-103">Specifies common language runtime startup information.</span></span>  
  
 <span data-ttu-id="5cf73-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5cf73-104">\<configuration></span></span>  
<span data-ttu-id="5cf73-105">\<Inicio ></span><span class="sxs-lookup"><span data-stu-id="5cf73-105">\<startup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cf73-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cf73-106">Syntax</span></span>  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cf73-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5cf73-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5cf73-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5cf73-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cf73-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="5cf73-109">Attributes</span></span>  
  
|<span data-ttu-id="5cf73-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="5cf73-110">Attribute</span></span>|<span data-ttu-id="5cf73-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cf73-111">Description</span></span>|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="5cf73-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="5cf73-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5cf73-113">Especifica si se habilita la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] directiva de activación en tiempo de ejecución o que se usará el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] directiva de activación.</span><span class="sxs-lookup"><span data-stu-id="5cf73-113">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="5cf73-114">Atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cf73-114">useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
  
|<span data-ttu-id="5cf73-115">Valor</span><span class="sxs-lookup"><span data-stu-id="5cf73-115">Value</span></span>|<span data-ttu-id="5cf73-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cf73-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="5cf73-117">Habilitar [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] en tiempo de ejecución directiva de activación para el tiempo de ejecución elegido, que se usa para enlazar las técnicas de activación de tiempo de ejecución heredado (como el [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegida en el archivo de configuración en lugar de límites de ellos en CLR versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="5cf73-117">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="5cf73-118">Por lo tanto, si se elige la versión CLR 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores de .NET Framework se cargan con la versión CLR elegida.</span><span class="sxs-lookup"><span data-stu-id="5cf73-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="5cf73-119">Al establecer este valor impide que CLR versión 1.1 o CLR versión 2.0 no se cargue en el mismo proceso, deshabilitando la característica en paralelo en proceso.</span><span class="sxs-lookup"><span data-stu-id="5cf73-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|  
|`false`|<span data-ttu-id="5cf73-120">Usar la directiva de activación predeterminada para el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores, que es permitir el tiempo de ejecución heredado técnicas de activación para cargar la versión 1.1 o 2.0 de CLR en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5cf73-120">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="5cf73-121">Al establecer este valor impide que los ensamblados de modo mixto de carga en .NET Framework 4 o posterior, a menos que se compilaron con .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="5cf73-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="5cf73-122">Este valor es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5cf73-122">This value is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cf73-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5cf73-123">Child Elements</span></span>  
  
|<span data-ttu-id="5cf73-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cf73-124">Element</span></span>|<span data-ttu-id="5cf73-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cf73-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cf73-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="5cf73-126">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="5cf73-127">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5cf73-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="5cf73-128">Las aplicaciones compiladas con la versión 1.1 o posterior del runtime deben usar el  **\<supportedRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="5cf73-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="5cf73-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="5cf73-129">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="5cf73-130">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5cf73-130">Specifies which versions of the common language runtime the application supports.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cf73-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5cf73-131">Parent Elements</span></span>  
  
|<span data-ttu-id="5cf73-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cf73-132">Element</span></span>|<span data-ttu-id="5cf73-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cf73-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5cf73-134">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cf73-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cf73-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5cf73-135">Remarks</span></span>  
 <span data-ttu-id="5cf73-136">El  **\<supportedRuntime >** se debe utilizar el elemento todas las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5cf73-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="5cf73-137">Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la  **\<requiredRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="5cf73-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>  
  
 <span data-ttu-id="5cf73-138">El código de inicio de una aplicación hospedada en Microsoft Internet Explorer omite el  **\<Inicio >** elemento y sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="5cf73-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="5cf73-139">El atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="5cf73-139">The useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
 <span data-ttu-id="5cf73-140">Este atributo es útil si la aplicación usa rutas de acceso de activación heredada, como la [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso para activar la versión 4 de CLR en lugar de una versión anterior, o si la aplicación con el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] , pero tiene una dependencia en un ensamblado de modo mixto generado con una versión anterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5cf73-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="5cf73-141">En esos escenarios, establezca el atributo en `true`.</span><span class="sxs-lookup"><span data-stu-id="5cf73-141">In those scenarios, set the attribute to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cf73-142">Establecer el atributo como `true` que CLR versión 1.1 o CLR versión 2.0 no se cargue en el mismo proceso, deshabilitando la característica en paralelo en proceso (consulte [ejecución en paralelo para interoperabilidad COM](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span><span class="sxs-lookup"><span data-stu-id="5cf73-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5cf73-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5cf73-143">Example</span></span>  
 <span data-ttu-id="5cf73-144">El ejemplo siguiente muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5cf73-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5cf73-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cf73-145">See Also</span></span>  
 [<span data-ttu-id="5cf73-146">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="5cf73-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="5cf73-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5cf73-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="5cf73-148">\<PaveOver> Especificar la versión en tiempo de ejecución que se va a usar</span><span class="sxs-lookup"><span data-stu-id="5cf73-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [<span data-ttu-id="5cf73-149">Ejecución en paralelo para interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="5cf73-149">Side-by-Side Execution for COM Interop</span></span>](https://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [<span data-ttu-id="5cf73-150">Ejecución en paralelo en proceso</span><span class="sxs-lookup"><span data-stu-id="5cf73-150">In-Process Side-by-Side Execution</span></span>](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
