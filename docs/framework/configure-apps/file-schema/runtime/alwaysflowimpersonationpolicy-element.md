---
title: <alwaysFlowImpersonationPolicy> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154488"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="62ffc-102">\<alwaysFlowImpersonationPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="62ffc-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="62ffc-103">Especifica que la identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se realizó la suplantación.</span><span class="sxs-lookup"><span data-stu-id="62ffc-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**\  
  
## <a name="syntax"></a><span data-ttu-id="62ffc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62ffc-104">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62ffc-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="62ffc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="62ffc-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="62ffc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62ffc-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="62ffc-107">Attributes</span></span>  
  
|<span data-ttu-id="62ffc-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="62ffc-108">Attribute</span></span>|<span data-ttu-id="62ffc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="62ffc-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="62ffc-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="62ffc-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="62ffc-111">Indica si la identidad de Windows fluye a través de puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="62ffc-111">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="62ffc-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="62ffc-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="62ffc-113">Value</span><span class="sxs-lookup"><span data-stu-id="62ffc-113">Value</span></span>|<span data-ttu-id="62ffc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="62ffc-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="62ffc-115">La identidad de Windows no fluye por puntos asincrónicos, a menos que la suplantación se realice a través de métodos administrados como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> .</span><span class="sxs-lookup"><span data-stu-id="62ffc-115">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="62ffc-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="62ffc-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="62ffc-117">La identidad de Windows siempre fluye por puntos asincrónicos, independientemente de cómo se haya realizado la suplantación.</span><span class="sxs-lookup"><span data-stu-id="62ffc-117">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62ffc-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="62ffc-118">Child Elements</span></span>  
 <span data-ttu-id="62ffc-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="62ffc-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62ffc-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62ffc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="62ffc-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="62ffc-121">Element</span></span>|<span data-ttu-id="62ffc-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="62ffc-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="62ffc-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62ffc-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="62ffc-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="62ffc-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62ffc-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62ffc-125">Remarks</span></span>  
 <span data-ttu-id="62ffc-126">En las versiones 1,0 y 1,1 de .NET Framework, la identidad de Windows no fluye a través de los puntos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="62ffc-126">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="62ffc-127">En la versión .NET Framework 2,0, hay un <xref:System.Threading.ExecutionContext> objeto que contiene información sobre el subproceso que se está ejecutando actualmente y lo transmite por puntos asincrónicos dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="62ffc-127">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="62ffc-128"><xref:System.Security.Principal.WindowsIdentity>También fluye como parte de la información que fluye a través de los puntos asincrónicos, siempre que la suplantación se logra utilizando métodos administrados como <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> y no a través de otros medios, como la invocación de plataforma a métodos nativos.</span><span class="sxs-lookup"><span data-stu-id="62ffc-128">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="62ffc-129">Este elemento se usa para especificar que la identidad de Windows se transmite por puntos asincrónicos, independientemente de cómo se haya conseguido la suplantación.</span><span class="sxs-lookup"><span data-stu-id="62ffc-129">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="62ffc-130">Puede modificar este comportamiento predeterminado de otras dos maneras:</span><span class="sxs-lookup"><span data-stu-id="62ffc-130">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="62ffc-131">En código administrado para cada subproceso.</span><span class="sxs-lookup"><span data-stu-id="62ffc-131">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="62ffc-132">Puede suprimir el flujo por subproceso modificando la configuración de y mediante <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> el <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType> <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> método, o <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="62ffc-132">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="62ffc-133">En la llamada a la interfaz de hospedaje no administrada para cargar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="62ffc-133">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="62ffc-134">Si se usa una interfaz de hospedaje no administrada (en lugar de un ejecutable administrado simple) para cargar CLR, puede especificar una marca especial en la llamada a la función de [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) .</span><span class="sxs-lookup"><span data-stu-id="62ffc-134">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="62ffc-135">Para habilitar el modo de compatibilidad para todo el proceso, establezca el `flags` parámetro de la [función CorBindToRuntimeEx](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) en `STARTUP_ALWAYSFLOW_IMPERSONATION` .</span><span class="sxs-lookup"><span data-stu-id="62ffc-135">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="62ffc-136">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="62ffc-136">Configuration File</span></span>  
 <span data-ttu-id="62ffc-137">En una aplicación .NET Framework, este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="62ffc-137">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="62ffc-138">En el caso de una aplicación de ASP.NET, el flujo de suplantación se puede configurar en el archivo Aspnet. config que se encuentra en el \<Windows Folder> directorio \Microsoft.NET\Framework\vx.x.xxxx</span><span class="sxs-lookup"><span data-stu-id="62ffc-138">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="62ffc-139">De forma predeterminada, ASP.NET deshabilita el flujo de suplantación en el archivo Aspnet. config con las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="62ffc-139">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="62ffc-140">En ASP.NET, si desea permitir el flujo de suplantación en su lugar, debe usar explícitamente las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="62ffc-140">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="62ffc-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62ffc-141">Example</span></span>  
 <span data-ttu-id="62ffc-142">En el ejemplo siguiente se muestra cómo especificar que la identidad de Windows fluye a través de puntos asincrónicos, incluso cuando la suplantación se logra a través de medios distintos de los métodos administrados.</span><span class="sxs-lookup"><span data-stu-id="62ffc-142">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62ffc-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62ffc-143">See also</span></span>

- [<span data-ttu-id="62ffc-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="62ffc-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="62ffc-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="62ffc-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="62ffc-146">\<legacyImpersonationPolicy>Element</span><span class="sxs-lookup"><span data-stu-id="62ffc-146">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
