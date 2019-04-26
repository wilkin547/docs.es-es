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
ms.openlocfilehash: 29932eb27bcd13876ea6982982e67341edb8e0de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674082"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="3019f-102">\<publisherPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="3019f-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="3019f-103">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="3019f-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="3019f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3019f-104">\<configuration></span></span>  
<span data-ttu-id="3019f-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="3019f-105">\<runtime></span></span>  
<span data-ttu-id="3019f-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="3019f-106">\<assemblyBinding></span></span>  
<span data-ttu-id="3019f-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="3019f-107">\<dependentAssembly></span></span>  
<span data-ttu-id="3019f-108">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="3019f-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3019f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3019f-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3019f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3019f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3019f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3019f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3019f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3019f-112">Attributes</span></span>  
  
|<span data-ttu-id="3019f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3019f-113">Attribute</span></span>|<span data-ttu-id="3019f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3019f-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="3019f-115">Especifica si se debe aplicar la directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="3019f-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="3019f-116">aplicar el atributo</span><span class="sxs-lookup"><span data-stu-id="3019f-116">apply Attribute</span></span>  
  
|<span data-ttu-id="3019f-117">Valor</span><span class="sxs-lookup"><span data-stu-id="3019f-117">Value</span></span>|<span data-ttu-id="3019f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3019f-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="3019f-119">Aplica la directiva de publicador.</span><span class="sxs-lookup"><span data-stu-id="3019f-119">Applies publisher policy.</span></span> <span data-ttu-id="3019f-120">Ésta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3019f-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="3019f-121">No se aplica la directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="3019f-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3019f-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3019f-122">Child Elements</span></span>  
 <span data-ttu-id="3019f-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3019f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3019f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3019f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3019f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3019f-125">Element</span></span>|<span data-ttu-id="3019f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3019f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3019f-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3019f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3019f-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3019f-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3019f-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3019f-129">Remarks</span></span>  
 <span data-ttu-id="3019f-130">Cuando un proveedor lanza una nueva versión de un ensamblado, el proveedor puede incluir una directiva de publicador para que las aplicaciones que usan la versión anterior ahora usar la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="3019f-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="3019f-131">Para especificar si se debe aplicar la directiva de edición para un ensamblado determinado, coloque el  **\<publisherPolicy >** elemento en el  **\<dependentAssembly >** elemento.</span><span class="sxs-lookup"><span data-stu-id="3019f-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="3019f-132">La configuración predeterminada para el **aplicar** atributo es **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3019f-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="3019f-133">Establecer el **aplicar** atributo **ningún** invalida cualquier anterior **Sí** configuración de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3019f-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="3019f-134">Se requiere permiso para una aplicación para omitir explícitamente la directiva de publicador con el [ \<publisherPolicy aplicar = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) elemento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3019f-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="3019f-135">El permiso se otorga estableciendo el <xref:System.Security.Permissions.SecurityPermissionFlag> marca en el <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="3019f-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="3019f-136">Para obtener más información, consulte [permiso de seguridad de redirección de enlace de ensamblado](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="3019f-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3019f-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3019f-137">Example</span></span>  
 <span data-ttu-id="3019f-138">El ejemplo siguiente se desactiva la directiva de publicador para el ensamblado, `myAssembly`.</span><span class="sxs-lookup"><span data-stu-id="3019f-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3019f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="3019f-139">See also</span></span>

- [<span data-ttu-id="3019f-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3019f-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="3019f-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3019f-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="3019f-142">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="3019f-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="3019f-143">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="3019f-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
