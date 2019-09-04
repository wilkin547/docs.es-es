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
ms.openlocfilehash: d5b45ea4b30677d17e72685b16c19f9192c8c144
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252677"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="3297d-102">\<disableCachingBindingFailures >, elemento</span><span class="sxs-lookup"><span data-stu-id="3297d-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="3297d-103">Especifica si se va a deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
<span data-ttu-id="3297d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3297d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3297d-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3297d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3297d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disableCachingBindingFailures>**</span><span class="sxs-lookup"><span data-stu-id="3297d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3297d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3297d-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3297d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3297d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3297d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3297d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3297d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="3297d-110">Attributes</span></span>  
  
|<span data-ttu-id="3297d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="3297d-111">Attribute</span></span>|<span data-ttu-id="3297d-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3297d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3297d-113">enabled</span><span class="sxs-lookup"><span data-stu-id="3297d-113">enabled</span></span>|<span data-ttu-id="3297d-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3297d-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3297d-115">Especifica si se va a deshabilitar el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3297d-116">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="3297d-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="3297d-117">Valor</span><span class="sxs-lookup"><span data-stu-id="3297d-117">Value</span></span>|<span data-ttu-id="3297d-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3297d-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3297d-119">0</span><span class="sxs-lookup"><span data-stu-id="3297d-119">0</span></span>|<span data-ttu-id="3297d-120">No deshabilite el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="3297d-121">Este es el comportamiento de enlace predeterminado a partir de la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="3297d-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="3297d-122">1</span><span class="sxs-lookup"><span data-stu-id="3297d-122">1</span></span>|<span data-ttu-id="3297d-123">Deshabilite el almacenamiento en caché de errores de enlace que se producen porque el sondeo no ha encontrado el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="3297d-124">Esta configuración revierte al comportamiento de enlace de la .NET Framework versión 1,1.</span><span class="sxs-lookup"><span data-stu-id="3297d-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3297d-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3297d-125">Child Elements</span></span>  
 <span data-ttu-id="3297d-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3297d-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3297d-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3297d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3297d-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="3297d-128">Element</span></span>|<span data-ttu-id="3297d-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3297d-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3297d-130">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3297d-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3297d-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3297d-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3297d-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3297d-132">Remarks</span></span>  
 <span data-ttu-id="3297d-133">A partir de la versión 2,0 de .NET Framework, el comportamiento predeterminado para cargar ensamblados es almacenar en caché todos los errores de enlace y carga.</span><span class="sxs-lookup"><span data-stu-id="3297d-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="3297d-134">Es decir, si se produce un error al intentar cargar un ensamblado, las solicitudes posteriores para cargar el mismo ensamblado producen un error inmediatamente, sin ningún intento de buscar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="3297d-135">Este elemento deshabilita el comportamiento predeterminado para los errores de enlace que se producen porque no se pudo encontrar el ensamblado en la ruta de acceso de sondeo.</span><span class="sxs-lookup"><span data-stu-id="3297d-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="3297d-136">Se producen <xref:System.IO.FileNotFoundException>estos errores.</span><span class="sxs-lookup"><span data-stu-id="3297d-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="3297d-137">Algunos errores de enlace y carga no se ven afectados por este elemento y siempre se almacenan en caché.</span><span class="sxs-lookup"><span data-stu-id="3297d-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="3297d-138">Estos errores se producen porque se encontró el ensamblado, pero no se pudo cargar.</span><span class="sxs-lookup"><span data-stu-id="3297d-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="3297d-139">Inician <xref:System.BadImageFormatException> o <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="3297d-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="3297d-140">La lista siguiente incluye algunos ejemplos de estos errores.</span><span class="sxs-lookup"><span data-stu-id="3297d-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="3297d-141">Si intenta cargar un archivo no es un ensamblado válido, se producirá un error en los intentos posteriores de cargar el ensamblado aunque el archivo incorrecto se reemplace con el ensamblado correcto.</span><span class="sxs-lookup"><span data-stu-id="3297d-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="3297d-142">Si intenta cargar un ensamblado bloqueado por el sistema de archivos, se producirá un error en los intentos posteriores de cargar el ensamblado incluso después de que el sistema de archivos libere el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="3297d-143">Si una o varias de las versiones del ensamblado que está intentando cargar se encuentran en la ruta de acceso de sondeo, pero la versión específica que está solicitando no está entre ellas, los intentos posteriores de cargar esa versión producirán un error aunque la versión correcta se mueva a la ruta de acceso de sondeo.</span><span class="sxs-lookup"><span data-stu-id="3297d-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3297d-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3297d-144">Example</span></span>  
 <span data-ttu-id="3297d-145">En el ejemplo siguiente se muestra cómo deshabilitar el almacenamiento en caché de errores de enlace de ensamblados que se producen porque el sondeo no encontró el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3297d-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3297d-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="3297d-146">See also</span></span>

- [<span data-ttu-id="3297d-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3297d-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3297d-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3297d-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3297d-149">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3297d-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
