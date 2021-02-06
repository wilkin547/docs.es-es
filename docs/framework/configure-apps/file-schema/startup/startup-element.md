---
description: 'Más información acerca de: <startup> elemento'
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
ms.openlocfilehash: 82ece56aaa05376237922b3bd54b6f15967adf8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639827"
---
# <a name="startup-element"></a><span data-ttu-id="5bab2-103">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="5bab2-103">\<startup> element</span></span>

<span data-ttu-id="5bab2-104">Especifica Common Language Runtime información de inicio.</span><span class="sxs-lookup"><span data-stu-id="5bab2-104">Specifies common language runtime startup information.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<startup>**  

## <a name="syntax"></a><span data-ttu-id="5bab2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bab2-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5bab2-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5bab2-106">Attributes and elements</span></span>

 <span data-ttu-id="5bab2-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5bab2-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5bab2-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5bab2-108">Attributes</span></span>

|<span data-ttu-id="5bab2-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5bab2-109">Attribute</span></span>|<span data-ttu-id="5bab2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bab2-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="5bab2-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="5bab2-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5bab2-112">Especifica si se debe habilitar la Directiva de activación en tiempo de ejecución de .NET Framework 2,0 o usar la Directiva de activación de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="5bab2-112">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="5bab2-113">useLegacyV2RuntimeActivationPolicy (atributo)</span><span class="sxs-lookup"><span data-stu-id="5bab2-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="5bab2-114">Value</span><span class="sxs-lookup"><span data-stu-id="5bab2-114">Value</span></span>|<span data-ttu-id="5bab2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bab2-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="5bab2-116">Habilite la Directiva de activación en tiempo de ejecución de .NET Framework 2,0 para el tiempo de ejecución elegido, que consiste en enlazar las técnicas de activación en tiempo de ejecución heredadas (como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) al tiempo de ejecución elegido desde el archivo de configuración en lugar de limitarlos a la versión 2,0 de CLR.</span><span class="sxs-lookup"><span data-stu-id="5bab2-116">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="5bab2-117">Por lo tanto, si se elige CLR versión 4 o posterior del archivo de configuración, los ensamblados de modo mixto creados con versiones anteriores del .NET Framework se cargan con la versión de CLR elegida.</span><span class="sxs-lookup"><span data-stu-id="5bab2-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="5bab2-118">Si se establece este valor, se evita que la versión 1,1 o la versión 2,0 de CLR se carguen en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso.</span><span class="sxs-lookup"><span data-stu-id="5bab2-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="5bab2-119">Use la Directiva de activación predeterminada para el .NET Framework 4 y versiones posteriores, que consiste en permitir técnicas de activación en tiempo de ejecución heredadas para cargar la versión 1,1 o 2,0 de CLR en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5bab2-119">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="5bab2-120">Al establecer este valor, se evita que los ensamblados de modo mixto se carguen en el .NET Framework 4 o posterior, a menos que se hayan compilado con .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="5bab2-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="5bab2-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5bab2-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5bab2-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5bab2-122">Child elements</span></span>

|<span data-ttu-id="5bab2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bab2-123">Element</span></span>|<span data-ttu-id="5bab2-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bab2-124">Description</span></span>|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="5bab2-125">Especifica que la aplicación solo admite la versión 1.0 de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5bab2-125">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="5bab2-126">Las aplicaciones compiladas con la versión 1,1 o posterior del tiempo de ejecución deben usar el **\<supportedRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="5bab2-126">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="5bab2-127">Especifica qué versiones de Common Language Runtime admite la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5bab2-127">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="5bab2-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5bab2-128">Parent elements</span></span>

|<span data-ttu-id="5bab2-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="5bab2-129">Element</span></span>|<span data-ttu-id="5bab2-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bab2-130">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="5bab2-131">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5bab2-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5bab2-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5bab2-132">Remarks</span></span>

 <span data-ttu-id="5bab2-133">**\<supportedRuntime>** Todas las aplicaciones compiladas con la versión 1,1 o posterior del tiempo de ejecución deben usar el elemento.</span><span class="sxs-lookup"><span data-stu-id="5bab2-133">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="5bab2-134">Las aplicaciones compiladas para admitir solo la versión 1,0 del Runtime deben usar el **\<requiredRuntime>** elemento.</span><span class="sxs-lookup"><span data-stu-id="5bab2-134">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="5bab2-135">El código de inicio de una aplicación hospedada en Microsoft Internet Explorer omite el **\<startup>** elemento y sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="5bab2-135">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="5bab2-136">El atributo useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="5bab2-136">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="5bab2-137">Este atributo es útil si la aplicación usa rutas de activación heredadas, como la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), y desea que esas rutas de acceso activen la versión 4 de CLR en lugar de una versión anterior, o si la aplicación se compila con el .NET Framework 4 pero tiene una dependencia en un ensamblado de modo mixto creado con una versión anterior del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5bab2-137">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="5bab2-138">En esos escenarios, establezca el atributo en `true` .</span><span class="sxs-lookup"><span data-stu-id="5bab2-138">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="5bab2-139">Al establecer el atributo en, se evita que la `true` versión de clr 1,1 o la versión 2,0 de CLR se cargue en el mismo proceso, deshabilitando eficazmente la característica en paralelo en proceso (vea la [ejecución en paralelo para la interoperabilidad com](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="5bab2-139">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="5bab2-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bab2-140">Example</span></span>

 <span data-ttu-id="5bab2-141">En el ejemplo siguiente se muestra cómo especificar la versión en tiempo de ejecución en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bab2-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5bab2-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bab2-142">See also</span></span>

- [<span data-ttu-id="5bab2-143">Esquema de configuración de inicio</span><span class="sxs-lookup"><span data-stu-id="5bab2-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5bab2-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5bab2-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5bab2-145">Cómo: Configurar una aplicación para que admita .NET Framework 4 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="5bab2-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="5bab2-146">[Ejecución simultánea para interoperabilidad COM](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5bab2-146">[Side-by-Side Execution for COM Interop](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="5bab2-147">Ejecución en paralelo en proceso</span><span class="sxs-lookup"><span data-stu-id="5bab2-147">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
