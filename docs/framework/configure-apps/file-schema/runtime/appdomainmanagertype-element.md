---
title: <appDomainManagerType> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: bae4aa39f9c43480ac2ef984f78834b68646742d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118242"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="5c5b2-102">\<elemento > appDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="5c5b2-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="5c5b2-103">Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="5c5b2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c5b2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5c5b2-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5c5b2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5c5b2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<appDomainManagerType >**</span><span class="sxs-lookup"><span data-stu-id="5c5b2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5b2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c5b2-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c5b2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c5b2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5c5b2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c5b2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c5b2-110">Attributes</span></span>  
  
|<span data-ttu-id="5c5b2-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5c5b2-111">Attribute</span></span>|<span data-ttu-id="5c5b2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c5b2-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="5c5b2-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-113">Required attribute.</span></span> <span data-ttu-id="5c5b2-114">Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como administrador del dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c5b2-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c5b2-115">Child Elements</span></span>  
 <span data-ttu-id="5c5b2-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c5b2-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c5b2-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5c5b2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c5b2-118">Element</span></span>|<span data-ttu-id="5c5b2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c5b2-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5c5b2-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5c5b2-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c5b2-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c5b2-122">Remarks</span></span>  
 <span data-ttu-id="5c5b2-123">Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [\<appDomainManagerAssembly >](appdomainmanagerassembly-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="5c5b2-124">Si no se especifica ninguno de estos elementos, se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="5c5b2-125">Cuando se carga el dominio de aplicación predeterminado, se produce <xref:System.TypeLoadException> si el tipo especificado no existe en el ensamblado especificado por el elemento de [> de\<appDomainManagerAssembly](appdomainmanagerassembly-element.md) . y el proceso no se inicia.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="5c5b2-126">Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="5c5b2-127">Use las propiedades <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> y <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="5c5b2-128">La especificación del tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="5c5b2-129">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, se produce una <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="5c5b2-130">El formato del tipo y el espacio de nombres es el mismo formato que se utiliza para la propiedad <xref:System.Type.FullName%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="5c5b2-131">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c5b2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c5b2-132">Example</span></span>  
 <span data-ttu-id="5c5b2-133">En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el tipo de `MyMgr` del ensamblado `AdMgrExample`.</span><span class="sxs-lookup"><span data-stu-id="5c5b2-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c5b2-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c5b2-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5c5b2-135">\<elemento > appDomainManagerAssembly</span><span class="sxs-lookup"><span data-stu-id="5c5b2-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="5c5b2-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="5c5b2-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5c5b2-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="5c5b2-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5c5b2-138">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="5c5b2-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
