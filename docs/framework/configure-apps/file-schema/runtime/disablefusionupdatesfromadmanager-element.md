---
title: '&lt;disableFusionUpdatesFromADManager&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d3a1214b4aecf56c9a6440e31459573a5922676
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a><span data-ttu-id="957e5-102">&lt;disableFusionUpdatesFromADManager&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="957e5-102">&lt;disableFusionUpdatesFromADManager&gt; Element</span></span>
<span data-ttu-id="957e5-103">Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="957e5-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="957e5-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="957e5-104">\<configuration> Element</span></span>  
<span data-ttu-id="957e5-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="957e5-105">\<runtime> Element</span></span>  
<span data-ttu-id="957e5-106">\<disableFusionUpdatesFromADManager ></span><span class="sxs-lookup"><span data-stu-id="957e5-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="957e5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="957e5-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="957e5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="957e5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="957e5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="957e5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="957e5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="957e5-110">Attributes</span></span>  
  
|<span data-ttu-id="957e5-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="957e5-111">Attribute</span></span>|<span data-ttu-id="957e5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="957e5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="957e5-113">enabled</span><span class="sxs-lookup"><span data-stu-id="957e5-113">enabled</span></span>|<span data-ttu-id="957e5-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="957e5-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="957e5-115">Especifica si se deshabilita la capacidad predeterminada de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="957e5-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="957e5-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="957e5-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="957e5-117">Valor</span><span class="sxs-lookup"><span data-stu-id="957e5-117">Value</span></span>|<span data-ttu-id="957e5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="957e5-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="957e5-119">0</span><span class="sxs-lookup"><span data-stu-id="957e5-119">0</span></span>|<span data-ttu-id="957e5-120">Deshabilitar la capacidad de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="957e5-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="957e5-121">Éste es el comportamiento predeterminado, a partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="957e5-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="957e5-122">1</span><span class="sxs-lookup"><span data-stu-id="957e5-122">1</span></span>|<span data-ttu-id="957e5-123">Deshabilitar la capacidad de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="957e5-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="957e5-124">Esto revierte el comportamiento de versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="957e5-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="957e5-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="957e5-125">Child Elements</span></span>  
 <span data-ttu-id="957e5-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="957e5-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="957e5-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="957e5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="957e5-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="957e5-128">Element</span></span>|<span data-ttu-id="957e5-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="957e5-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="957e5-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="957e5-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="957e5-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="957e5-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="957e5-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="957e5-132">Remarks</span></span>  
 <span data-ttu-id="957e5-133">A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], el comportamiento predeterminado es permitir la <xref:System.AppDomainManager> objeto que se va a invalidar opciones de configuración mediante el uso de la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad o el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método de la <xref:System.AppDomainSetup> objeto que se pasa a la implementación de la <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método, en su subclase de <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="957e5-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="957e5-134">Para el dominio de aplicación predeterminado, la configuración que cambia invalida la configuración especificada por el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="957e5-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="957e5-135">Para otros dominios de aplicación, invalidan los valores de configuración que se pasaron a la <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="957e5-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="957e5-136">Puede pasar nueva información de configuración o pasar null (`Nothing` en Visual Basic) para eliminar la información de configuración que se pasó.</span><span class="sxs-lookup"><span data-stu-id="957e5-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="957e5-137">No pase información de configuración a ambos el <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad y el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método.</span><span class="sxs-lookup"><span data-stu-id="957e5-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="957e5-138">Si se pasa la información de configuración a ambos, la información se pasa a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad se omite porque el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método invalida la información de configuración desde el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="957e5-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="957e5-139">Si usas el <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad, se puede pasar null (`Nothing` en Visual Basic) a la <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método para eliminar los bytes de configuración que se especificaron en la llamada a la <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="957e5-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="957e5-140">Además de información de configuración, puede cambiar la configuración siguiente en el <xref:System.AppDomainSetup> objeto que se pasa a la implementación de la <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, y <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="957e5-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="957e5-141">Como alternativa al uso de la `<disableFusionUpdatesFromADManager>` elemento, puede deshabilitar el comportamiento predeterminado mediante la creación de una configuración del registro o estableciendo una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="957e5-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="957e5-142">En el registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` en `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`y establezca el valor en 1.</span><span class="sxs-lookup"><span data-stu-id="957e5-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="957e5-143">En la línea de comandos, establezca la variable de entorno `COMPLUS_disableFusionUpdatesFromADManager` en 1.</span><span class="sxs-lookup"><span data-stu-id="957e5-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="957e5-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="957e5-144">Example</span></span>  
 <span data-ttu-id="957e5-145">En el ejemplo siguiente se muestra cómo deshabilitar la capacidad de invalidar la configuración de fusión usando el `<disableFusionUpdatesFromADManager>` elemento.</span><span class="sxs-lookup"><span data-stu-id="957e5-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="957e5-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="957e5-146">See Also</span></span>  
 [<span data-ttu-id="957e5-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="957e5-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="957e5-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="957e5-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="957e5-149">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="957e5-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
