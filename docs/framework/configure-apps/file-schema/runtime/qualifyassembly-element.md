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
ms.openlocfilehash: 26b265996a059d8e52901557603bcf5e7636e596
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195225"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="dbf82-102">\<qualifyAssembly> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="dbf82-102">\<qualifyAssembly> Element</span></span>

<span data-ttu-id="dbf82-103">Especifica el nombre completo del ensamblado que debe cargarse dinámicamente cuando se utiliza un nombre parcial.</span><span class="sxs-lookup"><span data-stu-id="dbf82-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="dbf82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbf82-104">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbf82-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dbf82-105">Attributes and Elements</span></span>  

 <span data-ttu-id="dbf82-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dbf82-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbf82-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="dbf82-107">Attributes</span></span>  
  
|<span data-ttu-id="dbf82-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="dbf82-108">Attribute</span></span>|<span data-ttu-id="dbf82-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbf82-109">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="dbf82-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="dbf82-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="dbf82-111">Especifica el nombre parcial del ensamblado tal y como aparece en el código.</span><span class="sxs-lookup"><span data-stu-id="dbf82-111">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="dbf82-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="dbf82-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="dbf82-113">Especifica el nombre completo del ensamblado tal y como aparece en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="dbf82-113">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbf82-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dbf82-114">Child Elements</span></span>  

 <span data-ttu-id="dbf82-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dbf82-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbf82-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dbf82-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dbf82-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbf82-117">Element</span></span>|<span data-ttu-id="dbf82-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbf82-118">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="dbf82-119">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="dbf82-119">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="dbf82-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbf82-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dbf82-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="dbf82-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbf82-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dbf82-122">Remarks</span></span>  

 <span data-ttu-id="dbf82-123">La llamada al <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> método utilizando nombres de ensamblado parciales hace que el Common Language Runtime busque el ensamblado solo en el directorio base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dbf82-123">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="dbf82-124">Use el **\<qualifyAssembly>** elemento en el archivo de configuración de la aplicación para proporcionar la información de ensamblado completa (nombre, versión, token de clave pública y referencia cultural) y hacer que el Common Language Runtime busque el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="dbf82-124">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="dbf82-125">El atributo **FullName** debe incluir los cuatro campos de la identidad del ensamblado: nombre, versión, token de clave pública y referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="dbf82-125">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="dbf82-126">El atributo **partialName** debe hacer referencia a un ensamblado parcialmente.</span><span class="sxs-lookup"><span data-stu-id="dbf82-126">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="dbf82-127">Debe especificar al menos el nombre de texto del ensamblado (el caso más común), pero también puede incluir la versión, el token de clave pública o la referencia cultural (o cualquier combinación de los cuatro, pero no los cuatro).</span><span class="sxs-lookup"><span data-stu-id="dbf82-127">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="dbf82-128">**PartialName** debe coincidir con el nombre especificado en la llamada.</span><span class="sxs-lookup"><span data-stu-id="dbf82-128">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="dbf82-129">Por ejemplo, no puede especificar `"math"` como el atributo **partialName** en el archivo de configuración y llamar a `Assembly.Load("math, Version=3.3.3.3")` en el código.</span><span class="sxs-lookup"><span data-stu-id="dbf82-129">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbf82-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbf82-130">Example</span></span>  

 <span data-ttu-id="dbf82-131">En el ejemplo siguiente se convierte lógicamente la llamada `Assembly.Load("math")` en `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` .</span><span class="sxs-lookup"><span data-stu-id="dbf82-131">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dbf82-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbf82-132">See also</span></span>

- [<span data-ttu-id="dbf82-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="dbf82-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dbf82-134">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="dbf82-134">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="dbf82-135">[Referencias parciales a ensamblados](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dbf82-135">[Partial Assembly References](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
