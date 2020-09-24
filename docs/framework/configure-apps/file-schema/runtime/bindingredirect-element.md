---
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
ms.openlocfilehash: 7667f78d2c341990585526fd153c0b230658a2ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167254"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="e4fa5-102">\<bindingRedirect> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="e4fa5-102">\<bindingRedirect> Element</span></span>

<span data-ttu-id="e4fa5-103">Redirige una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-103">Redirects one assembly version to another.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**  
  
## <a name="syntax"></a><span data-ttu-id="e4fa5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4fa5-104">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4fa5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4fa5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e4fa5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4fa5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4fa5-107">Attributes</span></span>  
  
|<span data-ttu-id="e4fa5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e4fa5-108">Attribute</span></span>|<span data-ttu-id="e4fa5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4fa5-109">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="e4fa5-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e4fa5-111">Especifica la versión del ensamblado solicitada originalmente.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-111">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="e4fa5-112">El formato de un número de versión de ensamblado es *principal. secundaria. compilación. revisión*.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-112">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="e4fa5-113">Los valores válidos para cada una de las partes de este número de versión van del 0 al 65535.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-113">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="e4fa5-114">También se puede especificar un intervalo de versiones con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="e4fa5-114">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="e4fa5-115">*n. n. n. n-n. n*</span><span class="sxs-lookup"><span data-stu-id="e4fa5-115">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="e4fa5-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e4fa5-117">Especifica la versión del ensamblado que se va a usar en lugar de la versión solicitada originalmente en el formato: *n* . n. n</span><span class="sxs-lookup"><span data-stu-id="e4fa5-117">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="e4fa5-118">Este valor puede especificar una versión anterior a `oldVersion`.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-118">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4fa5-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4fa5-119">Child Elements</span></span>  
  
|<span data-ttu-id="e4fa5-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4fa5-120">Element</span></span>|<span data-ttu-id="e4fa5-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4fa5-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4fa5-122">None</span><span class="sxs-lookup"><span data-stu-id="e4fa5-122">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="e4fa5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4fa5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e4fa5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4fa5-124">Element</span></span>|<span data-ttu-id="e4fa5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4fa5-125">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="e4fa5-126">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-126">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="e4fa5-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="e4fa5-128">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-128">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="e4fa5-129">Use un elemento dependentAssembly para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-129">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="e4fa5-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4fa5-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e4fa5-131">Remarks</span></span>  

 <span data-ttu-id="e4fa5-132">Al compilar una aplicación .NET Framework en un ensamblado con nombre seguro, la aplicación usa esa versión del ensamblado en tiempo de ejecución de forma predeterminada, aunque haya disponible otra versión posterior.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-132">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="e4fa5-133">No obstante, la aplicación puede configurarse para ejecutarla en una versión más reciente del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-133">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="e4fa5-134">Para obtener información detallada sobre cómo el motor en tiempo de ejecución usa estos archivos para determinar qué versión de ensamblado se va a usar, vea [cómo el motor en tiempo de ejecución ubica ensamblados](../../../deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="e4fa5-134">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="e4fa5-135">Se puede redirigir más de una versión de ensamblado con la inclusión de varios elementos `bindingRedirect` en un elemento `dependentAssembly`.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-135">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="e4fa5-136">También puede redirigirse de una versión más reciente a una versión anterior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-136">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="e4fa5-137">Para realizar una redirección de enlaces de ensamblado de forma explícita en un archivo de configuración, se precisa permiso de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-137">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="e4fa5-138">Esto se aplica a la redirección de los ensamblados de .NET Framework y de los ensamblados de otros proveedores.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-138">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="e4fa5-139">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="e4fa5-139">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="e4fa5-140">Para obtener más información, vea [permisos de seguridad de redirección de enlace de ensamblados](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="e4fa5-140">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4fa5-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e4fa5-141">Example</span></span>  

 <span data-ttu-id="e4fa5-142">En el ejemplo siguiente se muestra cómo redirigir una versión de ensamblado a otra versión.</span><span class="sxs-lookup"><span data-stu-id="e4fa5-142">The following example shows how to redirect one assembly version to another.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e4fa5-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4fa5-143">See also</span></span>

- [<span data-ttu-id="e4fa5-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="e4fa5-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e4fa5-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e4fa5-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e4fa5-146">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="e4fa5-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
