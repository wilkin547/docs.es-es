---
title: <disableCachingBindingFailures> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c2ed46e1d26d829fbe832e44efb40844ae7d56f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592720"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="2f90e-102">\<disableCachingBindingFailures > elemento</span><span class="sxs-lookup"><span data-stu-id="2f90e-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="2f90e-103">Especifica si se deshabilita el almacenamiento en caché de errores que se producen porque no se encontró el ensamblado mediante sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2f90e-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="2f90e-104">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="2f90e-104">\<configuration> Element</span></span>  
<span data-ttu-id="2f90e-105">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="2f90e-105">\<runtime> Element</span></span>  
<span data-ttu-id="2f90e-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="2f90e-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f90e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f90e-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f90e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f90e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2f90e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f90e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f90e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f90e-110">Attributes</span></span>  
  
|<span data-ttu-id="2f90e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2f90e-111">Attribute</span></span>|<span data-ttu-id="2f90e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f90e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f90e-113">enabled</span><span class="sxs-lookup"><span data-stu-id="2f90e-113">enabled</span></span>|<span data-ttu-id="2f90e-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2f90e-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="2f90e-115">Especifica si se deshabilita el almacenamiento en caché de errores que se producen porque no se encontró el ensamblado mediante sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2f90e-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2f90e-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="2f90e-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="2f90e-117">Valor</span><span class="sxs-lookup"><span data-stu-id="2f90e-117">Value</span></span>|<span data-ttu-id="2f90e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f90e-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f90e-119">0</span><span class="sxs-lookup"><span data-stu-id="2f90e-119">0</span></span>|<span data-ttu-id="2f90e-120">No deshabilite el almacenamiento en caché de errores que se producen porque no se encontró el ensamblado mediante sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2f90e-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="2f90e-121">Este es el comportamiento de enlace predeterminada a partir de la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f90e-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="2f90e-122">1</span><span class="sxs-lookup"><span data-stu-id="2f90e-122">1</span></span>|<span data-ttu-id="2f90e-123">Deshabilitar el almacenamiento en caché de errores que se producen porque no se encontró el ensamblado mediante sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2f90e-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="2f90e-124">Esta opción revierte el comportamiento de enlace de la versión 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f90e-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f90e-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f90e-125">Child Elements</span></span>  
 <span data-ttu-id="2f90e-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f90e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f90e-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f90e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="2f90e-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f90e-128">Element</span></span>|<span data-ttu-id="2f90e-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f90e-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2f90e-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2f90e-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2f90e-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2f90e-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f90e-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f90e-132">Remarks</span></span>  
 <span data-ttu-id="2f90e-133">A partir de la versión 2.0 de .NET Framework, el comportamiento predeterminado para la carga de ensamblados es almacenar en caché todos los enlaces y errores de carga.</span><span class="sxs-lookup"><span data-stu-id="2f90e-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="2f90e-134">Es decir, si se produce un error en un intento de cargar un ensamblado, las solicitudes posteriores para cargar el mismo ensamblado producirá un error inmediatamente, sin intentar localizar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2f90e-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="2f90e-135">Este elemento deshabilita ese comportamiento predeterminado para los errores que se producen porque no se encontró el ensamblado en la ruta de acceso de sondeo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2f90e-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="2f90e-136">Producen estos errores <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="2f90e-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="2f90e-137">Algunos enlaces de errores de carga no se ven afectados por este elemento y siempre se almacenan en caché.</span><span class="sxs-lookup"><span data-stu-id="2f90e-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="2f90e-138">Estos errores se producen porque se encontró el ensamblado, pero no se pudo cargar.</span><span class="sxs-lookup"><span data-stu-id="2f90e-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="2f90e-139">Producen <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="2f90e-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="2f90e-140">En la lista siguiente incluye algunos ejemplos de tales errores.</span><span class="sxs-lookup"><span data-stu-id="2f90e-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="2f90e-141">Si intenta cargar un archivo no es un ensamblado válido, se producirá un error en los intentos posteriores para cargar el ensamblado incluso si se reemplaza el archivo incorrecto con el ensamblado correcto.</span><span class="sxs-lookup"><span data-stu-id="2f90e-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="2f90e-142">Si intenta cargar un ensamblado que está bloqueado por el sistema de archivos, se producirá un error en los intentos posteriores para cargar el ensamblado incluso después de que el ensamblado se libera por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="2f90e-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="2f90e-143">Si una o varias versiones del ensamblado que está intentando cargar es en la ruta de acceso de sondeo, pero la versión específica que solicita no está entre ellos, se producirá un error en los intentos posteriores para cargar esa versión incluso si se mueve la versión correcta en la ruta de acceso de sondeo.</span><span class="sxs-lookup"><span data-stu-id="2f90e-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f90e-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f90e-144">Example</span></span>  
 <span data-ttu-id="2f90e-145">El ejemplo siguiente muestra cómo deshabilitar el almacenamiento en caché de errores de enlace de ensamblado que se producen porque no se encontró el ensamblado mediante sondeo.</span><span class="sxs-lookup"><span data-stu-id="2f90e-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f90e-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f90e-146">See also</span></span>

- [<span data-ttu-id="2f90e-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="2f90e-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="2f90e-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2f90e-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="2f90e-149">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="2f90e-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
