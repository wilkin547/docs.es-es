---
title: '&lt;appDomainManagerAssembly&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e2c43a5cfba89df3ae90950f09a7a947729f51b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746601"
---
# <a name="ltappdomainmanagerassemblygt-element"></a><span data-ttu-id="a8205-102">&lt;appDomainManagerAssembly&gt; Element</span><span class="sxs-lookup"><span data-stu-id="a8205-102">&lt;appDomainManagerAssembly&gt; Element</span></span>
<span data-ttu-id="a8205-103">Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8205-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
 <span data-ttu-id="a8205-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a8205-104">\<configuration></span></span>  
<span data-ttu-id="a8205-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a8205-105">\<runtime></span></span>  
<span data-ttu-id="a8205-106">\<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="a8205-106">\<appDomainManagerAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8205-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8205-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8205-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a8205-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a8205-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a8205-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8205-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8205-110">Attributes</span></span>  
  
|<span data-ttu-id="a8205-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a8205-111">Attribute</span></span>|<span data-ttu-id="a8205-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8205-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="a8205-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a8205-113">Required attribute.</span></span> <span data-ttu-id="a8205-114">Especifica el nombre para mostrar del ensamblado que proporciona el administrador del dominio para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8205-114">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8205-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a8205-115">Child Elements</span></span>  
 <span data-ttu-id="a8205-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a8205-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8205-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a8205-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a8205-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8205-118">Element</span></span>|<span data-ttu-id="a8205-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8205-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a8205-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8205-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a8205-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a8205-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8205-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8205-122">Remarks</span></span>  
 <span data-ttu-id="a8205-123">Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="a8205-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="a8205-124">Si no se especifica cualquiera de estos elementos, se omite el resto.</span><span class="sxs-lookup"><span data-stu-id="a8205-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="a8205-125">Cuando se carga el dominio de aplicación predeterminado, <xref:System.TypeLoadException> se produce si el ensamblado especificado no existe o si el ensamblado no contiene el tipo especificado por el [ \<appDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) elemento; y no se puede iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="a8205-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="a8205-126">Si se encuentra el ensamblado, pero no coincide con la información de versión, un <xref:System.IO.FileLoadException> se produce.</span><span class="sxs-lookup"><span data-stu-id="a8205-126">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="a8205-127">Cuando se especifica el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8205-127">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="a8205-128">Use la <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> y <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8205-128">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="a8205-129">Especifica el tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a8205-129">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="a8205-130">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, un <xref:System.TypeLoadException> se produce.</span><span class="sxs-lookup"><span data-stu-id="a8205-130">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="a8205-131">Para el formato del nombre para mostrar del ensamblado, vea el <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a8205-131">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="a8205-132">Este elemento de configuración solo está disponible en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a8205-132">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8205-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8205-133">Example</span></span>  
 <span data-ttu-id="a8205-134">El ejemplo siguiente muestra cómo especificar que el Administrador de dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el `MyMgr` escriba en el `AdMgrExample` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a8205-134">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8205-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8205-135">See also</span></span>
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a8205-136">\<appDomainManagerType > elemento</span><span class="sxs-lookup"><span data-stu-id="a8205-136">\<appDomainManagerType> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [<span data-ttu-id="a8205-137">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a8205-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a8205-138">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a8205-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="a8205-139">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="a8205-139">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
