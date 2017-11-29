---
title: '&lt;NetFx40_PInvokeStackResilience&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e77e43ed9d7520cbbcf453d067a49de3a86de3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="c2a38-102">&lt;NetFx40_PInvokeStackResilience&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="c2a38-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="c2a38-103">Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c2a38-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="c2a38-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c2a38-104">\<configuration></span></span>  
<span data-ttu-id="c2a38-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="c2a38-105">\<runtime></span></span>  
<span data-ttu-id="c2a38-106">< NetFx40_PInvokeStackResilience ></span><span class="sxs-lookup"><span data-stu-id="c2a38-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a38-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2a38-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2a38-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2a38-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c2a38-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c2a38-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2a38-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2a38-110">Attributes</span></span>  
  
|<span data-ttu-id="c2a38-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="c2a38-111">Attribute</span></span>|<span data-ttu-id="c2a38-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2a38-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c2a38-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c2a38-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c2a38-114">Especifica si el tiempo de ejecución detecta incorrecta de la plataforma declaraciones de invocación y corrige automáticamente la pila en tiempo de ejecución en plataformas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c2a38-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c2a38-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="c2a38-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c2a38-116">Valor</span><span class="sxs-lookup"><span data-stu-id="c2a38-116">Value</span></span>|<span data-ttu-id="c2a38-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2a38-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="c2a38-118">El runtime usa la arquitectura que se introdujo en referencias interoperativo más rápido el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], que no detecta y declaraciones de invocación de plataforma incorrectas de corrección.</span><span class="sxs-lookup"><span data-stu-id="c2a38-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="c2a38-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c2a38-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="c2a38-120">El runtime usa transiciones más lentas que detectan y corrigen incorrecta de la plataforma de declaraciones de invocación.</span><span class="sxs-lookup"><span data-stu-id="c2a38-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2a38-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2a38-121">Child Elements</span></span>  
 <span data-ttu-id="c2a38-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c2a38-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2a38-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2a38-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c2a38-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2a38-124">Element</span></span>|<span data-ttu-id="c2a38-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2a38-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c2a38-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2a38-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c2a38-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c2a38-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2a38-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2a38-128">Remarks</span></span>  
 <span data-ttu-id="c2a38-129">Este elemento le permite realizar transacciones comerciales más rápidos de referencias interoperativo para las declaraciones de invocación de resistencia de tiempo de ejecución con la plataforma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c2a38-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="c2a38-130">A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], una arquitectura de serialización de interoperabilidad simplificada proporciona una mejora significativa del rendimiento para las transiciones desde el código administrado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="c2a38-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="c2a38-131">En versiones anteriores de .NET Framework, la plataforma incorrecta de capa detectado serialización invocar declaraciones en plataformas de 32 bits y automáticamente fija la pila.</span><span class="sxs-lookup"><span data-stu-id="c2a38-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="c2a38-132">La nueva arquitectura de cálculo de referencias elimina este paso.</span><span class="sxs-lookup"><span data-stu-id="c2a38-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="c2a38-133">Como resultado, las transiciones son muy rápidas, pero declaración de invocación de una plataforma incorrecta puede producir un error de programa.</span><span class="sxs-lookup"><span data-stu-id="c2a38-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="c2a38-134">Para facilitar la detectar declaraciones incorrectas durante el desarrollo, se ha mejorado la experiencia de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c2a38-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="c2a38-135">El [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) Asistente para la depuración administrada (MDA) notifica sobre incorrecta de la plataforma declaraciones de invocación cuando se ejecuta la aplicación con el depurador adjunto.</span><span class="sxs-lookup"><span data-stu-id="c2a38-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="c2a38-136">Para resolver escenarios donde la aplicación usa componentes que no se puede volver a compilar, y que haya incorrecta declaraciones invocación de plataforma, puede usar el `NetFx40_PInvokeStackResilience` elemento.</span><span class="sxs-lookup"><span data-stu-id="c2a38-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="c2a38-137">Agregar este elemento a su archivo de configuración de aplicación con `enabled="1"` opta por participar en un modo de compatibilidad con el comportamiento de versiones anteriores de .NET Framework, pero a costa de transiciones más lentas.</span><span class="sxs-lookup"><span data-stu-id="c2a38-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="c2a38-138">Los ensamblados que se han compilado con versiones anteriores de .NET Framework se suscriben automáticamente en este modo de compatibilidad y no es necesario este elemento.</span><span class="sxs-lookup"><span data-stu-id="c2a38-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c2a38-139">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c2a38-139">Configuration File</span></span>  
 <span data-ttu-id="c2a38-140">Este elemento se puede usar únicamente en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="c2a38-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2a38-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2a38-141">Example</span></span>  
 <span data-ttu-id="c2a38-142">El ejemplo siguiente muestra cómo no formen parte de una mayor resistencia contra incorrecta de invocación de plataforma declaraciones para una aplicación, a costa de transiciones más lentas entre código administrado y.</span><span class="sxs-lookup"><span data-stu-id="c2a38-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2a38-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2a38-143">See Also</span></span>  
 [<span data-ttu-id="c2a38-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c2a38-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="c2a38-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c2a38-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="c2a38-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="c2a38-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
