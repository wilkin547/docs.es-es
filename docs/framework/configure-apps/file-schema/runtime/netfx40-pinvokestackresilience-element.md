---
title: Elemento <NetFx40_PInvokeStackResilience>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116159"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="b30bd-102">\<NetFx40_PInvokeStackResilience> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="b30bd-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="b30bd-103">Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.</span><span class="sxs-lookup"><span data-stu-id="b30bd-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="b30bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b30bd-104">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b30bd-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b30bd-105">Attributes and Elements</span></span>

<span data-ttu-id="b30bd-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b30bd-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b30bd-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="b30bd-107">Attributes</span></span>

|<span data-ttu-id="b30bd-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="b30bd-108">Attribute</span></span>|<span data-ttu-id="b30bd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b30bd-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b30bd-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b30bd-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b30bd-111">Especifica si el tiempo de ejecución detecta declaraciones de invocación de plataforma incorrectas y corrige automáticamente la pila en tiempo de ejecución en las plataformas de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="b30bd-111">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="b30bd-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="b30bd-112">enabled Attribute</span></span>

|<span data-ttu-id="b30bd-113">Value</span><span class="sxs-lookup"><span data-stu-id="b30bd-113">Value</span></span>|<span data-ttu-id="b30bd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b30bd-114">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="b30bd-115">El motor en tiempo de ejecución utiliza la arquitectura de serialización de interoperabilidad más rápida incluida en el .NET Framework 4, que no detecta ni corrige las declaraciones de invocación de plataforma incorrectas.</span><span class="sxs-lookup"><span data-stu-id="b30bd-115">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="b30bd-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b30bd-116">This is the default.</span></span>|
|`1`|<span data-ttu-id="b30bd-117">El motor en tiempo de ejecución utiliza transiciones más lentas que detectan y corrigen declaraciones de invocación de plataforma incorrectas.</span><span class="sxs-lookup"><span data-stu-id="b30bd-117">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b30bd-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b30bd-118">Child Elements</span></span>

<span data-ttu-id="b30bd-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b30bd-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b30bd-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b30bd-120">Parent Elements</span></span>

|<span data-ttu-id="b30bd-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b30bd-121">Element</span></span>|<span data-ttu-id="b30bd-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b30bd-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b30bd-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b30bd-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b30bd-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b30bd-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b30bd-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b30bd-125">Remarks</span></span>

<span data-ttu-id="b30bd-126">Este elemento le permite intercambiar el cálculo de referencias de interoperabilidad más rápido para la resistencia en tiempo de ejecución con declaraciones de invocación de plataforma incorrectas.</span><span class="sxs-lookup"><span data-stu-id="b30bd-126">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="b30bd-127">A partir de la .NET Framework 4, una arquitectura de serialización de interoperabilidad simplificada proporciona una mejora significativa del rendimiento para las transiciones de código administrado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="b30bd-127">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="b30bd-128">En versiones anteriores del .NET Framework, la capa de serialización detectaba declaraciones de invocación de plataforma incorrectas en las plataformas de 32 bits y corrige automáticamente la pila.</span><span class="sxs-lookup"><span data-stu-id="b30bd-128">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="b30bd-129">La nueva arquitectura de cálculo de referencias elimina este paso.</span><span class="sxs-lookup"><span data-stu-id="b30bd-129">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="b30bd-130">Como resultado, las transiciones son muy rápidas, pero una declaración incorrecta de invocación de plataforma puede producir un error en el programa.</span><span class="sxs-lookup"><span data-stu-id="b30bd-130">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="b30bd-131">Para facilitar la detección de declaraciones incorrectas durante el desarrollo, se ha mejorado la experiencia de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b30bd-131">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="b30bd-132">El Asistente para la depuración administrada (MDA) de [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) le notifica las declaraciones de invocación de plataforma incorrectas cuando la aplicación se ejecuta con el depurador asociado.</span><span class="sxs-lookup"><span data-stu-id="b30bd-132">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="b30bd-133">Para solucionar los escenarios en los que la aplicación usa componentes que no se pueden volver a compilar y que tienen declaraciones de invocación de plataforma incorrectas, puede utilizar el `NetFx40_PInvokeStackResilience` elemento.</span><span class="sxs-lookup"><span data-stu-id="b30bd-133">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="b30bd-134">Al agregar este elemento al archivo de configuración de `enabled="1"` la aplicación, se opta por un modo de compatibilidad con el comportamiento de las versiones anteriores del .NET Framework, a costa de transiciones más lentas.</span><span class="sxs-lookup"><span data-stu-id="b30bd-134">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="b30bd-135">Los ensamblados compilados con versiones anteriores del .NET Framework se incorporan automáticamente a este modo de compatibilidad y no necesitan este elemento.</span><span class="sxs-lookup"><span data-stu-id="b30bd-135">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="b30bd-136">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b30bd-136">Configuration File</span></span>

<span data-ttu-id="b30bd-137">Este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b30bd-137">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="b30bd-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b30bd-138">Example</span></span>

<span data-ttu-id="b30bd-139">En el ejemplo siguiente se muestra cómo optar por aumentar la resistencia frente a las declaraciones de invocación de plataforma incorrectas para una aplicación, a costa de transiciones más lentas entre código administrado y no administrado.</span><span class="sxs-lookup"><span data-stu-id="b30bd-139">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b30bd-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b30bd-140">See also</span></span>

- [<span data-ttu-id="b30bd-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b30bd-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b30bd-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b30bd-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b30bd-143">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="b30bd-143">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
