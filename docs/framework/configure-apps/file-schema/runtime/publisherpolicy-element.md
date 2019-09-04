---
title: <publisherPolicy> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252378"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="54739-102">\<publisherPolicy >, elemento</span><span class="sxs-lookup"><span data-stu-id="54739-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="54739-103">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="54739-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="54739-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="54739-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="54739-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="54739-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="54739-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> assemblyBinding**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="54739-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="54739-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de dependentAssembly**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="54739-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="54739-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> publisherPolicy**</span><span class="sxs-lookup"><span data-stu-id="54739-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54739-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54739-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54739-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="54739-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54739-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="54739-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54739-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="54739-112">Attributes</span></span>  
  
|<span data-ttu-id="54739-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="54739-113">Attribute</span></span>|<span data-ttu-id="54739-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="54739-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="54739-115">Especifica si se debe aplicar la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="54739-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="54739-116">aplicar atributo</span><span class="sxs-lookup"><span data-stu-id="54739-116">apply Attribute</span></span>  
  
|<span data-ttu-id="54739-117">Value</span><span class="sxs-lookup"><span data-stu-id="54739-117">Value</span></span>|<span data-ttu-id="54739-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="54739-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="54739-119">Aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="54739-119">Applies publisher policy.</span></span> <span data-ttu-id="54739-120">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="54739-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="54739-121">No aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="54739-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54739-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="54739-122">Child Elements</span></span>  

<span data-ttu-id="54739-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="54739-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54739-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="54739-124">Parent Elements</span></span>  
  
|<span data-ttu-id="54739-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="54739-125">Element</span></span>|<span data-ttu-id="54739-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="54739-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="54739-127">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="54739-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="54739-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="54739-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="54739-129">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="54739-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="54739-130">Use un `<dependentAssembly>` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="54739-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="54739-131">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="54739-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54739-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54739-132">Remarks</span></span>  
 <span data-ttu-id="54739-133">Cuando un proveedor de componentes publica una nueva versión de un ensamblado, el proveedor puede incluir una directiva de edición para que las aplicaciones que usan la versión anterior utilicen ahora la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="54739-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="54739-134">Para especificar si se va a aplicar la Directiva de edición para un ensamblado determinado, coloque el  **\<elemento > de publisherPolicy** en el  **\<elemento de > dependentAssembly** .</span><span class="sxs-lookup"><span data-stu-id="54739-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="54739-135">La configuración predeterminada para el atributo **aplicar** es **sí**.</span><span class="sxs-lookup"><span data-stu-id="54739-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="54739-136">Al establecer el atributo **Apply** en **no** , se reemplaza cualquier configuración anterior de **sí** para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="54739-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="54739-137">Se requiere permiso para que una aplicación ignore explícitamente la Directiva de edición mediante el [ \<elemento publisherPolicy Apply = "no"/>](publisherpolicy-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="54739-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="54739-138">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca <xref:System.Security.Permissions.SecurityPermission>en.</span><span class="sxs-lookup"><span data-stu-id="54739-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="54739-139">Para obtener más información, vea [permisos de seguridad de redirección de enlace de ensamblados](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="54739-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54739-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54739-140">Example</span></span>  
 <span data-ttu-id="54739-141">En el siguiente ejemplo se desactiva la Directiva de edición para `myAssembly`el ensamblado,.</span><span class="sxs-lookup"><span data-stu-id="54739-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54739-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="54739-142">See also</span></span>

- [<span data-ttu-id="54739-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="54739-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="54739-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="54739-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="54739-145">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="54739-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="54739-146">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="54739-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
