---
title: <appDomainManagerType> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ffb297cc38f20917e720b216607e9ccfc966866
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252841"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="38e7c-102">\<appDomainManagerType >, elemento</span><span class="sxs-lookup"><span data-stu-id="38e7c-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="38e7c-103">Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="38e7c-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="38e7c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38e7c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38e7c-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="38e7c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="38e7c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerType>**</span><span class="sxs-lookup"><span data-stu-id="38e7c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e7c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38e7c-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38e7c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38e7c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="38e7c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38e7c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38e7c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="38e7c-110">Attributes</span></span>  
  
|<span data-ttu-id="38e7c-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="38e7c-111">Attribute</span></span>|<span data-ttu-id="38e7c-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="38e7c-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="38e7c-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="38e7c-113">Required attribute.</span></span> <span data-ttu-id="38e7c-114">Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como administrador del dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="38e7c-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38e7c-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38e7c-115">Child Elements</span></span>  
 <span data-ttu-id="38e7c-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="38e7c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38e7c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38e7c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="38e7c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="38e7c-118">Element</span></span>|<span data-ttu-id="38e7c-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="38e7c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="38e7c-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38e7c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="38e7c-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="38e7c-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38e7c-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38e7c-122">Remarks</span></span>  
 <span data-ttu-id="38e7c-123">Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el elemento [ \<> de appDomainManagerAssembly](appdomainmanagerassembly-element.md) .</span><span class="sxs-lookup"><span data-stu-id="38e7c-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="38e7c-124">Si no se especifica ninguno de estos elementos, se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="38e7c-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="38e7c-125">Cuando se carga el dominio de aplicación predeterminado <xref:System.TypeLoadException> , se produce si el tipo especificado no existe en el ensamblado especificado por el [ \<elemento > appDomainManagerAssembly](appdomainmanagerassembly-element.md) ; y el proceso no se inicia.</span><span class="sxs-lookup"><span data-stu-id="38e7c-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="38e7c-126">Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="38e7c-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="38e7c-127">Use las <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> propiedades <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> y para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="38e7c-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="38e7c-128">La especificación del tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="38e7c-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="38e7c-129">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, se produce <xref:System.TypeLoadException> una excepción.</span><span class="sxs-lookup"><span data-stu-id="38e7c-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="38e7c-130">El formato del tipo y el espacio de nombres es el mismo formato que se utiliza <xref:System.Type.FullName%2A?displayProperty=nameWithType> para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="38e7c-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="38e7c-131">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="38e7c-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38e7c-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38e7c-132">Example</span></span>  
 <span data-ttu-id="38e7c-133">En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación para el dominio de aplicación predeterminado de `MyMgr` un proceso es el tipo del ensamblado.`AdMgrExample`</span><span class="sxs-lookup"><span data-stu-id="38e7c-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38e7c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="38e7c-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="38e7c-135">\<appDomainManagerAssembly >, elemento</span><span class="sxs-lookup"><span data-stu-id="38e7c-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="38e7c-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="38e7c-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="38e7c-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="38e7c-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="38e7c-138">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="38e7c-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
