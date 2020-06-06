---
title: Elemento <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116249"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="59b50-102">\<NetFx40_LegacySecurityPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="59b50-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="59b50-103">Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.</span><span class="sxs-lookup"><span data-stu-id="59b50-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="59b50-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59b50-104">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="59b50-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59b50-105">Attributes and Elements</span></span>

<span data-ttu-id="59b50-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59b50-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="59b50-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="59b50-107">Attributes</span></span>

|<span data-ttu-id="59b50-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="59b50-108">Attribute</span></span>|<span data-ttu-id="59b50-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="59b50-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="59b50-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="59b50-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="59b50-111">Especifica si el Runtime usa una directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="59b50-111">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="59b50-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="59b50-112">enabled Attribute</span></span>

|<span data-ttu-id="59b50-113">Value</span><span class="sxs-lookup"><span data-stu-id="59b50-113">Value</span></span>|<span data-ttu-id="59b50-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="59b50-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="59b50-115">El runtime no utiliza la Directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="59b50-115">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="59b50-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="59b50-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="59b50-117">El Runtime usa una directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="59b50-117">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="59b50-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59b50-118">Child Elements</span></span>

<span data-ttu-id="59b50-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59b50-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="59b50-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59b50-120">Parent Elements</span></span>

|<span data-ttu-id="59b50-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="59b50-121">Element</span></span>|<span data-ttu-id="59b50-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="59b50-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="59b50-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59b50-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="59b50-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59b50-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="59b50-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59b50-125">Remarks</span></span>

<span data-ttu-id="59b50-126">En la versión 3,5 de .NET Framework y versiones anteriores, la Directiva CAS está siempre en vigor.</span><span class="sxs-lookup"><span data-stu-id="59b50-126">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="59b50-127">En el .NET Framework 4, la Directiva de CAS debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="59b50-127">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="59b50-128">La Directiva CAS es específica de la versión.</span><span class="sxs-lookup"><span data-stu-id="59b50-128">CAS policy is version-specific.</span></span> <span data-ttu-id="59b50-129">Las directivas de CA personalizadas que existen en versiones anteriores del .NET Framework deben reespecificarse en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="59b50-129">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="59b50-130">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento a un ensamblado de .NET Framework 4 no afecta al [código transparente en seguridad](../../../misc/security-transparent-code.md); las reglas de transparencia se siguen aplicando.</span><span class="sxs-lookup"><span data-stu-id="59b50-130">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59b50-131">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento puede dar lugar a penalizaciones de rendimiento significativas para los ensamblados de imagen nativa creados por el [generador de imágenes nativas (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) que no están instalados en la [caché global de ensamblados](../../../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="59b50-131">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="59b50-132">La degradación del rendimiento se debe a la incapacidad del tiempo de ejecución para cargar los ensamblados como imágenes nativas cuando se aplica el atributo, lo que da lugar a que se carguen como ensamblados Just-in-Time.</span><span class="sxs-lookup"><span data-stu-id="59b50-132">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="59b50-133">Si especifica una versión de .NET Framework de destino anterior a la .NET Framework 4 en la configuración del proyecto para el proyecto de Visual Studio, se habilitará la Directiva de CAS, incluidas las directivas CA personalizadas que haya especificado para esa versión.</span><span class="sxs-lookup"><span data-stu-id="59b50-133">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="59b50-134">Sin embargo, no podrá usar los nuevos tipos y miembros de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="59b50-134">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="59b50-135">También puede especificar una versión anterior del .NET Framework mediante el [ \<supportedRuntime> elemento](../startup/supportedruntime-element.md) del esquema de configuración de inicio en el archivo de [configuración](../../index.md)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59b50-135">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="59b50-136">La sintaxis del archivo de configuración distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="59b50-136">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="59b50-137">Debe utilizar la sintaxis que se proporciona en las secciones sintaxis y ejemplo.</span><span class="sxs-lookup"><span data-stu-id="59b50-137">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="59b50-138">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="59b50-138">Configuration File</span></span>

<span data-ttu-id="59b50-139">Este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59b50-139">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="59b50-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59b50-140">Example</span></span>

<span data-ttu-id="59b50-141">En el ejemplo siguiente se muestra cómo habilitar la Directiva CAS heredada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="59b50-141">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="59b50-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59b50-142">See also</span></span>

- [<span data-ttu-id="59b50-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="59b50-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="59b50-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="59b50-144">Configuration File Schema</span></span>](../index.md)
