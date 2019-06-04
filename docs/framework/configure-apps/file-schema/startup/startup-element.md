---
title: Elemento <startup>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: 5b15c504a01a0ab8e17b8ad8811d9ed183609322
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456262"
---
# <a name="startup-element"></a><span data-ttu-id="7f513-102">\<Inicio > elemento</span><span class="sxs-lookup"><span data-stu-id="7f513-102">\<startup> element</span></span>

<span data-ttu-id="7f513-103">Especifica la información de inicio de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="7f513-103">Specifies common language runtime startup information.</span></span>

 <span data-ttu-id="7f513-104">\<Configuración > \<Inicio ></span><span class="sxs-lookup"><span data-stu-id="7f513-104">\<configuration> \<startup></span></span>

## <a name="syntax"></a><span data-ttu-id="7f513-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f513-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7f513-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f513-106">Attributes and elements</span></span>

 <span data-ttu-id="7f513-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7f513-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7f513-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f513-108">Attributes</span></span>

|<span data-ttu-id="7f513-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="7f513-109">Attribute</span></span>|<span data-ttu-id="7f513-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f513-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="7f513-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="7f513-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7f513-112">Especifica si se habilita la [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] directiva de activación en tiempo de ejecución o que se usará el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] directiva de activación.</span><span class="sxs-lookup"><span data-stu-id="7f513-112">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="7f513-113">atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f513-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="7f513-114">Valor</span><span class="sxs-lookup"><span data-stu-id="7f513-114">Value</span></span>|<span data-ttu-id="7f513-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f513-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="7f513-116">Habilitar [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] en tiempo de ejecución directiva de activación para el tiempo de ejecución elegido, que se usa para enlazar las técnicas de activación de tiempo de ejecución heredado (como el [CorBindToRuntimeEx (función)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegida en el archivo de configuración en lugar de límites de ellos en CLR versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="7f513-116">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="7f513-117">Por lo tanto, si se elige la versión CLR 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores de .NET Framework se cargan con la versión CLR elegida.</span><span class="sxs-lookup"><span data-stu-id="7f513-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="7f513-118">Al establecer este valor impide que CLR versión 1.1 o CLR versión 2.0 no se cargue en el mismo proceso, deshabilitando la característica en paralelo en proceso.</span><span class="sxs-lookup"><span data-stu-id="7f513-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="7f513-119">Usar la directiva de activación predeterminada de .NET Framework 4 y versiones posteriores, que consiste en permitir en tiempo de ejecución heredado técnicas de activación para cargar la versión 1.1 o 2.0 de CLR en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7f513-119">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="7f513-120">Al establecer este valor impide que los ensamblados de modo mixto de carga en .NET Framework 4 o posterior, a menos que se compilaron con .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="7f513-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="7f513-121">Este valor es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f513-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7f513-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f513-122">Child elements</span></span>

|<span data-ttu-id="7f513-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f513-123">Element</span></span>|<span data-ttu-id="7f513-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f513-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="7f513-125">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="7f513-125">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="7f513-126">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="7f513-126">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="7f513-127">Las aplicaciones compiladas con la versión 1.1 o posterior del runtime deben usar el  **\<supportedRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="7f513-127">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="7f513-128">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="7f513-128">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="7f513-129">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f513-129">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="7f513-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f513-130">Parent elements</span></span>

|<span data-ttu-id="7f513-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f513-131">Element</span></span>|<span data-ttu-id="7f513-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f513-132">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7f513-133">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f513-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7f513-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f513-134">Remarks</span></span>

 <span data-ttu-id="7f513-135">El  **\<supportedRuntime >** se debe utilizar el elemento todas las aplicaciones compiladas con la versión 1.1 o posterior del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f513-135">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="7f513-136">Las aplicaciones compiladas para admitir sólo la versión 1.0 del tiempo de ejecución deben usar la  **\<requiredRuntime >** elemento.</span><span class="sxs-lookup"><span data-stu-id="7f513-136">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="7f513-137">El código de inicio de una aplicación hospedada en Microsoft Internet Explorer omite el  **\<Inicio >** elemento y sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7f513-137">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="7f513-138">El atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="7f513-138">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="7f513-139">Este atributo es útil si la aplicación usa rutas de acceso de activación heredada, como la [CorBindToRuntimeEx (función)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso para activar la versión 4 de CLR en lugar de una versión anterior, o si la aplicación compilada con .NET Framework 4, pero tiene una dependencia en un ensamblado de modo mixto generado con una versión anterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f513-139">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="7f513-140">En esos escenarios, establezca el atributo en `true`.</span><span class="sxs-lookup"><span data-stu-id="7f513-140">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="7f513-141">Establecer el atributo como `true` que CLR versión 1.1 o CLR versión 2.0 no se cargue en el mismo proceso, deshabilitando la característica en paralelo en proceso (consulte [ejecución en paralelo para interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="7f513-141">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="7f513-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f513-142">Example</span></span>

 <span data-ttu-id="7f513-143">El ejemplo siguiente muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7f513-143">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7f513-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f513-144">See also</span></span>

- [<span data-ttu-id="7f513-145">Esquema de la configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="7f513-145">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7f513-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7f513-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7f513-147">Cómo: Configuración de una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7f513-147">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="7f513-148">[Ejecución en paralelo para interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7f513-148">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="7f513-149">Ejecución en paralelo en proceso</span><span class="sxs-lookup"><span data-stu-id="7f513-149">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
