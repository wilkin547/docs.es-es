---
description: 'Más información acerca de: <publisherPolicy> elemento'
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
ms.openlocfilehash: 35d729d5b195e010a80e7272312f14ac5802001b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802442"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="1f089-103">\<publisherPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="1f089-103">\<publisherPolicy> Element</span></span>

<span data-ttu-id="1f089-104">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="1f089-104">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="1f089-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f089-105">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f089-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1f089-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1f089-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1f089-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f089-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="1f089-108">Attributes</span></span>  
  
|<span data-ttu-id="1f089-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="1f089-109">Attribute</span></span>|<span data-ttu-id="1f089-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f089-110">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="1f089-111">Especifica si se debe aplicar la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="1f089-111">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="1f089-112">aplicar atributo</span><span class="sxs-lookup"><span data-stu-id="1f089-112">apply Attribute</span></span>  
  
|<span data-ttu-id="1f089-113">Value</span><span class="sxs-lookup"><span data-stu-id="1f089-113">Value</span></span>|<span data-ttu-id="1f089-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f089-114">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="1f089-115">Aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="1f089-115">Applies publisher policy.</span></span> <span data-ttu-id="1f089-116">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1f089-116">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="1f089-117">No aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="1f089-117">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f089-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1f089-118">Child Elements</span></span>  

<span data-ttu-id="1f089-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1f089-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f089-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1f089-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1f089-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="1f089-121">Element</span></span>|<span data-ttu-id="1f089-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f089-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="1f089-123">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="1f089-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="1f089-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1f089-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="1f089-125">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f089-125">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="1f089-126">Use un `<dependentAssembly>` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f089-126">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="1f089-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1f089-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f089-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f089-128">Remarks</span></span>  

 <span data-ttu-id="1f089-129">Cuando un proveedor de componentes publica una nueva versión de un ensamblado, el proveedor puede incluir una directiva de edición para que las aplicaciones que usan la versión anterior utilicen ahora la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="1f089-129">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="1f089-130">Para especificar si se va a aplicar la Directiva de edición para un ensamblado determinado, coloque el **\<publisherPolicy>** elemento en el **\<dependentAssembly>** elemento.</span><span class="sxs-lookup"><span data-stu-id="1f089-130">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="1f089-131">La configuración predeterminada para el atributo **aplicar** es **sí**.</span><span class="sxs-lookup"><span data-stu-id="1f089-131">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="1f089-132">Al establecer el atributo **Apply** en **no** , se reemplaza cualquier configuración anterior de **sí** para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f089-132">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="1f089-133">El permiso es necesario para que una aplicación ignore explícitamente la Directiva de edición mediante el [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) elemento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1f089-133">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="1f089-134">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="1f089-134">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="1f089-135">Para obtener más información, vea [permisos de seguridad de redirección de enlace de ensamblados](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="1f089-135">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f089-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f089-136">Example</span></span>  

 <span data-ttu-id="1f089-137">En el siguiente ejemplo se desactiva la Directiva de edición para el ensamblado, `myAssembly` .</span><span class="sxs-lookup"><span data-stu-id="1f089-137">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1f089-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f089-138">See also</span></span>

- [<span data-ttu-id="1f089-139">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1f089-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1f089-140">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1f089-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1f089-141">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="1f089-141">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="1f089-142">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="1f089-142">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
