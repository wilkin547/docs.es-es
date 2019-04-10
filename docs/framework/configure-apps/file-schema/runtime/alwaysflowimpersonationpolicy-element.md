---
title: <alwaysFlowImpersonationPolicy> Elemento
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec411039363cfb118fee06dff88daf50bbc97a86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314781"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="15dce-102">\<alwaysFlowImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="15dce-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="15dce-103">Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="15dce-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="15dce-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="15dce-104">\<configuration></span></span>  
<span data-ttu-id="15dce-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="15dce-105">\<runtime></span></span>  
<span data-ttu-id="15dce-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="15dce-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15dce-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15dce-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15dce-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15dce-108">Attributes and Elements</span></span>  
 <span data-ttu-id="15dce-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15dce-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15dce-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="15dce-110">Attributes</span></span>  
  
|<span data-ttu-id="15dce-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="15dce-111">Attribute</span></span>|<span data-ttu-id="15dce-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="15dce-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="15dce-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="15dce-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="15dce-114">Indica si la identidad de Windows fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="15dce-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="15dce-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="15dce-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="15dce-116">Valor</span><span class="sxs-lookup"><span data-stu-id="15dce-116">Value</span></span>|<span data-ttu-id="15dce-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="15dce-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="15dce-118">La identidad no fluye por puntos asincrónicos, a menos que la suplantación se realiza a través de Windows administrado métodos como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span><span class="sxs-lookup"><span data-stu-id="15dce-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="15dce-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="15dce-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="15dce-120">La identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="15dce-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15dce-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15dce-121">Child Elements</span></span>  
 <span data-ttu-id="15dce-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15dce-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15dce-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15dce-123">Parent Elements</span></span>  
  
|<span data-ttu-id="15dce-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="15dce-124">Element</span></span>|<span data-ttu-id="15dce-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="15dce-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="15dce-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="15dce-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="15dce-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="15dce-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15dce-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15dce-128">Remarks</span></span>  
 <span data-ttu-id="15dce-129">En las versiones 1.0 y 1.1 de .NET Framework, la identidad de Windows no fluye por puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="15dce-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="15dce-130">En la versión 2.0 de .NET Framework, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso actualmente en ejecución y hace que fluya por puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="15dce-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="15dce-131">El <xref:System.Security.Principal.WindowsIdentity> también flujos como parte de la información que fluye a través de los puntos asincrónicos, siempre que la suplantación se logra mediante métodos administran como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> y no a través de otros medios como plataforma de invocación a métodos nativos.</span><span class="sxs-lookup"><span data-stu-id="15dce-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="15dce-132">Este elemento se utiliza para especificar que la identidad de Windows fluye por puntos asincrónicos, independientemente de cómo se logró la suplantación.</span><span class="sxs-lookup"><span data-stu-id="15dce-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="15dce-133">Puede modificar este comportamiento predeterminado de dos formas:</span><span class="sxs-lookup"><span data-stu-id="15dce-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="15dce-134">En el código administrado en una base por subproceso.</span><span class="sxs-lookup"><span data-stu-id="15dce-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="15dce-135">Puede suprimir el flujo por subproceso modificando el <xref:System.Threading.ExecutionContext> y <xref:System.Security.SecurityContext> valores mediante el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="15dce-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="15dce-136">En la llamada a la interfaz de hospedaje no administrada para cargar common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="15dce-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="15dce-137">Si una interfaz de hospedaje no administrada (en lugar de un ejecutable simple administrado) se usa para cargar el CLR, puede especificar un marcador especial en la llamada a la [función CorBindToRuntimeEx](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="15dce-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="15dce-138">Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro [CorBindToRuntimeEx (función)](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) a `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span><span class="sxs-lookup"><span data-stu-id="15dce-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="15dce-139">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="15dce-139">Configuration File</span></span>  
 <span data-ttu-id="15dce-140">En una aplicación de .NET Framework, este elemento se puede usar solo en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="15dce-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="15dce-141">Para una aplicación ASP.NET, el flujo de suplantación puede configurarse en el archivo aspnet.config se encuentra en la \<carpeta de Windows > \Microsoft.NET\Framework\vx.x.xxxx directory.</span><span class="sxs-lookup"><span data-stu-id="15dce-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="15dce-142">ASP.NET de forma predeterminada, se deshabilita el flujo de suplantación en el archivo aspnet.config mediante el uso de las opciones de configuración siguientes:</span><span class="sxs-lookup"><span data-stu-id="15dce-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="15dce-143">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe usar explícitamente la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="15dce-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="15dce-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15dce-144">Example</span></span>  
 <span data-ttu-id="15dce-145">El ejemplo siguiente muestra cómo especificar que la identidad de Windows fluye por puntos asincrónicos, incluso cuando la suplantación se logra a través de otros medios distintos métodos administrados.</span><span class="sxs-lookup"><span data-stu-id="15dce-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15dce-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="15dce-146">See also</span></span>

- [<span data-ttu-id="15dce-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="15dce-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="15dce-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="15dce-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="15dce-149">\<legacyImpersonationPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="15dce-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
