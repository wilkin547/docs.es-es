---
title: '&lt;legacyImpersonationPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f6bed837ab7b0c6a4aebe6116c5ab28bbc62175
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a><span data-ttu-id="8313e-102">&lt;legacyImpersonationPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="8313e-102">&lt;legacyImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="8313e-103">Especifica que la identidad de Windows no fluye por puntos asincrónicos, independientemente de la configuración del flujo del contexto de ejecución del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="8313e-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="8313e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8313e-104">\<configuration></span></span>  
<span data-ttu-id="8313e-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="8313e-105">\<runtime></span></span>  
<span data-ttu-id="8313e-106">\<legacyImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="8313e-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8313e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8313e-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8313e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8313e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8313e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8313e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8313e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8313e-110">Attributes</span></span>  
  
|<span data-ttu-id="8313e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="8313e-111">Attribute</span></span>|<span data-ttu-id="8313e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8313e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="8313e-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="8313e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="8313e-114">Especifica que la <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos, sin tener en cuenta el <xref:System.Threading.ExecutionContext> flujo de configuración en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="8313e-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="8313e-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="8313e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="8313e-116">Valor</span><span class="sxs-lookup"><span data-stu-id="8313e-116">Value</span></span>|<span data-ttu-id="8313e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8313e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8313e-118"><xref:System.Security.Principal.WindowsIdentity>fluye por puntos asincrónicos según el <xref:System.Threading.ExecutionContext> flujo de configuración para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="8313e-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="8313e-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8313e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8313e-120"><xref:System.Security.Principal.WindowsIdentity>no fluye por puntos asincrónicos, sin tener en cuenta el <xref:System.Threading.ExecutionContext> flujo de configuración en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="8313e-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8313e-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8313e-121">Child Elements</span></span>  
 <span data-ttu-id="8313e-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8313e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8313e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8313e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8313e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8313e-124">Element</span></span>|<span data-ttu-id="8313e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8313e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8313e-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8313e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="8313e-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8313e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8313e-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8313e-128">Remarks</span></span>  
 <span data-ttu-id="8313e-129">En las versiones de .NET Framework 1.0 y 1.1, la <xref:System.Security.Principal.WindowsIdentity> no fluye por ningún punto asincrónico definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8313e-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="8313e-130">A partir de la versión 2.0 de .NET Framework, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso actualmente en ejecución y fluye por puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8313e-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="8313e-131">El <xref:System.Security.Principal.WindowsIdentity> se incluye en este contexto de ejecución y, por tanto, también fluye por los puntos asincrónicos, lo que significa que si existe un contexto de suplantación, se desplazarán así.</span><span class="sxs-lookup"><span data-stu-id="8313e-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="8313e-132">A partir de .NET Framework 2.0, puede usar el `<legacyImpersonationPolicy>` elemento para especificar que <xref:System.Security.Principal.WindowsIdentity> no fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="8313e-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8313e-133">Common language runtime (CLR) es consciente de suplantación invocación de operaciones realizadas sólo con código administrado, no de suplantación realizada fuera del código administrado, como a través de la plataforma a código no administrado o mediante llamadas directas a funciones de Win32.</span><span class="sxs-lookup"><span data-stu-id="8313e-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="8313e-134">Solo se ocupaba de <xref:System.Security.Principal.WindowsIdentity> objetos pueden fluir por puntos asincrónicos, a menos que la `alwaysFlowImpersonationPolicy` elemento se ha establecido en true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="8313e-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="8313e-135">Establecer el `alwaysFlowImpersonationPolicy` elemento a true especifica que la identidad de Windows siempre fluye por puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="8313e-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="8313e-136">Para obtener más información en la que fluyen suplantación no administrada por puntos asincrónicos, vea [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="8313e-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="8313e-137">Puede modificar este comportamiento predeterminado de dos formas:</span><span class="sxs-lookup"><span data-stu-id="8313e-137">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="8313e-138">En el código administrado en una base por subproceso.</span><span class="sxs-lookup"><span data-stu-id="8313e-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="8313e-139">Puede suprimir el flujo por subproceso modificando la <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext> configuración mediante el uso de la <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="8313e-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="8313e-140">En la llamada a la interfaz de hospedaje no administrada para cargar common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8313e-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="8313e-141">Si una interfaz de hospedaje no administrada (en lugar de un simple archivo ejecutable administrado) se usa para cargar CLR, puede especificar una marca especial en la llamada a la [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (función).</span><span class="sxs-lookup"><span data-stu-id="8313e-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="8313e-142">Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) en STARTUP_LEGACY_IMPERSONATION.</span><span class="sxs-lookup"><span data-stu-id="8313e-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="8313e-143">Para obtener más información, consulte el [ \<alwaysFlowImpersonationPolicy > elemento](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span><span class="sxs-lookup"><span data-stu-id="8313e-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="8313e-144">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="8313e-144">Configuration File</span></span>  
 <span data-ttu-id="8313e-145">En una aplicación de .NET Framework, este elemento se puede usar únicamente en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8313e-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="8313e-146">Para una aplicación ASP.NET, se puede configurar el flujo de suplantación en el archivo aspnet.config se encuentra en la \<carpeta Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.</span><span class="sxs-lookup"><span data-stu-id="8313e-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="8313e-147">ASP.NET de forma predeterminada, se deshabilita el flujo de suplantación en el archivo aspnet.config mediante las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="8313e-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="8313e-148">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe utilizar explícitamente los valores de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="8313e-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="8313e-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8313e-149">Example</span></span>  
 <span data-ttu-id="8313e-150">En el ejemplo siguiente se muestra cómo especificar el comportamiento heredado que no fluye la identidad de Windows por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="8313e-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8313e-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="8313e-151">See Also</span></span>  
 [<span data-ttu-id="8313e-152">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="8313e-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="8313e-153">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="8313e-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="8313e-154">\<alwaysFlowImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="8313e-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
