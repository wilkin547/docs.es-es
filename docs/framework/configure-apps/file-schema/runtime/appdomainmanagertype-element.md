---
title: '&lt;appDomainManagerType&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e7f37fd652ce98e24d2e2e99edcd3d59a0e597b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610437"
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="4559a-102">&lt;appDomainManagerType&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="4559a-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="4559a-103">Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4559a-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="4559a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4559a-104">\<configuration></span></span>  
<span data-ttu-id="4559a-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="4559a-105">\<runtime></span></span>  
<span data-ttu-id="4559a-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="4559a-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4559a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4559a-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4559a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4559a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4559a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4559a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4559a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4559a-110">Attributes</span></span>  
  
|<span data-ttu-id="4559a-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="4559a-111">Attribute</span></span>|<span data-ttu-id="4559a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4559a-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="4559a-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4559a-113">Required attribute.</span></span> <span data-ttu-id="4559a-114">Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como el Administrador de dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4559a-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4559a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4559a-115">Child Elements</span></span>  
 <span data-ttu-id="4559a-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4559a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4559a-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4559a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4559a-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="4559a-118">Element</span></span>|<span data-ttu-id="4559a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4559a-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4559a-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4559a-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="4559a-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4559a-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4559a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4559a-122">Remarks</span></span>  
 <span data-ttu-id="4559a-123">Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4559a-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="4559a-124">Si no se especifica cualquiera de estos elementos, se omite el resto.</span><span class="sxs-lookup"><span data-stu-id="4559a-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="4559a-125">Cuando se carga el dominio de aplicación predeterminado, <xref:System.TypeLoadException> se produce si el tipo especificado no existe en el ensamblado especificado por el [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento; y el proceso no puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="4559a-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="4559a-126">Cuando se especifica el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4559a-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="4559a-127">Use la <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> y <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4559a-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="4559a-128">Especifica el tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="4559a-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="4559a-129">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, un <xref:System.TypeLoadException> se produce.</span><span class="sxs-lookup"><span data-stu-id="4559a-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="4559a-130">El formato del tipo y espacio de nombres es el mismo formato que se usa para el <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="4559a-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="4559a-131">Este elemento de configuración solo está disponible en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4559a-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4559a-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4559a-132">Example</span></span>  
 <span data-ttu-id="4559a-133">El ejemplo siguiente muestra cómo especificar que el Administrador de dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el `MyMgr` escriba en el `AdMgrExample` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4559a-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4559a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="4559a-134">See Also</span></span>  
- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="4559a-135">\<appDomainManagerAssembly > elemento</span><span class="sxs-lookup"><span data-stu-id="4559a-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
- [<span data-ttu-id="4559a-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4559a-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="4559a-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4559a-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="4559a-138">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="4559a-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
