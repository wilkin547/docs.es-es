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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da01d0dac2e67d6c0131a2b5965472bbd19213fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927325"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="9fc53-102">\<legacyImpersonationPolicy >, elemento</span><span class="sxs-lookup"><span data-stu-id="9fc53-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="9fc53-103">Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9fc53-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="9fc53-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9fc53-104">\<configuration></span></span>  
<span data-ttu-id="9fc53-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9fc53-105">\<runtime></span></span>  
<span data-ttu-id="9fc53-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="9fc53-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fc53-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fc53-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fc53-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9fc53-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9fc53-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9fc53-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fc53-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="9fc53-110">Attributes</span></span>  
  
|<span data-ttu-id="9fc53-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="9fc53-111">Attribute</span></span>|<span data-ttu-id="9fc53-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9fc53-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9fc53-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9fc53-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9fc53-114">Especifica que el <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos, independientemente de la <xref:System.Threading.ExecutionContext> configuración de Flow en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9fc53-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9fc53-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="9fc53-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9fc53-116">Value</span><span class="sxs-lookup"><span data-stu-id="9fc53-116">Value</span></span>|<span data-ttu-id="9fc53-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9fc53-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9fc53-118"><xref:System.Security.Principal.WindowsIdentity>fluye a través de puntos asincrónicos en función <xref:System.Threading.ExecutionContext> de la configuración de flujo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9fc53-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="9fc53-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9fc53-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9fc53-120"><xref:System.Security.Principal.WindowsIdentity>no fluye por puntos asincrónicos, independientemente de la <xref:System.Threading.ExecutionContext> configuración de Flow en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="9fc53-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fc53-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9fc53-121">Child Elements</span></span>  
 <span data-ttu-id="9fc53-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9fc53-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fc53-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9fc53-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9fc53-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9fc53-124">Element</span></span>|<span data-ttu-id="9fc53-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9fc53-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9fc53-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9fc53-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9fc53-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9fc53-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fc53-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9fc53-128">Remarks</span></span>  
 <span data-ttu-id="9fc53-129">En las .NET Framework versiones 1,0 y 1,1, no <xref:System.Security.Principal.WindowsIdentity> fluye por los puntos asincrónicos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9fc53-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="9fc53-130">A partir de la versión .NET Framework 2,0, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso que se está ejecutando actualmente y fluye a través de los puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9fc53-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="9fc53-131"><xref:System.Security.Principal.WindowsIdentity> Se incluye en este contexto de ejecución y, por tanto, también fluye por los puntos asincrónicos, lo que significa que, si existe un contexto de suplantación, se producirá un flujo también.</span><span class="sxs-lookup"><span data-stu-id="9fc53-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="9fc53-132">A partir de la .NET Framework 2,0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="9fc53-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fc53-133">El Common Language Runtime (CLR) es consciente de las operaciones de suplantación realizadas con solo código administrado, no de la suplantación realizada fuera del código administrado, como a través de la invocación de plataforma a código no administrado o a través de llamadas directas a funciones de Win32.</span><span class="sxs-lookup"><span data-stu-id="9fc53-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="9fc53-134">Solo los <xref:System.Security.Principal.WindowsIdentity> objetos administrados pueden fluir por puntos asincrónicos, `alwaysFlowImpersonationPolicy` a menos que el elemento se haya`<alwaysFlowImpersonationPolicy enabled="true"/>`establecido en true ().</span><span class="sxs-lookup"><span data-stu-id="9fc53-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="9fc53-135">Al establecer `alwaysFlowImpersonationPolicy` el elemento en true, se especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se haya realizado la suplantación.</span><span class="sxs-lookup"><span data-stu-id="9fc53-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="9fc53-136">Para obtener más información sobre cómo fluir la suplantación no administrada a través de puntos asincrónicos, vea [ \<alwaysFlowImpersonationPolicy > elemento](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="9fc53-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="9fc53-137">Puede modificar este comportamiento predeterminado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="9fc53-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="9fc53-138">En código administrado para cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="9fc53-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="9fc53-139">Puede suprimir el flujo por subproceso <xref:System.Threading.ExecutionContext> modificando la configuración de y <xref:System.Security.SecurityContext> mediante el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>método, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9fc53-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="9fc53-140">En la llamada a la interfaz de hospedaje no administrada para cargar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9fc53-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="9fc53-141">Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la función de [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9fc53-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="9fc53-142">Para habilitar el modo de compatibilidad para todo el proceso, establezca `flags` el parámetro de la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="9fc53-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="9fc53-143">Para obtener más información, vea el [ \<elemento > de alwaysFlowImpersonationPolicy](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="9fc53-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9fc53-144">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="9fc53-144">Configuration File</span></span>  
 <span data-ttu-id="9fc53-145">En una aplicación .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9fc53-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="9fc53-146">En el caso de una aplicación ASP.net, el flujo de suplantación se puede configurar en el archivo Aspnet. \<config que se encuentra en la carpeta Windows > directorio \Microsoft.NET\Framework\vx.x.xxxx</span><span class="sxs-lookup"><span data-stu-id="9fc53-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="9fc53-147">De forma predeterminada, ASP.NET deshabilita el flujo de suplantación en el archivo Aspnet. config con las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="9fc53-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="9fc53-148">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe usar explícitamente las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="9fc53-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="9fc53-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fc53-149">Example</span></span>  
 <span data-ttu-id="9fc53-150">En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no transmite la identidad de Windows a través de puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="9fc53-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fc53-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fc53-151">See also</span></span>

- [<span data-ttu-id="9fc53-152">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="9fc53-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9fc53-153">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9fc53-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9fc53-154">\<alwaysFlowImpersonationPolicy >, elemento</span><span class="sxs-lookup"><span data-stu-id="9fc53-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
