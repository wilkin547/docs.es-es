---
title: <disableFusionUpdatesFromADManager> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: c3971379b358ae16fc463df2b8d6288cf8881391
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205040"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="35657-102">\<disableFusionUpdatesFromADManager> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="35657-102">\<disableFusionUpdatesFromADManager> Element</span></span>

<span data-ttu-id="35657-103">Especifica si el comportamiento predeterminado, que consiste en permitir el host en tiempo de ejecución para invalidar los valores de configuración de un dominio de aplicación, está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="35657-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a><span data-ttu-id="35657-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35657-104">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35657-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35657-105">Attributes and Elements</span></span>  

 <span data-ttu-id="35657-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="35657-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35657-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="35657-107">Attributes</span></span>  
  
|<span data-ttu-id="35657-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="35657-108">Attribute</span></span>|<span data-ttu-id="35657-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="35657-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35657-110">enabled</span><span class="sxs-lookup"><span data-stu-id="35657-110">enabled</span></span>|<span data-ttu-id="35657-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="35657-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="35657-112">Especifica si está deshabilitada la capacidad predeterminada de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="35657-112">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="35657-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="35657-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="35657-114">Value</span><span class="sxs-lookup"><span data-stu-id="35657-114">Value</span></span>|<span data-ttu-id="35657-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="35657-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="35657-116">0</span><span class="sxs-lookup"><span data-stu-id="35657-116">0</span></span>|<span data-ttu-id="35657-117">No deshabilite la capacidad de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="35657-117">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="35657-118">Este es el comportamiento predeterminado, comenzando por el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="35657-118">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="35657-119">1</span><span class="sxs-lookup"><span data-stu-id="35657-119">1</span></span>|<span data-ttu-id="35657-120">Deshabilitar la capacidad de invalidar la configuración de fusión.</span><span class="sxs-lookup"><span data-stu-id="35657-120">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="35657-121">Esto revierte el comportamiento de las versiones anteriores del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35657-121">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35657-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35657-122">Child Elements</span></span>  

 <span data-ttu-id="35657-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="35657-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35657-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35657-124">Parent Elements</span></span>  
  
|<span data-ttu-id="35657-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="35657-125">Element</span></span>|<span data-ttu-id="35657-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="35657-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35657-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35657-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="35657-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="35657-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35657-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35657-129">Remarks</span></span>  

 <span data-ttu-id="35657-130">A partir de la .NET Framework 4, el comportamiento predeterminado es permitir que el <xref:System.AppDomainManager> objeto invalide los valores de configuración mediante la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad o el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método del <xref:System.AppDomainSetup> objeto que se pasa a la implementación del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método, en la subclase de <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="35657-130">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="35657-131">En el caso del dominio de aplicación predeterminado, la configuración que cambie invalida la configuración especificada por el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35657-131">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="35657-132">En otros dominios de aplicación, invalidan las opciones de configuración que se pasaron al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método o.</span><span class="sxs-lookup"><span data-stu-id="35657-132">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="35657-133">Puede pasar información de configuración nueva o pasar un valor null ( `Nothing` en Visual Basic) para eliminar la información de configuración que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="35657-133">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="35657-134">No pase información de configuración a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad y al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método.</span><span class="sxs-lookup"><span data-stu-id="35657-134">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="35657-135">Si se pasa información de configuración a ambos, se omite la información que se pasa a la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad, porque el <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método reemplaza la información de configuración del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35657-135">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="35657-136">Si usa la <xref:System.AppDomainSetup.ConfigurationFile%2A> propiedad, puede pasar null ( `Nothing` en Visual Basic) al <xref:System.AppDomainSetup.SetConfigurationBytes%2A> método para eliminar los bytes de configuración especificados en la llamada al <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> método o.</span><span class="sxs-lookup"><span data-stu-id="35657-136">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="35657-137">Además de la información de configuración, puede cambiar la configuración siguiente en el <xref:System.AppDomainSetup> objeto que se pasa a la implementación del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método: <xref:System.AppDomainSetup.ApplicationBase%2A> , <xref:System.AppDomainSetup.ApplicationName%2A> , <xref:System.AppDomainSetup.CachePath%2A> , <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> , <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A> , <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> , <xref:System.AppDomainSetup.DynamicBase%2A> , <xref:System.AppDomainSetup.LoaderOptimization%2A> , <xref:System.AppDomainSetup.PrivateBinPath%2A> , <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> , <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> y <xref:System.AppDomainSetup.ShadowCopyFiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="35657-137">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="35657-138">Como alternativa al uso del `<disableFusionUpdatesFromADManager>` elemento, puede deshabilitar el comportamiento predeterminado mediante la creación de una configuración del registro o mediante el establecimiento de una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="35657-138">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="35657-139">En el registro, cree un valor DWORD denominado `COMPLUS_disableFusionUpdatesFromADManager` en `HKCU\Software\Microsoft\.NETFramework` o `HKLM\Software\Microsoft\.NETFramework` y establezca el valor en 1.</span><span class="sxs-lookup"><span data-stu-id="35657-139">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="35657-140">En la línea de comandos, establezca la variable de entorno `COMPLUS_disableFusionUpdatesFromADManager` en 1.</span><span class="sxs-lookup"><span data-stu-id="35657-140">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35657-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35657-141">Example</span></span>  

 <span data-ttu-id="35657-142">En el ejemplo siguiente se muestra cómo deshabilitar la capacidad de invalidar la configuración de fusión mediante el `<disableFusionUpdatesFromADManager>` elemento.</span><span class="sxs-lookup"><span data-stu-id="35657-142">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35657-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="35657-143">See also</span></span>

- [<span data-ttu-id="35657-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="35657-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="35657-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="35657-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="35657-146">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="35657-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
