---
title: <appDomainManagerType> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154436"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="a0e72-102">\<elemento de> appDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="a0e72-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="a0e72-103">Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a0e72-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="a0e72-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0e72-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0e72-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0e72-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a0e72-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span><span class="sxs-lookup"><span data-stu-id="a0e72-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e72-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0e72-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0e72-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0e72-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0e72-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0e72-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0e72-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0e72-110">Attributes</span></span>  
  
|<span data-ttu-id="a0e72-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0e72-111">Attribute</span></span>|<span data-ttu-id="a0e72-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0e72-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="a0e72-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a0e72-113">Required attribute.</span></span> <span data-ttu-id="a0e72-114">Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como administrador de dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a0e72-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0e72-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0e72-115">Child Elements</span></span>  
 <span data-ttu-id="a0e72-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0e72-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0e72-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0e72-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a0e72-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0e72-118">Element</span></span>|<span data-ttu-id="a0e72-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0e72-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a0e72-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a0e72-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a0e72-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a0e72-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0e72-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a0e72-122">Remarks</span></span>  
 <span data-ttu-id="a0e72-123">Para especificar el tipo del administrador de dominio de aplicación, debe especificar este elemento y el [ \<elemento de>appDomainManagerAssembly.](appdomainmanagerassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0e72-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="a0e72-124">Si no se especifica ninguno de estos elementos, se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="a0e72-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="a0e72-125">Cuando se carga el <xref:System.TypeLoadException> dominio de aplicación predeterminado, se produce si el tipo especificado no existe en el ensamblado especificado por el [ \<elemento de>appDomainManagerAssembly;](appdomainmanagerassembly-element.md) y el proceso no se inicia.</span><span class="sxs-lookup"><span data-stu-id="a0e72-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="a0e72-126">Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados a partir del dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0e72-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="a0e72-127">Use <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> las <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades y para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0e72-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="a0e72-128">Especificar el tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="a0e72-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="a0e72-129">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza.) Si la aplicación no tiene <xref:System.TypeLoadException> plena confianza, se produce un.</span><span class="sxs-lookup"><span data-stu-id="a0e72-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="a0e72-130">El formato del tipo y el espacio de <xref:System.Type.FullName%2A?displayProperty=nameWithType> nombres es el mismo formato que se usa para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a0e72-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="a0e72-131">Este elemento de configuración solo está disponible en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a0e72-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0e72-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0e72-132">Example</span></span>  
 <span data-ttu-id="a0e72-133">En el ejemplo siguiente se muestra cómo especificar que el administrador `MyMgr` de dominio `AdMgrExample` de aplicación para el dominio de aplicación predeterminado de un proceso es el tipo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a0e72-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0e72-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0e72-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a0e72-135">\<appDomainManagerAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="a0e72-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="a0e72-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a0e72-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a0e72-137">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a0e72-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a0e72-138">Método SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="a0e72-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
