---
title: '&lt;bypassTrustedAppStrongNames&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6988be28e3129748ee7f7996a66c728ccde3c70b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745388"
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a><span data-ttu-id="03c54-102">&lt;bypassTrustedAppStrongNames&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="03c54-102">&lt;bypassTrustedAppStrongNames&gt; Element</span></span>
<span data-ttu-id="03c54-103">Especifica si se debe omitir la validación de nombres seguros en los ensamblados de plena confianza que se cargan en plena confianza <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="03c54-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="03c54-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03c54-104">\<configuration></span></span>  
<span data-ttu-id="03c54-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="03c54-105">\<runtime></span></span>  
<span data-ttu-id="03c54-106">\<bypassTrustedAppStrongNames ></span><span class="sxs-lookup"><span data-stu-id="03c54-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03c54-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03c54-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03c54-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03c54-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03c54-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03c54-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03c54-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="03c54-110">Attributes</span></span>  
  
|<span data-ttu-id="03c54-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="03c54-111">Attribute</span></span>|<span data-ttu-id="03c54-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="03c54-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="03c54-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="03c54-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="03c54-114">Especifica si está habilitada la característica de omisión que evite la validación de nombres seguros para los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="03c54-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="03c54-115">Cuando esta característica está habilitada, no se validan los nombres seguros son correctos cuando se carga el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="03c54-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="03c54-116">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="03c54-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="03c54-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="03c54-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="03c54-118">Valor</span><span class="sxs-lookup"><span data-stu-id="03c54-118">Value</span></span>|<span data-ttu-id="03c54-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="03c54-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="03c54-120">Las firmas de nombre seguro de ensamblados de plena confianza no se validan cuando los ensamblados se cargan en plena confianza <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="03c54-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="03c54-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="03c54-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="03c54-122">Las firmas de nombre seguro en los ensamblados de plena confianza se validan cuando los ensamblados se cargan en plena confianza <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="03c54-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="03c54-123">Se comprueba la firma de nombre seguro solo para la exactitud de la firma; no se compara con otro nombre seguro para una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="03c54-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03c54-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03c54-124">Child Elements</span></span>  
 <span data-ttu-id="03c54-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="03c54-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03c54-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03c54-126">Parent Elements</span></span>  
  
|<span data-ttu-id="03c54-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="03c54-127">Element</span></span>|<span data-ttu-id="03c54-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="03c54-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03c54-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03c54-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="03c54-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="03c54-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03c54-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03c54-131">Remarks</span></span>  
 <span data-ttu-id="03c54-132">La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de firma de nombre seguro de ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="03c54-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="03c54-133">La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:</span><span class="sxs-lookup"><span data-stu-id="03c54-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="03c54-134">Plena confianza sin el <xref:System.Security.Policy.StrongName> evidencia (por ejemplo, tiene `MyComputer` evidencia de zona).</span><span class="sxs-lookup"><span data-stu-id="03c54-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="03c54-135">se cargue en un <xref:System.AppDomain> de plena confianza;</span><span class="sxs-lookup"><span data-stu-id="03c54-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="03c54-136">se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="03c54-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="03c54-137">no tenga firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="03c54-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03c54-138">Si la característica de omisión se ha desactivado para todas las aplicaciones en el equipo mediante el uso de una clave del registro, este archivo de configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="03c54-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="03c54-139">Para obtener más información, consulte [Cómo: deshabilitar la característica de omisión de nombres seguros](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="03c54-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03c54-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03c54-140">Example</span></span>  
 <span data-ttu-id="03c54-141">En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="03c54-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03c54-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="03c54-142">See Also</span></span>  
 [<span data-ttu-id="03c54-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="03c54-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="03c54-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="03c54-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 <span data-ttu-id="03c54-145">[Cómo: Deshabilitar la característica de omisión de nombres seguros](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="03c54-145">[How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)</span></span>
