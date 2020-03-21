---
title: <startup> (elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153741"
---
# <a name="startup-element"></a><span data-ttu-id="993a6-102">\<startup> elemento</span><span class="sxs-lookup"><span data-stu-id="993a6-102">\<startup> element</span></span>

<span data-ttu-id="993a6-103">Especifica la información de inicio de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="993a6-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="993a6-104">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="993a6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="993a6-105">&nbsp;&nbsp;**\<>de inicio**</span><span class="sxs-lookup"><span data-stu-id="993a6-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="993a6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="993a6-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="993a6-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="993a6-107">Attributes and elements</span></span>

 <span data-ttu-id="993a6-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="993a6-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="993a6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="993a6-109">Attributes</span></span>

|<span data-ttu-id="993a6-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="993a6-110">Attribute</span></span>|<span data-ttu-id="993a6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="993a6-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="993a6-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="993a6-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="993a6-113">Especifica si se debe habilitar la directiva de activación en tiempo de ejecución de .NET Framework 2.0 o usar la directiva de activación de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="993a6-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="993a6-114">atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="993a6-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="993a6-115">Value</span><span class="sxs-lookup"><span data-stu-id="993a6-115">Value</span></span>|<span data-ttu-id="993a6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="993a6-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="993a6-117">Habilite la directiva de activación en tiempo de ejecución de .NET Framework 2.0 para el tiempo de ejecución elegido, que consiste en enlazar técnicas de activación en tiempo de ejecución heredadas (como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegido del archivo de configuración en lugar de limitarlas en la versión 2.0 de CLR.</span><span class="sxs-lookup"><span data-stu-id="993a6-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="993a6-118">Por lo tanto, si se elige CLR versión 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores de .NET Framework se cargan con la versión CLR elegida.</span><span class="sxs-lookup"><span data-stu-id="993a6-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="993a6-119">Establecer este valor impide que la versión 1.1 o la versión 2.0 de CLR se carguen en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso.</span><span class="sxs-lookup"><span data-stu-id="993a6-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="993a6-120">Use la directiva de activación predeterminada para .NET Framework 4 y versiones posteriores, que consiste en permitir que las técnicas de activación en tiempo de ejecución heredadas carguen LA versión 1.1 o 2.0 de CLR en el proceso.</span><span class="sxs-lookup"><span data-stu-id="993a6-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="993a6-121">Establecer este valor impide que los ensamblados en modo mixto se carguen en .NET Framework 4 o posterior a menos que se hayan compilado con .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="993a6-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="993a6-122">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="993a6-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="993a6-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="993a6-123">Child elements</span></span>

|<span data-ttu-id="993a6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="993a6-124">Element</span></span>|<span data-ttu-id="993a6-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="993a6-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="993a6-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="993a6-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="993a6-127">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="993a6-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="993a6-128">Las aplicaciones creadas con la versión \*\* \<\*\* en tiempo de ejecución 1.1 o posterior deben usar el elemento supportedRuntime>.</span><span class="sxs-lookup"><span data-stu-id="993a6-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="993a6-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="993a6-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="993a6-130">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="993a6-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="993a6-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="993a6-131">Parent elements</span></span>

|<span data-ttu-id="993a6-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="993a6-132">Element</span></span>|<span data-ttu-id="993a6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="993a6-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="993a6-134">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="993a6-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="993a6-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="993a6-135">Remarks</span></span>

 <span data-ttu-id="993a6-136">El \*\* \<elemento supportedRuntime>\*\* debe ser utilizado por todas las aplicaciones creadas con la versión 1.1 o posterior del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="993a6-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="993a6-137">Las aplicaciones creadas para admitir solo la \*\* \<\*\* versión 1.0 del tiempo de ejecución deben usar el elemento requiredRuntime>.</span><span class="sxs-lookup"><span data-stu-id="993a6-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="993a6-138">El código de inicio de una aplicación \*\* \<\*\* hospedada en Microsoft Internet Explorer omite el elemento>de inicio y sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="993a6-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="993a6-139">El atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="993a6-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="993a6-140">Este atributo es útil si la aplicación usa rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con .NET Framework 4 pero tiene una dependencia de un ensamblado en modo mixto creado con una versión anterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="993a6-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="993a6-141">En esos escenarios, establezca `true`el atributo en .</span><span class="sxs-lookup"><span data-stu-id="993a6-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="993a6-142">Establecer el `true` atributo para impedir que la versión 1.1 o la versión 2.0 de CLR se carguen en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso (consulte Ejecución en paralelo para la [interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="993a6-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="993a6-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="993a6-143">Example</span></span>

 <span data-ttu-id="993a6-144">En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="993a6-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="993a6-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="993a6-145">See also</span></span>

- [<span data-ttu-id="993a6-146">Esquema de configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="993a6-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="993a6-147">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="993a6-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="993a6-148">Cómo: Configurar una aplicación para admitir .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="993a6-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="993a6-149">[Ejecución simultánea para interoperabilidad COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="993a6-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="993a6-150">Ejecución en paralelo en proceso</span><span class="sxs-lookup"><span data-stu-id="993a6-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
