---
title: '&lt;alwaysFlowImpersonationPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be1df955f7586848968cb32cd66a4c6889cfffa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="d5145-102">&lt;alwaysFlowImpersonationPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d5145-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="d5145-103">Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="d5145-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="d5145-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d5145-104">\<configuration></span></span>  
<span data-ttu-id="d5145-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="d5145-105">\<runtime></span></span>  
<span data-ttu-id="d5145-106">\<alwaysFlowImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="d5145-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5145-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5145-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5145-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5145-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d5145-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d5145-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5145-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5145-110">Attributes</span></span>  
  
|<span data-ttu-id="d5145-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d5145-111">Attribute</span></span>|<span data-ttu-id="d5145-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5145-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d5145-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d5145-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d5145-114">Indica si la identidad de Windows fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="d5145-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d5145-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="d5145-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d5145-116">Valor</span><span class="sxs-lookup"><span data-stu-id="d5145-116">Value</span></span>|<span data-ttu-id="d5145-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5145-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d5145-118">La identidad no fluye por puntos asincrónicos, a menos que la suplantación se realiza a través de Windows administrados métodos como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d5145-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="d5145-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d5145-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="d5145-120">La identidad de Windows siempre fluye por puntos asincrónicos, sin tener en cuenta cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="d5145-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5145-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5145-121">Child Elements</span></span>  
 <span data-ttu-id="d5145-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5145-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5145-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5145-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d5145-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5145-124">Element</span></span>|<span data-ttu-id="d5145-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5145-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d5145-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5145-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d5145-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d5145-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5145-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5145-128">Remarks</span></span>  
 <span data-ttu-id="d5145-129">En las versiones 1.0 y 1.1 de .NET Framework, la identidad de Windows no fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="d5145-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="d5145-130">En la versión 2.0 de .NET Framework, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso actualmente en ejecución y fluye por puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5145-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="d5145-131">El <xref:System.Security.Principal.WindowsIdentity> también fluye como parte de la información que fluye por los puntos asincrónicos, siempre que se ha realizado la suplantación mediante métodos administrados como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> y no a través de otros medios como plataforma, invocar métodos nativos.</span><span class="sxs-lookup"><span data-stu-id="d5145-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="d5145-132">Este elemento se utiliza para especificar que la identidad de Windows fluye por puntos asincrónicos, sin tener en cuenta cómo se logró la suplantación.</span><span class="sxs-lookup"><span data-stu-id="d5145-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="d5145-133">Puede modificar este comportamiento predeterminado de dos formas:</span><span class="sxs-lookup"><span data-stu-id="d5145-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="d5145-134">En el código administrado en una base por subproceso.</span><span class="sxs-lookup"><span data-stu-id="d5145-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="d5145-135">Puede suprimir el flujo por subproceso modificando la <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext> configuración mediante el uso de la <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="d5145-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="d5145-136">En la llamada a la interfaz de hospedaje no administrada para cargar common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d5145-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="d5145-137">Si una interfaz de hospedaje no administrada (en lugar de un simple archivo ejecutable administrado) se usa para cargar CLR, puede especificar una marca especial en la llamada a la [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) (función).</span><span class="sxs-lookup"><span data-stu-id="d5145-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="d5145-138">Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) a `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="d5145-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d5145-139">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d5145-139">Configuration File</span></span>  
 <span data-ttu-id="d5145-140">En una aplicación de .NET Framework, este elemento se puede usar únicamente en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5145-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="d5145-141">Para una aplicación ASP.NET, se puede configurar el flujo de suplantación en el archivo aspnet.config se encuentra en la \<carpeta Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.</span><span class="sxs-lookup"><span data-stu-id="d5145-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="d5145-142">ASP.NET de forma predeterminada, se deshabilita el flujo de suplantación en el archivo aspnet.config mediante las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="d5145-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="d5145-143">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe utilizar explícitamente los valores de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="d5145-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="d5145-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5145-144">Example</span></span>  
 <span data-ttu-id="d5145-145">En el ejemplo siguiente se muestra cómo especificar que la identidad de Windows fluye por puntos asincrónicos, incluso cuando la suplantación se logra a través de otros medios distintos de los métodos administrados.</span><span class="sxs-lookup"><span data-stu-id="d5145-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5145-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5145-146">See Also</span></span>  
 [<span data-ttu-id="d5145-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d5145-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d5145-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d5145-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="d5145-149">\<legacyImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="d5145-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
