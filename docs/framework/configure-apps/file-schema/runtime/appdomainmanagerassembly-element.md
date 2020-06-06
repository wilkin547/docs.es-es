---
title: <appDomainManagerAssembly> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154437"
---
# <a name="appdomainmanagerassembly-element"></a><span data-ttu-id="ddccb-102">\<appDomainManagerAssembly> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="ddccb-102">\<appDomainManagerAssembly> Element</span></span>
<span data-ttu-id="ddccb-103">Especifica el ensamblado que proporciona el administrador de dominios de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ddccb-103">Specifies the assembly that provides the application domain manager for the default application domain in the process.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="ddccb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddccb-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddccb-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ddccb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ddccb-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ddccb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddccb-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="ddccb-107">Attributes</span></span>  
  
|<span data-ttu-id="ddccb-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="ddccb-108">Attribute</span></span>|<span data-ttu-id="ddccb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddccb-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="ddccb-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ddccb-110">Required attribute.</span></span> <span data-ttu-id="ddccb-111">Especifica el nombre para mostrar del ensamblado que proporciona el administrador del dominio de aplicación para el dominio de aplicación predeterminado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ddccb-111">Specifies the display name of the assembly that provides the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddccb-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ddccb-112">Child Elements</span></span>  
 <span data-ttu-id="ddccb-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ddccb-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddccb-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ddccb-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ddccb-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddccb-115">Element</span></span>|<span data-ttu-id="ddccb-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddccb-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ddccb-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ddccb-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ddccb-118">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ddccb-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddccb-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ddccb-119">Remarks</span></span>  
 <span data-ttu-id="ddccb-120">Para especificar el tipo del administrador del dominio de aplicación, debe especificar este elemento y el [\<appDomainManagerType>](appdomainmanagertype-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="ddccb-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerType>](appdomainmanagertype-element.md) element.</span></span> <span data-ttu-id="ddccb-121">Si no se especifica ninguno de estos elementos, se omite el otro.</span><span class="sxs-lookup"><span data-stu-id="ddccb-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="ddccb-122">Cuando se carga el dominio de aplicación predeterminado, <xref:System.TypeLoadException> se produce si el ensamblado especificado no existe o si el ensamblado no contiene el tipo especificado por el [\<appDomainManagerType>](appdomainmanagertype-element.md) elemento; y el proceso no se inicia.</span><span class="sxs-lookup"><span data-stu-id="ddccb-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified assembly does not exist or if the assembly does not contain the type specified by the [\<appDomainManagerType>](appdomainmanagertype-element.md) element; and the process fails to start.</span></span> <span data-ttu-id="ddccb-123">Si se encuentra el ensamblado pero la información de la versión no coincide, <xref:System.IO.FileLoadException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ddccb-123">If the assembly is found but the version information does not match, a <xref:System.IO.FileLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ddccb-124">Al especificar el tipo de administrador de dominio de aplicación para el dominio de aplicación predeterminado, otros dominios de aplicación creados desde el dominio de aplicación predeterminado heredan el tipo de administrador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ddccb-124">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="ddccb-125">Use las <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> propiedades y para especificar un tipo de administrador de dominio de aplicación diferente para un nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ddccb-125">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="ddccb-126">La especificación del tipo de administrador de dominio de aplicación requiere que la aplicación tenga plena confianza.</span><span class="sxs-lookup"><span data-stu-id="ddccb-126">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="ddccb-127">(Por ejemplo, una aplicación que se ejecuta en el escritorio tiene plena confianza). Si la aplicación no tiene plena confianza, <xref:System.TypeLoadException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="ddccb-127">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="ddccb-128">Para obtener el formato del nombre para mostrar del ensamblado, vea la <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="ddccb-128">For the format of the assembly display name, see the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="ddccb-129">Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ddccb-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddccb-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddccb-130">Example</span></span>  
 <span data-ttu-id="ddccb-131">En el ejemplo siguiente se muestra cómo especificar que el administrador del dominio de aplicación para el dominio de aplicación predeterminado de un proceso es el `MyMgr` tipo del `AdMgrExample` ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ddccb-131">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddccb-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddccb-132">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ddccb-133">\<appDomainManagerType>Element</span><span class="sxs-lookup"><span data-stu-id="ddccb-133">\<appDomainManagerType> Element</span></span>](appdomainmanagertype-element.md)
- [<span data-ttu-id="ddccb-134">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="ddccb-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ddccb-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ddccb-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ddccb-136">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="ddccb-136">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
