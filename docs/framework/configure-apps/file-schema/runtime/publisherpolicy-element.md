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
ms.openlocfilehash: 7c8f8744d3ef1ca30eb05a4c8c3290d8a514714b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663511"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="7dbd3-102">\<publisherPolicy >, elemento</span><span class="sxs-lookup"><span data-stu-id="7dbd3-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="7dbd3-103">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="7dbd3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7dbd3-104">\<configuration></span></span>  
<span data-ttu-id="7dbd3-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7dbd3-105">\<runtime></span></span>  
<span data-ttu-id="7dbd3-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="7dbd3-106">\<assemblyBinding></span></span>  
<span data-ttu-id="7dbd3-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="7dbd3-107">\<dependentAssembly></span></span>  
<span data-ttu-id="7dbd3-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="7dbd3-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dbd3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dbd3-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dbd3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7dbd3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7dbd3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dbd3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7dbd3-112">Attributes</span></span>  
  
|<span data-ttu-id="7dbd3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="7dbd3-113">Attribute</span></span>|<span data-ttu-id="7dbd3-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7dbd3-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="7dbd3-115">Especifica si se debe aplicar la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="7dbd3-116">aplicar atributo</span><span class="sxs-lookup"><span data-stu-id="7dbd3-116">apply Attribute</span></span>  
  
|<span data-ttu-id="7dbd3-117">Valor</span><span class="sxs-lookup"><span data-stu-id="7dbd3-117">Value</span></span>|<span data-ttu-id="7dbd3-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7dbd3-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="7dbd3-119">Aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-119">Applies publisher policy.</span></span> <span data-ttu-id="7dbd3-120">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="7dbd3-121">No aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dbd3-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7dbd3-122">Child Elements</span></span>  
 <span data-ttu-id="7dbd3-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dbd3-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7dbd3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7dbd3-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7dbd3-125">Element</span></span>|<span data-ttu-id="7dbd3-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7dbd3-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7dbd3-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7dbd3-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dbd3-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7dbd3-129">Remarks</span></span>  
 <span data-ttu-id="7dbd3-130">Cuando un proveedor de componentes publica una nueva versión de un ensamblado, el proveedor puede incluir una directiva de edición para que las aplicaciones que usan la versión anterior utilicen ahora la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="7dbd3-131">Para especificar si se va a aplicar la Directiva de edición para un ensamblado determinado, coloque el  **\<elemento > de publisherPolicy** en el  **\<elemento de > dependentAssembly** .</span><span class="sxs-lookup"><span data-stu-id="7dbd3-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="7dbd3-132">La configuración predeterminada para el atributo **aplicar** es **sí**.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="7dbd3-133">Al establecer el atributo **Apply** en **no** , se reemplaza cualquier configuración anterior de **sí** para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="7dbd3-134">Se requiere permiso para que una aplicación ignore explícitamente la Directiva de edición mediante el [ \<elemento publisherPolicy Apply = "no"/>](publisherpolicy-element.md) del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="7dbd3-135">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca <xref:System.Security.Permissions.SecurityPermission>en.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="7dbd3-136">Para obtener más información, vea [permisos de seguridad](../../assembly-binding-redirection-security-permission.md)de redirección de enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-136">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dbd3-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dbd3-137">Example</span></span>  
 <span data-ttu-id="7dbd3-138">En el siguiente ejemplo se desactiva la Directiva de edición para `myAssembly`el ensamblado,.</span><span class="sxs-lookup"><span data-stu-id="7dbd3-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7dbd3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dbd3-139">See also</span></span>

- [<span data-ttu-id="7dbd3-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="7dbd3-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7dbd3-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7dbd3-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7dbd3-142">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="7dbd3-142">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="7dbd3-143">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="7dbd3-143">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
