---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 636b7020a8728978ea13529382a822d99cd36f74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a><span data-ttu-id="f398d-102">&lt;NetFx40_LegacySecurityPolicy&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="f398d-102">&lt;NetFx40_LegacySecurityPolicy&gt; Element</span></span>
<span data-ttu-id="f398d-103">Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.</span><span class="sxs-lookup"><span data-stu-id="f398d-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="f398d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f398d-104">\<configuration></span></span>  
<span data-ttu-id="f398d-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="f398d-105">\<runtime></span></span>  
<span data-ttu-id="f398d-106">< NetFx40_LegacySecurityPolicy ></span><span class="sxs-lookup"><span data-stu-id="f398d-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f398d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f398d-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f398d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f398d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f398d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f398d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f398d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f398d-110">Attributes</span></span>  
  
|<span data-ttu-id="f398d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="f398d-111">Attribute</span></span>|<span data-ttu-id="f398d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f398d-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f398d-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f398d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f398d-114">Especifica si el runtime usa la directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="f398d-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f398d-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="f398d-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f398d-116">Valor</span><span class="sxs-lookup"><span data-stu-id="f398d-116">Value</span></span>|<span data-ttu-id="f398d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f398d-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="f398d-118">El tiempo de ejecución no usa la directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="f398d-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="f398d-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f398d-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="f398d-120">El runtime usa la directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="f398d-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f398d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f398d-121">Child Elements</span></span>  
 <span data-ttu-id="f398d-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f398d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f398d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f398d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f398d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f398d-124">Element</span></span>|<span data-ttu-id="f398d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f398d-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f398d-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f398d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f398d-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f398d-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f398d-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f398d-128">Remarks</span></span>  
 <span data-ttu-id="f398d-129">En la versión de .NET Framework 3.5 y versiones anteriores, la directiva CAS siempre está en efecto.</span><span class="sxs-lookup"><span data-stu-id="f398d-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="f398d-130">En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], debe estar habilitada la directiva CAS.</span><span class="sxs-lookup"><span data-stu-id="f398d-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="f398d-131">La directiva CAS es específico de la versión.</span><span class="sxs-lookup"><span data-stu-id="f398d-131">CAS policy is version-specific.</span></span> <span data-ttu-id="f398d-132">Directivas personalizadas de entidades emisoras de certificados que existen en las versiones anteriores de .NET Framework deben especificarla en el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f398d-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="f398d-133">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento a una [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] ensamblado no afecta a [código transparente en seguridad](../../../../../docs/framework/misc/security-transparent-code.md); las reglas de transparencia se siguen aplican.</span><span class="sxs-lookup"><span data-stu-id="f398d-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f398d-134">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento puede dar lugar a reducciones importantes del rendimiento para los ensamblados de imagen nativa creados por el [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) que no están instalados en el [caché global de ensamblados ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="f398d-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="f398d-135">La degradación del rendimiento se debe a la incapacidad del runtime para cargar los ensamblados como imágenes nativas cuando se aplica el atributo, lo que resulta en los que se va a carga ensamblados como just-in-time.</span><span class="sxs-lookup"><span data-stu-id="f398d-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f398d-136">Si especifica una versión de .NET Framework de destino que es anterior a la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] en la configuración del proyecto para el proyecto de Visual Studio, la directiva CAS se habilitará, incluyendo cualquier directiva CAS personalizada que especificó para esa versión.</span><span class="sxs-lookup"><span data-stu-id="f398d-136">If you specify a target .NET Framework version that is earlier than the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="f398d-137">Sin embargo, no podrá utilizar new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] tipos y miembros.</span><span class="sxs-lookup"><span data-stu-id="f398d-137">However, you will not be able to use new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] types and members.</span></span> <span data-ttu-id="f398d-138">También puede especificar una versión anterior de .NET Framework mediante el [ \<supportedRuntime > elemento](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) en el esquema de configuración de inicio en su [archivo de configuración de aplicación](../../../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="f398d-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f398d-139">Sintaxis del archivo de configuración distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f398d-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="f398d-140">Debe usar la sintaxis como se indica en las secciones de sintaxis y ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f398d-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f398d-141">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f398d-141">Configuration File</span></span>  
 <span data-ttu-id="f398d-142">Este elemento se puede usar únicamente en el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f398d-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f398d-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f398d-143">Example</span></span>  
 <span data-ttu-id="f398d-144">En el ejemplo siguiente se muestra cómo habilitar la directiva CAS heredada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f398d-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f398d-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="f398d-145">See Also</span></span>  
 [<span data-ttu-id="f398d-146">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="f398d-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="f398d-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f398d-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
