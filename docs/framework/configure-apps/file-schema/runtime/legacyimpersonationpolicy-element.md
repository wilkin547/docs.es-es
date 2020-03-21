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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154109"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="a3e10-102">\<legacyImpersonationPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="a3e10-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="a3e10-103">Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a3e10-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="a3e10-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3e10-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a3e10-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3e10-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a3e10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span><span class="sxs-lookup"><span data-stu-id="a3e10-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e10-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3e10-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3e10-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3e10-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a3e10-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3e10-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3e10-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3e10-110">Attributes</span></span>  
  
|<span data-ttu-id="a3e10-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a3e10-111">Attribute</span></span>|<span data-ttu-id="a3e10-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e10-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a3e10-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a3e10-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a3e10-114">Especifica que <xref:System.Security.Principal.WindowsIdentity> no fluye a través de <xref:System.Threading.ExecutionContext> puntos asincrónicos, independientemente de la configuración de flujo en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a3e10-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a3e10-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="a3e10-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a3e10-116">Value</span><span class="sxs-lookup"><span data-stu-id="a3e10-116">Value</span></span>|<span data-ttu-id="a3e10-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e10-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a3e10-118"><xref:System.Security.Principal.WindowsIdentity>fluye a través de <xref:System.Threading.ExecutionContext> puntos asincrónicos dependiendo de la configuración de flujo para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a3e10-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="a3e10-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a3e10-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a3e10-120"><xref:System.Security.Principal.WindowsIdentity>no fluye a través de <xref:System.Threading.ExecutionContext> puntos asincrónicos, independientemente de la configuración de flujo en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a3e10-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3e10-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3e10-121">Child Elements</span></span>  
 <span data-ttu-id="a3e10-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a3e10-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3e10-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3e10-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a3e10-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3e10-124">Element</span></span>|<span data-ttu-id="a3e10-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e10-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a3e10-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3e10-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a3e10-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a3e10-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3e10-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3e10-128">Remarks</span></span>  
 <span data-ttu-id="a3e10-129">En las versiones 1.0 y 1.1 de .NET Framework, <xref:System.Security.Principal.WindowsIdentity> no fluye a través de ningún punto asincrónico definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a3e10-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="a3e10-130">A partir de la versión 2.0 <xref:System.Threading.ExecutionContext> de .NET Framework, hay un objeto que contiene información sobre el subproceso que se está ejecutando actualmente y fluye a través de puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3e10-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="a3e10-131">Se <xref:System.Security.Principal.WindowsIdentity> incluye en este contexto de ejecución y, por lo tanto, también fluye a través de los puntos asincrónicos, lo que significa que si existe un contexto de suplantación, también fluirá.</span><span class="sxs-lookup"><span data-stu-id="a3e10-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="a3e10-132">A partir de .NET Framework 2.0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye a través de puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a3e10-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3e10-133">Common Language Runtime (CLR) es consciente de las operaciones de suplantación realizadas solo con código administrado, no de la suplantación realizada fuera del código administrado, como a través de la invocación de plataforma en código no administrado o mediante llamadas directas a funciones Win32.</span><span class="sxs-lookup"><span data-stu-id="a3e10-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="a3e10-134">Solo <xref:System.Security.Principal.WindowsIdentity> los objetos administrados pueden `alwaysFlowImpersonationPolicy` fluir a través`<alwaysFlowImpersonationPolicy enabled="true"/>`de puntos asincrónicos, a menos que el elemento se haya establecido en true ( ).</span><span class="sxs-lookup"><span data-stu-id="a3e10-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="a3e10-135">Establecer `alwaysFlowImpersonationPolicy` el elemento en true especifica que la identidad de Windows siempre fluye a través de puntos asincrónicos, independientemente de cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="a3e10-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="a3e10-136">Para obtener más información sobre el flujo de suplantación no administrada entre puntos asincrónicos, vea [ \<AlwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="a3e10-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="a3e10-137">Puede modificar este comportamiento predeterminado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="a3e10-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="a3e10-138">En código administrado por subproceso.</span><span class="sxs-lookup"><span data-stu-id="a3e10-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="a3e10-139">Puede suprimir el flujo por subproceso modificando <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> la configuración <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>y <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> mediante el método , o .</span><span class="sxs-lookup"><span data-stu-id="a3e10-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="a3e10-140">En la llamada a la interfaz de hospedaje no administrada para cargar Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a3e10-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="a3e10-141">Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la [función Función CorBindToRuntimeEx.](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)</span><span class="sxs-lookup"><span data-stu-id="a3e10-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="a3e10-142">Para habilitar el modo de compatibilidad para `flags` todo el proceso, establezca el parámetro para [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="a3e10-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="a3e10-143">Para obtener más información, vea [ \<el elemento alwaysFlowImpersonationPolicy>](alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="a3e10-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a3e10-144">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a3e10-144">Configuration File</span></span>  
 <span data-ttu-id="a3e10-145">En una aplicación de .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3e10-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="a3e10-146">Para una aplicación ASP.NET, el flujo de suplantación se puede \<configurar en el archivo aspnet.config que se encuentra en el directorio de carpetas de Windows>.</span><span class="sxs-lookup"><span data-stu-id="a3e10-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="a3e10-147">ASP.NET deshabilita de forma predeterminada el flujo de suplantación en el archivo aspnet.config mediante los siguientes valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="a3e10-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="a3e10-148">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe utilizar explícitamente los siguientes valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="a3e10-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="a3e10-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3e10-149">Example</span></span>  
 <span data-ttu-id="a3e10-150">En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no fluye la identidad de Windows a través de puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="a3e10-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3e10-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3e10-151">See also</span></span>

- [<span data-ttu-id="a3e10-152">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a3e10-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a3e10-153">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a3e10-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a3e10-154">\<alwaysFlowImpersonationPolicy> Element</span><span class="sxs-lookup"><span data-stu-id="a3e10-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
