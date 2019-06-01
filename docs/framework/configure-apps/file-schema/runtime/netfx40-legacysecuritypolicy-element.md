---
title: Elemento <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848c56773c0ff2986f0bec3e82a08a3d0dd35434
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456471"
---
# <a name="netfx40legacysecuritypolicy-element"></a><span data-ttu-id="64494-102">\<NetFx40_LegacySecurityPolicy > elemento</span><span class="sxs-lookup"><span data-stu-id="64494-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>
<span data-ttu-id="64494-103">Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.</span><span class="sxs-lookup"><span data-stu-id="64494-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="64494-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="64494-104">\<configuration></span></span>  
<span data-ttu-id="64494-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="64494-105">\<runtime></span></span>  
<span data-ttu-id="64494-106"><NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="64494-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64494-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64494-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64494-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64494-108">Attributes and Elements</span></span>  
 <span data-ttu-id="64494-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="64494-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64494-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="64494-110">Attributes</span></span>  
  
|<span data-ttu-id="64494-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="64494-111">Attribute</span></span>|<span data-ttu-id="64494-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="64494-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="64494-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="64494-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="64494-114">Especifica si el runtime usa la directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="64494-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="64494-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="64494-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="64494-116">Valor</span><span class="sxs-lookup"><span data-stu-id="64494-116">Value</span></span>|<span data-ttu-id="64494-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="64494-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="64494-118">El tiempo de ejecución no usa la directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="64494-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="64494-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="64494-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="64494-120">El runtime usa la directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="64494-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64494-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64494-121">Child Elements</span></span>  
 <span data-ttu-id="64494-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="64494-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64494-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64494-123">Parent Elements</span></span>  
  
|<span data-ttu-id="64494-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="64494-124">Element</span></span>|<span data-ttu-id="64494-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="64494-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="64494-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64494-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="64494-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="64494-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64494-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64494-128">Remarks</span></span>  
 <span data-ttu-id="64494-129">En la versión de .NET Framework 3.5 y versiones anteriores, la directiva CAS siempre está en efecto.</span><span class="sxs-lookup"><span data-stu-id="64494-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="64494-130">En el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], debe estar habilitada la directiva CAS.</span><span class="sxs-lookup"><span data-stu-id="64494-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="64494-131">La directiva CAS es específico de la versión.</span><span class="sxs-lookup"><span data-stu-id="64494-131">CAS policy is version-specific.</span></span> <span data-ttu-id="64494-132">Deben volver a especificar las directivas personalizadas de las entidades de certificación que existen en versiones anteriores de .NET Framework en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="64494-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="64494-133">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento a una [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] no afecta al ensamblado [código transparente en seguridad](../../../../../docs/framework/misc/security-transparent-code.md); las reglas de transparencia se siguen aplican.</span><span class="sxs-lookup"><span data-stu-id="64494-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64494-134">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento puede producir reducciones de rendimiento importantes para los ensamblados de imagen nativa creados por el [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) que no están instalados en el [caché global de ensamblados ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="64494-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="64494-135">La degradación del rendimiento se debe a la imposibilidad de que el tiempo de ejecución para cargar los ensamblados como imágenes nativas cuando se aplica el atributo, lo que sus carga los ensamblados como just-in-time.</span><span class="sxs-lookup"><span data-stu-id="64494-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64494-136">Si especifica una versión de .NET Framework de destino es anterior a .NET Framework 4 en la configuración del proyecto para el proyecto de Visual Studio, se habilitará la directiva CAS, incluyendo cualquier directiva CAS personalizada especificada para esa versión.</span><span class="sxs-lookup"><span data-stu-id="64494-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="64494-137">Sin embargo, no podrá usar los nuevos tipos de .NET Framework 4 y miembros.</span><span class="sxs-lookup"><span data-stu-id="64494-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="64494-138">También puede especificar una versión anterior de .NET Framework mediante la [ \<supportedRuntime > elemento](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) en el esquema de configuración de inicio en su [archivo de configuración de aplicación](../../../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="64494-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64494-139">Sintaxis del archivo de configuración distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="64494-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="64494-140">Debe usar la sintaxis que se proporciona en las secciones de sintaxis y ejemplo.</span><span class="sxs-lookup"><span data-stu-id="64494-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="64494-141">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="64494-141">Configuration File</span></span>  
 <span data-ttu-id="64494-142">Este elemento se puede usar solo en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64494-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64494-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64494-143">Example</span></span>  
 <span data-ttu-id="64494-144">El ejemplo siguiente muestra cómo se habilita la directiva CAS heredada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="64494-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="64494-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="64494-145">See also</span></span>

- [<span data-ttu-id="64494-146">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="64494-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="64494-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="64494-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
