---
title: Elemento <NetFx40_PInvokeStackResilience>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7a1cf34f63b1ba0dfced8ff23c252f3363723c6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489410"
---
# <a name="netfx40pinvokestackresilience-element"></a><span data-ttu-id="7f791-102">\<NetFx40_PInvokeStackResilience > elemento</span><span class="sxs-lookup"><span data-stu-id="7f791-102">\<NetFx40_PInvokeStackResilience> Element</span></span>
<span data-ttu-id="7f791-103">Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.</span><span class="sxs-lookup"><span data-stu-id="7f791-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="7f791-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7f791-104">\<configuration></span></span>  
<span data-ttu-id="7f791-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7f791-105">\<runtime></span></span>  
<span data-ttu-id="7f791-106"><NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="7f791-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f791-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f791-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f791-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f791-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7f791-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7f791-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f791-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f791-110">Attributes</span></span>  
  
|<span data-ttu-id="7f791-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="7f791-111">Attribute</span></span>|<span data-ttu-id="7f791-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f791-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7f791-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7f791-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f791-114">Especifica si el tiempo de ejecución detecta incorrecta de la plataforma las declaraciones de invocación y corrige automáticamente la pila en tiempo de ejecución en plataformas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7f791-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7f791-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="7f791-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7f791-116">Valor</span><span class="sxs-lookup"><span data-stu-id="7f791-116">Value</span></span>|<span data-ttu-id="7f791-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f791-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="7f791-118">El runtime usa la arquitectura que se introdujo en .NET Framework 4, no detecta de serialización de interoperabilidad más rápido y declaraciones de invocación de plataforma incorrectas de corrección.</span><span class="sxs-lookup"><span data-stu-id="7f791-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="7f791-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f791-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="7f791-120">El runtime usa transiciones más lentas que detectan y corrigen incorrecta de la plataforma de declaraciones de invocación.</span><span class="sxs-lookup"><span data-stu-id="7f791-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f791-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f791-121">Child Elements</span></span>  
 <span data-ttu-id="7f791-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7f791-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f791-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f791-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7f791-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f791-124">Element</span></span>|<span data-ttu-id="7f791-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f791-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7f791-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f791-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7f791-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f791-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f791-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f791-128">Remarks</span></span>  
 <span data-ttu-id="7f791-129">Este elemento le permite intercambiar más rápido la serialización de interoperabilidad para las declaraciones de invocación de tiempo de ejecución Resista la plataforma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="7f791-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="7f791-130">A partir de .NET Framework 4, una arquitectura de cálculo de referencias de interoperabilidad simplificada proporciona una mejora significativa del rendimiento de las transiciones de código administrado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="7f791-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="7f791-131">En versiones anteriores de .NET Framework, la plataforma incorrecta cálculo de referencias de capa detectado invocar declaraciones en las plataformas de 32 bits y automáticamente se ha corregido la pila.</span><span class="sxs-lookup"><span data-stu-id="7f791-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="7f791-132">La nueva arquitectura de cálculo de referencias elimina este paso.</span><span class="sxs-lookup"><span data-stu-id="7f791-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="7f791-133">Como resultado, transiciones son muy rápidas, pero la declaración de invocación de una plataforma incorrecta puede producir un error de programa.</span><span class="sxs-lookup"><span data-stu-id="7f791-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="7f791-134">Para que sea fácil de detectar declaraciones incorrectas durante el desarrollo, se ha mejorado la experiencia de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7f791-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="7f791-135">El [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) Asistente para la depuración administrada (MDA) notifica a las declaraciones de plataforma incorrectas de invocación cuando se ejecuta la aplicación con el depurador adjunto.</span><span class="sxs-lookup"><span data-stu-id="7f791-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="7f791-136">Para abordar escenarios donde la aplicación usa componentes que no se puede volver a compilar, y que dispone de invocación de plataforma incorrectas declaraciones, puede usar el `NetFx40_PInvokeStackResilience` elemento.</span><span class="sxs-lookup"><span data-stu-id="7f791-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="7f791-137">Al agregar este elemento al archivo de configuración de la aplicación con `enabled="1"` incluye un modo de compatibilidad con el comportamiento de las versiones anteriores de .NET Framework, a costa de transiciones más lentas.</span><span class="sxs-lookup"><span data-stu-id="7f791-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="7f791-138">Los ensamblados que se han compilado con versiones anteriores de .NET Framework se suscriben automáticamente en este modo de compatibilidad y no es necesario este elemento.</span><span class="sxs-lookup"><span data-stu-id="7f791-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="7f791-139">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7f791-139">Configuration File</span></span>  
 <span data-ttu-id="7f791-140">Este elemento se puede usar solo en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f791-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f791-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f791-141">Example</span></span>  
 <span data-ttu-id="7f791-142">El ejemplo siguiente se muestra cómo para participar en una mayor resistencia contra incorrecta de invocación de plataforma declaraciones para una aplicación, a costa de transiciones más lentas entre código administrado y.</span><span class="sxs-lookup"><span data-stu-id="7f791-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7f791-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f791-143">See also</span></span>

- [<span data-ttu-id="7f791-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="7f791-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7f791-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7f791-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7f791-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="7f791-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
