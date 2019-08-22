---
title: <disableFusionUpdatesFromADManager> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1923e70143ea2a158447eccdb35d347fe4f51ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663770"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="1df78-102">\<disableFusionUpdatesFromADManager >, elemento</span><span class="sxs-lookup"><span data-stu-id="1df78-102">\<disableFusionUpdatesFromADManager> Element</span></span>
<span data-ttu-id="1df78-103">Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1df78-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="1df78-104">\<Elemento Configuration ></span><span class="sxs-lookup"><span data-stu-id="1df78-104">\<configuration> Element</span></span>  
<span data-ttu-id="1df78-105">\<Elemento > en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1df78-105">\<runtime> Element</span></span>  
<span data-ttu-id="1df78-106">\<disableFusionUpdatesFromADManager></span><span class="sxs-lookup"><span data-stu-id="1df78-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1df78-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1df78-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1df78-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1df78-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1df78-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1df78-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1df78-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1df78-110">Attributes</span></span>  
  
|<span data-ttu-id="1df78-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1df78-111">Attribute</span></span>|<span data-ttu-id="1df78-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1df78-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1df78-113">enabled</span><span class="sxs-lookup"><span data-stu-id="1df78-113">enabled</span></span>|<span data-ttu-id="1df78-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1df78-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="1df78-115">Especifica si está deshabilitada la capacidad predeterminada de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="1df78-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1df78-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="1df78-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="1df78-117">Valor</span><span class="sxs-lookup"><span data-stu-id="1df78-117">Value</span></span>|<span data-ttu-id="1df78-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1df78-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1df78-119">0</span><span class="sxs-lookup"><span data-stu-id="1df78-119">0</span></span>|<span data-ttu-id="1df78-120">No deshabilite la capacidad de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="1df78-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="1df78-121">Este es el comportamiento predeterminado, comenzando por el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="1df78-121">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="1df78-122">1</span><span class="sxs-lookup"><span data-stu-id="1df78-122">1</span></span>|<span data-ttu-id="1df78-123">Deshabilitar la capacidad de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="1df78-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="1df78-124">Esto revierte el comportamiento de las versiones anteriores del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1df78-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1df78-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1df78-125">Child Elements</span></span>  
 <span data-ttu-id="1df78-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1df78-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1df78-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1df78-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1df78-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1df78-128">Element</span></span>|<span data-ttu-id="1df78-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1df78-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1df78-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1df78-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1df78-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1df78-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1df78-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1df78-132">Remarks</span></span>  
 <span data-ttu-id="1df78-133">A partir de la .NET Framework 4, el comportamiento predeterminado es permitir que <xref:System.AppDomainManager> el objeto invalide los valores de <xref:System.AppDomainSetup.ConfigurationFile%2A> configuración mediante la <xref:System.AppDomainSetup.SetConfigurationBytes%2A> propiedad <xref:System.AppDomainSetup> o el método del objeto que se pasa a la implementación. del método, en la subclase de <xref:System.AppDomainManager>. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1df78-133">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="1df78-134">En el caso del dominio de aplicación predeterminado, la configuración que cambie invalida la configuración especificada por el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1df78-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="1df78-135">En otros dominios de aplicación, invalidan las opciones de configuración que se <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> pasaron <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> al método o.</span><span class="sxs-lookup"><span data-stu-id="1df78-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="1df78-136">Puede pasar información de configuración nueva o pasar un valor null (`Nothing` en Visual Basic) para eliminar la información de configuración que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="1df78-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="1df78-137">No pase información de configuración a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad y al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1df78-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="1df78-138">Si se pasa información de configuración a ambos, se omite la información que <xref:System.AppDomainSetup.ConfigurationFile%2A> se pasa a la propiedad, <xref:System.AppDomainSetup.SetConfigurationBytes%2A> porque el método reemplaza la información de configuración del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1df78-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="1df78-139"><xref:System.AppDomainSetup.ConfigurationFile%2A> Si usa la propiedad, puede pasar null ( <xref:System.AppDomainSetup.SetConfigurationBytes%2A> `Nothing` en Visual Basic) al método para eliminar los bytes de configuración especificados en la llamada al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> método o <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1df78-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="1df78-140">Además de la información de configuración, puede cambiar la configuración siguiente en el <xref:System.AppDomainSetup> objeto que se pasa a la implementación <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> del método: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>,, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, y<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A></span><span class="sxs-lookup"><span data-stu-id="1df78-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="1df78-141">Como alternativa al uso del elemento `<disableFusionUpdatesFromADManager>` , puede deshabilitar el comportamiento predeterminado mediante la creación de una configuración del registro o mediante el establecimiento de una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="1df78-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="1df78-142">En el registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` en `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework`y establezca el valor en 1.</span><span class="sxs-lookup"><span data-stu-id="1df78-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="1df78-143">En la línea de comandos, establezca la variable `COMPLUS_disableFusionUpdatesFromADManager` de entorno en 1.</span><span class="sxs-lookup"><span data-stu-id="1df78-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1df78-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1df78-144">Example</span></span>  
 <span data-ttu-id="1df78-145">En el ejemplo siguiente se muestra cómo deshabilitar la capacidad de invalidar la configuración `<disableFusionUpdatesFromADManager>` de fusión mediante el elemento.</span><span class="sxs-lookup"><span data-stu-id="1df78-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1df78-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="1df78-146">See also</span></span>

- [<span data-ttu-id="1df78-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1df78-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1df78-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1df78-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1df78-149">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="1df78-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
