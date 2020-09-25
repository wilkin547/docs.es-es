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
ms.openlocfilehash: bd6ab1123ef3f84f7e8a06b25ce48aed37e4bef7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195264"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="0d40b-102">\<publisherPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="0d40b-102">\<publisherPolicy> Element</span></span>

<span data-ttu-id="0d40b-103">Especifica si el tiempo de ejecución aplica la directiva de editor.</span><span class="sxs-lookup"><span data-stu-id="0d40b-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="0d40b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d40b-104">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d40b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0d40b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0d40b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0d40b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d40b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="0d40b-107">Attributes</span></span>  
  
|<span data-ttu-id="0d40b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0d40b-108">Attribute</span></span>|<span data-ttu-id="0d40b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d40b-109">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="0d40b-110">Especifica si se debe aplicar la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="0d40b-110">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="0d40b-111">aplicar atributo</span><span class="sxs-lookup"><span data-stu-id="0d40b-111">apply Attribute</span></span>  
  
|<span data-ttu-id="0d40b-112">Value</span><span class="sxs-lookup"><span data-stu-id="0d40b-112">Value</span></span>|<span data-ttu-id="0d40b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d40b-113">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="0d40b-114">Aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="0d40b-114">Applies publisher policy.</span></span> <span data-ttu-id="0d40b-115">Esta es la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0d40b-115">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="0d40b-116">No aplica la Directiva de edición.</span><span class="sxs-lookup"><span data-stu-id="0d40b-116">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d40b-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0d40b-117">Child Elements</span></span>  

<span data-ttu-id="0d40b-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0d40b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d40b-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0d40b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0d40b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="0d40b-120">Element</span></span>|<span data-ttu-id="0d40b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d40b-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="0d40b-122">Contiene información sobre la redirección de versiones de ensamblado y las ubicaciones de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="0d40b-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="0d40b-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0d40b-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="0d40b-124">Encapsula la directiva de enlace y la ubicación de cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d40b-124">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="0d40b-125">Use un `<dependentAssembly>` elemento para cada ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d40b-125">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="0d40b-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0d40b-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d40b-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0d40b-127">Remarks</span></span>  

 <span data-ttu-id="0d40b-128">Cuando un proveedor de componentes publica una nueva versión de un ensamblado, el proveedor puede incluir una directiva de edición para que las aplicaciones que usan la versión anterior utilicen ahora la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="0d40b-128">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="0d40b-129">Para especificar si se va a aplicar la Directiva de edición para un ensamblado determinado, coloque el **\<publisherPolicy>** elemento en el **\<dependentAssembly>** elemento.</span><span class="sxs-lookup"><span data-stu-id="0d40b-129">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="0d40b-130">La configuración predeterminada para el atributo **aplicar** es **sí**.</span><span class="sxs-lookup"><span data-stu-id="0d40b-130">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="0d40b-131">Al establecer el atributo **Apply** en **no** , se reemplaza cualquier configuración anterior de **sí** para un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0d40b-131">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="0d40b-132">El permiso es necesario para que una aplicación ignore explícitamente la Directiva de edición mediante el [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) elemento en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0d40b-132">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="0d40b-133">El permiso se concede estableciendo la <xref:System.Security.Permissions.SecurityPermissionFlag> marca en <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="0d40b-133">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="0d40b-134">Para obtener más información, vea [permisos de seguridad de redirección de enlace de ensamblados](../../assembly-binding-redirection-security-permission.md).</span><span class="sxs-lookup"><span data-stu-id="0d40b-134">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d40b-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d40b-135">Example</span></span>  

 <span data-ttu-id="0d40b-136">En el siguiente ejemplo se desactiva la Directiva de edición para el ensamblado, `myAssembly` .</span><span class="sxs-lookup"><span data-stu-id="0d40b-136">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d40b-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d40b-137">See also</span></span>

- [<span data-ttu-id="0d40b-138">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0d40b-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0d40b-139">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0d40b-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0d40b-140">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="0d40b-140">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="0d40b-141">Redirigir versiones de ensamblado</span><span class="sxs-lookup"><span data-stu-id="0d40b-141">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
