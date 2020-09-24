---
title: <appDomainManagerType> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: e21384de6ca07c637a79ee54207d1e3ddfbf20e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170316"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="e77d2-102">\<appDomainManagerType> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="e77d2-102">\<appDomainManagerType> Element</span></span>

<span data-ttu-id="e77d2-103">Especifica el tipo que sirve de administrador de dominios de aplicación para el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e77d2-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="e77d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e77d2-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e77d2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e77d2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e77d2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e77d2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e77d2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="e77d2-107">Attributes</span></span>  
  
|<span data-ttu-id="e77d2-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="e77d2-108">Attribute</span></span>|<span data-ttu-id="e77d2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e77d2-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="e77d2-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="e77d2-110">Required attribute.</span></span> <span data-ttu-id="e77d2-111">Especifica el nombre del tipo, incluido el espacio de nombres, que actúa como administrador del dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e77d2-111">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e77d2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e77d2-112">Child Elements</span></span>  

 <span data-ttu-id="e77d2-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e77d2-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e77d2-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e77d2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e77d2-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e77d2-115">Element</span></span>|<span data-ttu-id="e77d2-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e77d2-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e77d2-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e77d2-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e77d2-118">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e77d2-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e77d2-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e77d2-119">Remarks</span></span>  

 <span data-ttu-id="e77d2-120">Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e77d2-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="e77d2-121">Si no se especifica ninguno de estos elementos, se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="e77d2-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="e77d2-122">Cuando se carga el dominio de aplicación predeterminado, <xref:System.TypeLoadException> se produce si el tipo especificado no existe en el ensamblado especificado por el [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) elemento; y el proceso no se inicia.</span><span class="sxs-lookup"><span data-stu-id="e77d2-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="e77d2-123">Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e77d2-123">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="e77d2-124">Use las <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades y para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e77d2-124">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="e77d2-125">La especificación del tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="e77d2-125">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="e77d2-126">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, <xref:System.TypeLoadException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="e77d2-126">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e77d2-127">El formato del tipo y el espacio de nombres es el mismo formato que se utiliza para la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e77d2-127">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="e77d2-128">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e77d2-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e77d2-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e77d2-129">Example</span></span>  

 <span data-ttu-id="e77d2-130">En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el `MyMgr` tipo del `AdMgrExample` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e77d2-130">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e77d2-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e77d2-131">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e77d2-132">Elemento \<appDomainManagerAssembly></span><span class="sxs-lookup"><span data-stu-id="e77d2-132">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="e77d2-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="e77d2-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e77d2-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e77d2-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e77d2-135">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="e77d2-135">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
