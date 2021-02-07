---
description: 'Más información acerca de: <bindingRedirect> elemento'
title: <bindingRedirect> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: 833ee73fa11d179ac855f3ac4d2bca8d7a2226ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719180"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="af407-103">\<bindingRedirect> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="af407-103">\<bindingRedirect> Element</span></span>

<span data-ttu-id="af407-104">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="af407-104">Redirects one assembly version to another.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**  
  
## <a name="syntax"></a><span data-ttu-id="af407-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af407-105">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af407-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af407-106">Attributes and Elements</span></span>  

 <span data-ttu-id="af407-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af407-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af407-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="af407-108">Attributes</span></span>  
  
|<span data-ttu-id="af407-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="af407-109">Attribute</span></span>|<span data-ttu-id="af407-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="af407-110">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="af407-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="af407-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="af407-112">Especifica la versión del ensamblado solicitada originalmente.</span><span class="sxs-lookup"><span data-stu-id="af407-112">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="af407-113">El formato de un número de versión de ensamblado es *principal. secundaria. compilación. revisión*.</span><span class="sxs-lookup"><span data-stu-id="af407-113">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="af407-114">Los valores válidos para cada una de las partes de este número de versión van del 0 al 65535.</span><span class="sxs-lookup"><span data-stu-id="af407-114">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="af407-115">También se puede especificar un intervalo de versiones con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="af407-115">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="af407-116">*n. n. n. n-n. n*</span><span class="sxs-lookup"><span data-stu-id="af407-116">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="af407-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="af407-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="af407-118">Especifica la versión del ensamblado que se va a usar en lugar de la versión solicitada originalmente en el formato: *n* . n. n</span><span class="sxs-lookup"><span data-stu-id="af407-118">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="af407-119">Este valor puede especificar una versión anterior a `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="af407-119">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af407-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af407-120">Child Elements</span></span>  
  
|<span data-ttu-id="af407-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="af407-121">Element</span></span>|<span data-ttu-id="af407-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="af407-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af407-123">None</span><span class="sxs-lookup"><span data-stu-id="af407-123">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="af407-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af407-124">Parent Elements</span></span>  
  
|<span data-ttu-id="af407-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="af407-125">Element</span></span>|<span data-ttu-id="af407-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="af407-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="af407-127">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="af407-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="af407-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af407-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="af407-129">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="af407-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="af407-130">Use un elemento dependentAssembly para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="af407-130">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="af407-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="af407-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af407-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af407-132">Remarks</span></span>  

 <span data-ttu-id="af407-133">Al compilar una aplicación .NET Framework en un ensamblado con nombre seguro, la aplicación usa esa versión del ensamblado en tiempo de ejecución de forma predeterminada, aunque haya disponible otra versión posterior.</span><span class="sxs-lookup"><span data-stu-id="af407-133">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="af407-134">No obstante, la aplicación puede configurarse para ejecutarla en una versión más reciente del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="af407-134">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="af407-135">Para obtener información detallada sobre cómo el motor en tiempo de ejecución usa estos archivos para determinar qué versión de ensamblado se va a usar, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="af407-135">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="af407-136">Se puede redirigir más de una versión de ensamblado con la inclusión de varios elementos `bindingRedirect` en un elemento `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="af407-136">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="af407-137">También puede redirigirse de una versión más reciente a una versión anterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="af407-137">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="af407-138">Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.</span><span class="sxs-lookup"><span data-stu-id="af407-138">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="af407-139">Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="af407-139">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="af407-140">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="af407-140">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="af407-141">Para obtener más información, vea [permisos de seguridad de redirección de enlace de ensamblados](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="af407-141">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af407-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af407-142">Example</span></span>  

 <span data-ttu-id="af407-143">En el ejemplo siguiente se muestra cómo redirigir una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="af407-143">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af407-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="af407-144">See also</span></span>

- [<span data-ttu-id="af407-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="af407-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af407-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="af407-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="af407-147">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="af407-147">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
