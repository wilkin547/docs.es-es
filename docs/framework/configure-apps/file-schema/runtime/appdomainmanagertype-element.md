---
title: '&lt;appDomainManagerType&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fcfdd9bcd1aa458aad705d4ab129646e746d63b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltappdomainmanagertypegt-element"></a><span data-ttu-id="d6000-102">&lt;appDomainManagerType&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="d6000-102">&lt;appDomainManagerType&gt; Element</span></span>
<span data-ttu-id="d6000-103">Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d6000-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
 <span data-ttu-id="d6000-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d6000-104">\<configuration></span></span>  
<span data-ttu-id="d6000-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="d6000-105">\<runtime></span></span>  
<span data-ttu-id="d6000-106">\<appDomainManagerType ></span><span class="sxs-lookup"><span data-stu-id="d6000-106">\<appDomainManagerType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6000-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6000-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6000-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d6000-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d6000-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d6000-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6000-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d6000-110">Attributes</span></span>  
  
|<span data-ttu-id="d6000-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d6000-111">Attribute</span></span>|<span data-ttu-id="d6000-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6000-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="d6000-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d6000-113">Required attribute.</span></span> <span data-ttu-id="d6000-114">Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como el Administrador de dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d6000-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6000-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d6000-115">Child Elements</span></span>  
 <span data-ttu-id="d6000-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d6000-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6000-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d6000-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d6000-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d6000-118">Element</span></span>|<span data-ttu-id="d6000-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6000-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d6000-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d6000-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d6000-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d6000-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6000-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6000-122">Remarks</span></span>  
 <span data-ttu-id="d6000-123">Para especificar el tipo de administrador de dominio de aplicación, debe especificar este elemento y el [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="d6000-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="d6000-124">Si alguno de estos elementos no se especifica, se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="d6000-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="d6000-125">Cuando se carga el dominio de aplicación predeterminado, <xref:System.TypeLoadException> se produce si el tipo especificado no existe en el ensamblado especificado por el [ \<appDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) elemento; y el proceso no puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="d6000-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="d6000-126">Cuando se especifica el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creadas desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6000-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="d6000-127">Use la <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> y <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6000-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="d6000-128">Especifica el tipo de administrador de dominio de aplicación requiere la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="d6000-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="d6000-129">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, un <xref:System.TypeLoadException> se produce.</span><span class="sxs-lookup"><span data-stu-id="d6000-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="d6000-130">El formato del tipo y el espacio de nombres es el mismo formato que se usa para la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d6000-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="d6000-131">Este elemento de configuración solo está disponible en la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d6000-131">This configuration element is available only in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6000-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6000-132">Example</span></span>  
 <span data-ttu-id="d6000-133">En el ejemplo siguiente se muestra cómo especificar que el Administrador de dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el `MyMgr` escriba en el `AdMgrExample` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d6000-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6000-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6000-134">See Also</span></span>  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d6000-135">\<appDomainManagerAssembly > elemento</span><span class="sxs-lookup"><span data-stu-id="d6000-135">\<appDomainManagerAssembly> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [<span data-ttu-id="d6000-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d6000-136">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="d6000-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d6000-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="d6000-138">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="d6000-138">SetAppDomainManagerType Method</span></span>](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
