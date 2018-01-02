---
title: '&lt;codeBase&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 272a4262295b5dd67414dd0ef6523f90b2125836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="bb453-102">&lt;codeBase&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="bb453-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="bb453-103">Especifica que common language runtime puede encontrar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb453-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="bb453-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb453-104">\<configuration></span></span>  
<span data-ttu-id="bb453-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="bb453-105">\<runtime></span></span>  
<span data-ttu-id="bb453-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="bb453-106">\<assemblyBinding></span></span>  
<span data-ttu-id="bb453-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="bb453-107">\<dependentAssembly></span></span>  
<span data-ttu-id="bb453-108">\<codeBase ></span><span class="sxs-lookup"><span data-stu-id="bb453-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb453-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb453-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb453-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bb453-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bb453-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bb453-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb453-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bb453-112">Attributes</span></span>  
  
|<span data-ttu-id="bb453-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="bb453-113">Attribute</span></span>|<span data-ttu-id="bb453-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb453-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="bb453-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bb453-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb453-116">Especifica la dirección URL donde encuentre el runtime la versión especificada del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb453-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="bb453-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="bb453-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb453-118">Especifica la versión del ensamblado al que se aplica el código base.</span><span class="sxs-lookup"><span data-stu-id="bb453-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="bb453-119">El formato de un número de versión de ensamblado es *principal.secundaria.compilación.revisión*.</span><span class="sxs-lookup"><span data-stu-id="bb453-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="bb453-120">versión del atributo</span><span class="sxs-lookup"><span data-stu-id="bb453-120">version Attribute</span></span>  
  
|<span data-ttu-id="bb453-121">Valor</span><span class="sxs-lookup"><span data-stu-id="bb453-121">Value</span></span>|<span data-ttu-id="bb453-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb453-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb453-123">Los valores válidos para cada parte del número de versión van del 0 al 65535.</span><span class="sxs-lookup"><span data-stu-id="bb453-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="bb453-124">No es aplicable.</span><span class="sxs-lookup"><span data-stu-id="bb453-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb453-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bb453-125">Child Elements</span></span>  
 <span data-ttu-id="bb453-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bb453-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb453-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bb453-127">Parent Elements</span></span>  
  
|<span data-ttu-id="bb453-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="bb453-128">Element</span></span>|<span data-ttu-id="bb453-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb453-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="bb453-130">Define una colección de proveedores de generación que se utiliza para compilar archivos de recursos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb453-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="bb453-131">Puede tener cualquier número de proveedores de generación.</span><span class="sxs-lookup"><span data-stu-id="bb453-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="bb453-132">Configura todas las opciones de compilación que utiliza ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bb453-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="bb453-133">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb453-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="bb453-134">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="bb453-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb453-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb453-135">Remarks</span></span>  
 <span data-ttu-id="bb453-136">En tiempo de ejecución usar el  **\<codeBase >** establecer en un archivo de configuración del equipo o el archivo de directiva de edición, el archivo también debe redirigir la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb453-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="bb453-137">Archivos de configuración de la aplicación pueden tener un valor de código base sin redirigir la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb453-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="bb453-138">Después de determinar qué versión del ensamblado, el tiempo de ejecución aplica la configuración de código base del archivo que determina la versión.</span><span class="sxs-lookup"><span data-stu-id="bb453-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="bb453-139">Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="bb453-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="bb453-140">Si el ensamblado tiene un nombre seguro, la configuración de código base puede ser en cualquier parte en la intranet local o Internet.</span><span class="sxs-lookup"><span data-stu-id="bb453-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="bb453-141">Si el ensamblado es un ensamblado privado, la configuración de código base debe ser una ruta de acceso relativa al directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb453-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="bb453-142">Para los ensamblados sin un nombre seguro, se ignora la versión y el cargador usa la primera aparición de \<codebase > dentro de \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="bb453-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="bb453-143">Si hay una entrada en el archivo de configuración de aplicación que redirija el enlace a otro ensamblado, la redirección tendrá prioridad incluso si la versión del ensamblado no coincide con la solicitud de enlace.</span><span class="sxs-lookup"><span data-stu-id="bb453-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb453-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bb453-144">Example</span></span>  
 <span data-ttu-id="bb453-145">En el ejemplo siguiente se muestra cómo especificar dónde encuentre el runtime un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb453-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb453-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb453-146">See Also</span></span>  
 [<span data-ttu-id="bb453-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="bb453-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="bb453-148">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="bb453-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="bb453-149">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="bb453-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="bb453-150">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="bb453-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
