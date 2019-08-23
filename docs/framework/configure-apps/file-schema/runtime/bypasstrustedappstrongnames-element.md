---
title: <bypassTrustedAppStrongNames> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92873277b4b25e4c1c5981628187078ac7cb5704
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920887"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="eb57e-102">Elemento \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="eb57e-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="eb57e-103">Especifica si se omitirá la validación de nombres seguros en ensamblados de plena confianza que se cargan en una <xref:System.AppDomain>plena confianza.</span><span class="sxs-lookup"><span data-stu-id="eb57e-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="eb57e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eb57e-104">\<configuration></span></span>  
<span data-ttu-id="eb57e-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="eb57e-105">\<runtime></span></span>  
<span data-ttu-id="eb57e-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="eb57e-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb57e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb57e-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb57e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eb57e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eb57e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eb57e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb57e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="eb57e-110">Attributes</span></span>  
  
|<span data-ttu-id="eb57e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="eb57e-111">Attribute</span></span>|<span data-ttu-id="eb57e-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eb57e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="eb57e-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="eb57e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="eb57e-114">Especifica si está habilitada la característica de omisión que evita la validación de nombres seguros para los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="eb57e-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="eb57e-115">Cuando esta característica está habilitada, los nombres seguros no se validan para comprobar su exactitud cuando se carga el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="eb57e-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="eb57e-116">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="eb57e-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="eb57e-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="eb57e-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="eb57e-118">Value</span><span class="sxs-lookup"><span data-stu-id="eb57e-118">Value</span></span>|<span data-ttu-id="eb57e-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eb57e-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="eb57e-120">Las firmas de nombre seguro de los ensamblados de plena confianza no se validan cuando los ensamblados se cargan en <xref:System.AppDomain>una plena confianza.</span><span class="sxs-lookup"><span data-stu-id="eb57e-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="eb57e-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="eb57e-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="eb57e-122">Las firmas de nombre seguro de los ensamblados de plena confianza se validan cuando los ensamblados se cargan en <xref:System.AppDomain>una plena confianza.</span><span class="sxs-lookup"><span data-stu-id="eb57e-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="eb57e-123">La firma de nombre seguro se comprueba únicamente para comprobar la exactitud de la firma; no se compara con otro nombre seguro para buscar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="eb57e-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb57e-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eb57e-124">Child Elements</span></span>  
 <span data-ttu-id="eb57e-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb57e-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb57e-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eb57e-126">Parent Elements</span></span>  
  
|<span data-ttu-id="eb57e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb57e-127">Element</span></span>|<span data-ttu-id="eb57e-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="eb57e-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eb57e-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb57e-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="eb57e-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="eb57e-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb57e-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb57e-131">Remarks</span></span>  
 <span data-ttu-id="eb57e-132">La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de la firma de nombre seguro de los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="eb57e-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="eb57e-133">La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:</span><span class="sxs-lookup"><span data-stu-id="eb57e-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
- <span data-ttu-id="eb57e-134">De plena confianza sin <xref:System.Security.Policy.StrongName> la evidencia (por ejemplo, `MyComputer` tiene evidencia de zona).</span><span class="sxs-lookup"><span data-stu-id="eb57e-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
- <span data-ttu-id="eb57e-135">se cargue en un <xref:System.AppDomain> de plena confianza;</span><span class="sxs-lookup"><span data-stu-id="eb57e-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="eb57e-136">se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="eb57e-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="eb57e-137">no tenga firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="eb57e-137">Not delay-signed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb57e-138">Si la característica de omisión se ha desactivado para todas las aplicaciones del equipo mediante una clave del registro, este valor del archivo de configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="eb57e-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="eb57e-139">Para obtener más información, consulte [Cómo para deshabilitar la característica de omisión de nombres seguros](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="eb57e-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb57e-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb57e-140">Example</span></span>  
 <span data-ttu-id="eb57e-141">En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="eb57e-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb57e-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb57e-142">See also</span></span>

- [<span data-ttu-id="eb57e-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="eb57e-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eb57e-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="eb57e-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="eb57e-145">Cómo: Deshabilitar la característica de omisión de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="eb57e-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)
