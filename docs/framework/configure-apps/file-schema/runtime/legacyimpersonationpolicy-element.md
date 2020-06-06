---
title: <legacyImpersonationPolicy> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154109"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="d3cbb-102">\<legacyImpersonationPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="d3cbb-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="d3cbb-103">Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="d3cbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3cbb-104">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3cbb-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d3cbb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d3cbb-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3cbb-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d3cbb-107">Attributes</span></span>  
  
|<span data-ttu-id="d3cbb-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d3cbb-108">Attribute</span></span>|<span data-ttu-id="d3cbb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3cbb-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d3cbb-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="d3cbb-111">Especifica que el no <xref:System.Security.Principal.WindowsIdentity> fluye por puntos asincrónicos, independientemente de la <xref:System.Threading.ExecutionContext> configuración de Flow en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-111">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d3cbb-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="d3cbb-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="d3cbb-113">Value</span><span class="sxs-lookup"><span data-stu-id="d3cbb-113">Value</span></span>|<span data-ttu-id="d3cbb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3cbb-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d3cbb-115"><xref:System.Security.Principal.WindowsIdentity>fluye a través de puntos asincrónicos en función de la <xref:System.Threading.ExecutionContext> configuración de flujo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-115"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="d3cbb-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d3cbb-117"><xref:System.Security.Principal.WindowsIdentity>no fluye por puntos asincrónicos, independientemente de la <xref:System.Threading.ExecutionContext> configuración de Flow en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-117"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3cbb-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d3cbb-118">Child Elements</span></span>  
 <span data-ttu-id="d3cbb-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3cbb-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d3cbb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d3cbb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d3cbb-121">Element</span></span>|<span data-ttu-id="d3cbb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3cbb-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d3cbb-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d3cbb-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3cbb-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d3cbb-125">Remarks</span></span>  
 <span data-ttu-id="d3cbb-126">En las .NET Framework versiones 1,0 y 1,1, no <xref:System.Security.Principal.WindowsIdentity> fluye por los puntos asincrónicos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-126">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="d3cbb-127">A partir de la versión .NET Framework 2,0, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso que se está ejecutando actualmente y fluye a través de los puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-127">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="d3cbb-128"><xref:System.Security.Principal.WindowsIdentity>Se incluye en este contexto de ejecución y, por tanto, también fluye por los puntos asincrónicos, lo que significa que, si existe un contexto de suplantación, se producirá un flujo también.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-128">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="d3cbb-129">A partir de la .NET Framework 2,0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-129">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3cbb-130">El Common Language Runtime (CLR) es consciente de las operaciones de suplantación realizadas con solo código administrado, no de la suplantación realizada fuera del código administrado, como a través de la invocación de plataforma a código no administrado o a través de llamadas directas a funciones de Win32.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-130">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="d3cbb-131">Solo <xref:System.Security.Principal.WindowsIdentity> los objetos administrados pueden fluir por puntos asincrónicos, a menos que el elemento se haya `alwaysFlowImpersonationPolicy` establecido en true ( `<alwaysFlowImpersonationPolicy enabled="true"/>` ).</span><span class="sxs-lookup"><span data-stu-id="d3cbb-131">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="d3cbb-132">Al establecer el `alwaysFlowImpersonationPolicy` elemento en true, se especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se haya realizado la suplantación.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-132">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="d3cbb-133">Para obtener más información sobre cómo fluir la suplantación no administrada a través de puntos asincrónicos, vea [ \<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="d3cbb-133">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="d3cbb-134">Puede modificar este comportamiento predeterminado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="d3cbb-134">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="d3cbb-135">En código administrado para cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-135">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="d3cbb-136">Puede suprimir el flujo por subproceso modificando la configuración de y mediante <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> método, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="d3cbb-136">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="d3cbb-137">En la llamada a la interfaz de hospedaje no administrada para cargar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d3cbb-137">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="d3cbb-138">Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la función de [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d3cbb-138">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="d3cbb-139">Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro de la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-139">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="d3cbb-140">Para obtener más información, vea el [ \<alwaysFlowImpersonationPolicy> elemento](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="d3cbb-140">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d3cbb-141">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d3cbb-141">Configuration File</span></span>  
 <span data-ttu-id="d3cbb-142">En una aplicación .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-142">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="d3cbb-143">En el caso de una aplicación de ASP.NET, el flujo de suplantación se puede configurar en el archivo Aspnet. config que se encuentra en el \<Windows Folder> directorio \Microsoft.NET\Framework\vx.x.xxxx</span><span class="sxs-lookup"><span data-stu-id="d3cbb-143">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="d3cbb-144">De forma predeterminada, ASP.NET deshabilita el flujo de suplantación en el archivo Aspnet. config con las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="d3cbb-144">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d3cbb-145">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe usar explícitamente las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="d3cbb-145">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="d3cbb-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d3cbb-146">Example</span></span>  
 <span data-ttu-id="d3cbb-147">En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no transmite la identidad de Windows a través de puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="d3cbb-147">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3cbb-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3cbb-148">See also</span></span>

- [<span data-ttu-id="d3cbb-149">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d3cbb-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d3cbb-150">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d3cbb-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d3cbb-151">\<alwaysFlowImpersonationPolicy>Element</span><span class="sxs-lookup"><span data-stu-id="d3cbb-151">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
