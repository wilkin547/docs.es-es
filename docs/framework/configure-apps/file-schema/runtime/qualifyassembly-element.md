---
title: <qualifyAssembly> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 17cfe9fc39d65f146beef5d02c701f5e3e2fbbe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115785"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="3bd44-102">\<elemento > qualifyAssembly</span><span class="sxs-lookup"><span data-stu-id="3bd44-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="3bd44-103">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="3bd44-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="3bd44-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3bd44-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3bd44-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3bd44-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3bd44-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="3bd44-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="3bd44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly >**</span><span class="sxs-lookup"><span data-stu-id="3bd44-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd44-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bd44-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bd44-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3bd44-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3bd44-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3bd44-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bd44-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3bd44-111">Attributes</span></span>  
  
|<span data-ttu-id="3bd44-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3bd44-112">Attribute</span></span>|<span data-ttu-id="3bd44-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bd44-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="3bd44-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3bd44-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3bd44-115">Especifica el nombre parcial del ensamblado tal y como aparece en el código.</span><span class="sxs-lookup"><span data-stu-id="3bd44-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="3bd44-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3bd44-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="3bd44-117">Especifica el nombre completo del ensamblado tal y como aparece en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3bd44-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bd44-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3bd44-118">Child Elements</span></span>  
 <span data-ttu-id="3bd44-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3bd44-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3bd44-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3bd44-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3bd44-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3bd44-121">Element</span></span>|<span data-ttu-id="3bd44-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bd44-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="3bd44-123">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3bd44-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="3bd44-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3bd44-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3bd44-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3bd44-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bd44-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3bd44-126">Remarks</span></span>  
 <span data-ttu-id="3bd44-127">La llamada al método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> utilizando nombres de ensamblado parciales hace que el Common Language Runtime busque el ensamblado solo en el directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3bd44-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="3bd44-128">Use el elemento **\<qualifyAssembly >** en el archivo de configuración de la aplicación para proporcionar la información de ensamblado completa (nombre, versión, token de clave pública y referencia cultural) y hacer que el Common Language Runtime busque el ensamblado en la caché de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3bd44-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="3bd44-129">El atributo **FullName** debe incluir los cuatro campos de la identidad del ensamblado: nombre, versión, token de clave pública y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="3bd44-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="3bd44-130">El atributo **partialName** debe hacer referencia a un ensamblado parcialmente.</span><span class="sxs-lookup"><span data-stu-id="3bd44-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="3bd44-131">Debe especificar al menos el nombre de texto del ensamblado (el caso más común), pero también puede incluir la versión, el token de clave pública o la referencia cultural (o cualquier combinación de los cuatro, pero no los cuatro).</span><span class="sxs-lookup"><span data-stu-id="3bd44-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="3bd44-132">**PartialName** debe coincidir con el nombre especificado en la llamada.</span><span class="sxs-lookup"><span data-stu-id="3bd44-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="3bd44-133">Por ejemplo, no puede especificar `"math"` como el atributo **partialName** en el archivo de configuración y llamar a `Assembly.Load("math, Version=3.3.3.3")` en el código.</span><span class="sxs-lookup"><span data-stu-id="3bd44-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bd44-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3bd44-134">Example</span></span>  
 <span data-ttu-id="3bd44-135">En el ejemplo siguiente se convierte lógicamente la `Assembly.Load("math")` de llamada en `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="3bd44-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bd44-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bd44-136">See also</span></span>

- [<span data-ttu-id="3bd44-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3bd44-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3bd44-138">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3bd44-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="3bd44-139">[Referencias de ensamblado parciales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3bd44-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
