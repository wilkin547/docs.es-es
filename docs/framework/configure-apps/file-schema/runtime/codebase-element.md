---
description: 'Más información acerca de: <codeBase> elemento'
title: <codeBase> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: 714392444d3ee3db9126e9fe67832cb5f0bf5e3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795123"
---
# <a name="codebase-element"></a><span data-ttu-id="5de64-103">\<codeBase> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="5de64-103">\<codeBase> Element</span></span>

<span data-ttu-id="5de64-104">Especifica dónde puede encontrar un ensamblado el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5de64-104">Specifies where the common language runtime can find an assembly.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

## <a name="syntax"></a><span data-ttu-id="5de64-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5de64-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5de64-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5de64-106">Attributes and Elements</span></span>

<span data-ttu-id="5de64-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5de64-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5de64-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="5de64-108">Attributes</span></span>

|<span data-ttu-id="5de64-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="5de64-109">Attribute</span></span>|<span data-ttu-id="5de64-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="5de64-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="5de64-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5de64-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="5de64-112">Especifica la dirección URL en la que el tiempo de ejecución puede encontrar la versión especificada del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5de64-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="5de64-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5de64-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5de64-114">Especifica la versión del ensamblado al que se aplica el código base.</span><span class="sxs-lookup"><span data-stu-id="5de64-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="5de64-115">El formato de un número de versión de ensamblado es *principal. secundaria. compilación. revisión*.</span><span class="sxs-lookup"><span data-stu-id="5de64-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="5de64-116">version (atributo)</span><span class="sxs-lookup"><span data-stu-id="5de64-116">version Attribute</span></span>

|<span data-ttu-id="5de64-117">Value</span><span class="sxs-lookup"><span data-stu-id="5de64-117">Value</span></span>|<span data-ttu-id="5de64-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5de64-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="5de64-119">Los valores válidos para cada parte del número de versión son de 0 a 65535.</span><span class="sxs-lookup"><span data-stu-id="5de64-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="5de64-120">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="5de64-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5de64-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5de64-121">Child Elements</span></span>

<span data-ttu-id="5de64-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5de64-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5de64-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5de64-123">Parent Elements</span></span>

|<span data-ttu-id="5de64-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5de64-124">Element</span></span>|<span data-ttu-id="5de64-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5de64-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="5de64-126">Define una colección de proveedores de generación que se utiliza para compilar archivos de recursos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5de64-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="5de64-127">Puede tener cualquier número de proveedores de generación.</span><span class="sxs-lookup"><span data-stu-id="5de64-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="5de64-128">Configura todos los valores de compilación que usa ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5de64-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="5de64-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5de64-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="5de64-130">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5de64-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5de64-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5de64-131">Remarks</span></span>

<span data-ttu-id="5de64-132">Para que el motor en tiempo de ejecución use la **\<codeBase>** configuración de un archivo de configuración del equipo o un archivo de directiva de edición, el archivo también debe redirigir la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5de64-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="5de64-133">Los archivos de configuración de la aplicación pueden tener una configuración de código base sin redirigir la versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5de64-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="5de64-134">Después de determinar la versión de ensamblado que se va a usar, el tiempo de ejecución aplica la configuración de código base del archivo que determina la versión.</span><span class="sxs-lookup"><span data-stu-id="5de64-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="5de64-135">Si no se indica ningún código base, el tiempo de ejecución sondea el ensamblado de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="5de64-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="5de64-136">Si el ensamblado tiene un nombre seguro, la configuración de código base puede estar en cualquier parte de la Intranet local o Internet.</span><span class="sxs-lookup"><span data-stu-id="5de64-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="5de64-137">Si el ensamblado es un ensamblado privado, la configuración de código base debe ser una ruta de acceso relativa al directorio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5de64-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="5de64-138">En el caso de los ensamblados sin un nombre seguro, se omite la versión y el cargador usa la primera aparición de \<codebase> dentro de \<dependentAssembly> .</span><span class="sxs-lookup"><span data-stu-id="5de64-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="5de64-139">Si hay una entrada en el archivo de configuración de la aplicación que redirige el enlace a otro ensamblado, la redirección tendrá prioridad aunque la versión del ensamblado no coincida con la solicitud de enlace.</span><span class="sxs-lookup"><span data-stu-id="5de64-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="5de64-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5de64-140">Example</span></span>

<span data-ttu-id="5de64-141">En el ejemplo siguiente se muestra cómo especificar dónde puede encontrar un ensamblado el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5de64-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5de64-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="5de64-142">See also</span></span>

- [<span data-ttu-id="5de64-143">Esquema de configuración en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5de64-143">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="5de64-144">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5de64-144">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="5de64-145">Especificar la ubicación de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="5de64-145">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="5de64-146">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="5de64-146">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
