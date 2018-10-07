---
title: '&lt;bindingRedirect&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 535519c65aba7ce13703bb33a16b09cde84c3f03
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836438"
---
# <a name="ltbindingredirectgt-element"></a><span data-ttu-id="5b376-102">&lt;bindingRedirect&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="5b376-102">&lt;bindingRedirect&gt; Element</span></span>
<span data-ttu-id="5b376-103">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="5b376-103">Redirects one assembly version to another.</span></span>  
  
 <span data-ttu-id="5b376-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5b376-104">\<configuration></span></span>  
<span data-ttu-id="5b376-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="5b376-105">\<runtime></span></span>  
<span data-ttu-id="5b376-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="5b376-106">\<assemblyBinding></span></span>  
<span data-ttu-id="5b376-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="5b376-107">\<dependentAssembly></span></span>  
<span data-ttu-id="5b376-108">\<bindingRedirect ></span><span class="sxs-lookup"><span data-stu-id="5b376-108">\<bindingRedirect></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b376-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b376-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b376-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b376-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5b376-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b376-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b376-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b376-112">Attributes</span></span>  
  
|<span data-ttu-id="5b376-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b376-113">Attribute</span></span>|<span data-ttu-id="5b376-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b376-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="5b376-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5b376-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="5b376-116">Especifica la versión del ensamblado solicitada originalmente.</span><span class="sxs-lookup"><span data-stu-id="5b376-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="5b376-117">El formato de un número de versión del ensamblado es *principal.secundaria.compilación.revisión*.</span><span class="sxs-lookup"><span data-stu-id="5b376-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="5b376-118">Los valores válidos para cada una de las partes de este número de versión van del 0 al 65535.</span><span class="sxs-lookup"><span data-stu-id="5b376-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="5b376-119">También se puede especificar un intervalo de versiones con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="5b376-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="5b376-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="5b376-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="5b376-121">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5b376-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="5b376-122">Especifica la versión del ensamblado que se va a usar en lugar de la versión solicitada inicialmente en el formato: *n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="5b376-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="5b376-123">Este valor puede especificar una versión anterior a `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="5b376-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b376-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b376-124">Child Elements</span></span>  
  
|<span data-ttu-id="5b376-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b376-125">Element</span></span>|<span data-ttu-id="5b376-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b376-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b376-127">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5b376-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="5b376-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b376-128">Parent Elements</span></span>  
  
|<span data-ttu-id="5b376-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b376-129">Element</span></span>|<span data-ttu-id="5b376-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b376-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="5b376-131">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5b376-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="5b376-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5b376-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="5b376-133">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b376-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="5b376-134">Use un elemento dependentAssembly para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b376-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="5b376-135">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5b376-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b376-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b376-136">Remarks</span></span>  
 <span data-ttu-id="5b376-137">Al compilar una aplicación .NET Framework en un ensamblado con nombre seguro, la aplicación usa esa versión del ensamblado en tiempo de ejecución de forma predeterminada, aunque haya disponible otra versión posterior.</span><span class="sxs-lookup"><span data-stu-id="5b376-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="5b376-138">No obstante, la aplicación puede configurarse para ejecutarla en una versión más reciente del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b376-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="5b376-139">Para obtener más información sobre cómo el runtime usa estos archivos para determinar qué versión del ensamblado, vea [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="5b376-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="5b376-140">Se puede redirigir más de una versión de ensamblado con la inclusión de varios elementos `bindingRedirect` en un elemento `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="5b376-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="5b376-141">También puede redirigirse de una versión más reciente a una versión anterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b376-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="5b376-142">Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5b376-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="5b376-143">Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="5b376-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="5b376-144">El permiso se otorga estableciendo el <xref:System.Security.Permissions.SecurityPermissionFlag> marca en el <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="5b376-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="5b376-145">Para obtener más información, consulte [permiso de seguridad de redirección de enlace de ensamblado](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="5b376-145">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b376-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b376-146">Example</span></span>  
 <span data-ttu-id="5b376-147">En el ejemplo siguiente se muestra cómo redirigir una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="5b376-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5b376-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b376-148">See Also</span></span>  
 [<span data-ttu-id="5b376-149">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="5b376-149">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="5b376-150">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5b376-150">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="5b376-151">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="5b376-151">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
