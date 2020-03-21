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
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153924"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="3dd66-102">\<qualifyAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="3dd66-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="3dd66-103">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="3dd66-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="3dd66-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3dd66-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3dd66-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="3dd66-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3dd66-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="3dd66-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="3dd66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span><span class="sxs-lookup"><span data-stu-id="3dd66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dd66-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dd66-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dd66-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3dd66-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3dd66-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3dd66-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dd66-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3dd66-111">Attributes</span></span>  
  
|<span data-ttu-id="3dd66-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3dd66-112">Attribute</span></span>|<span data-ttu-id="3dd66-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dd66-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="3dd66-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3dd66-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3dd66-115">Especifica el nombre parcial del ensamblado tal como aparece en el código.</span><span class="sxs-lookup"><span data-stu-id="3dd66-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="3dd66-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3dd66-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="3dd66-117">Especifica el nombre completo del ensamblado tal como aparece en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3dd66-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dd66-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3dd66-118">Child Elements</span></span>  
 <span data-ttu-id="3dd66-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3dd66-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dd66-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3dd66-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3dd66-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dd66-121">Element</span></span>|<span data-ttu-id="3dd66-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dd66-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="3dd66-123">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3dd66-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="3dd66-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3dd66-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3dd66-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3dd66-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dd66-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3dd66-126">Remarks</span></span>  
 <span data-ttu-id="3dd66-127">Llamar <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> al método mediante nombres de ensamblado parciales hace que Common Language Runtime busque el ensamblado solo en el directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3dd66-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="3dd66-128">Use \*\* \<\*\* el elemento>qualifyAssembly del archivo de configuración de la aplicación para proporcionar la información completa del ensamblado (nombre, versión, token de clave pública y referencia cultural) y hacer que Common Language Runtime busque el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3dd66-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="3dd66-129">El atributo **fullName** debe incluir los cuatro campos de identidad de ensamblado: nombre, versión, token de clave pública y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="3dd66-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="3dd66-130">El atributo **partialName** debe hacer referencia parcialmente a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3dd66-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="3dd66-131">Debe especificar al menos el nombre de texto del ensamblado (el caso más común), pero también puede incluir la versión, el token de clave pública o la referencia cultural (o cualquier combinación de los cuatro, pero no los cuatro).</span><span class="sxs-lookup"><span data-stu-id="3dd66-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="3dd66-132">El **partialName** debe coincidir con el nombre especificado en la llamada.</span><span class="sxs-lookup"><span data-stu-id="3dd66-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="3dd66-133">Por ejemplo, no `"math"` puede especificar como el atributo `Assembly.Load("math, Version=3.3.3.3")` **partialName** en el archivo de configuración y llamar al código.</span><span class="sxs-lookup"><span data-stu-id="3dd66-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dd66-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dd66-134">Example</span></span>  
 <span data-ttu-id="3dd66-135">En el ejemplo siguiente `Assembly.Load("math")` se `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`convierte lógicamente la llamada en .</span><span class="sxs-lookup"><span data-stu-id="3dd66-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3dd66-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dd66-136">See also</span></span>

- [<span data-ttu-id="3dd66-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3dd66-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3dd66-138">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3dd66-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="3dd66-139">[Referencias parciales a ensamblados](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3dd66-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
