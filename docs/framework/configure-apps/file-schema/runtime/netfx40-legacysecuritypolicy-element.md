---
description: 'Más información acerca de: <NetFx40_LegacySecurityPolicy elemento>'
title: Elemento <NetFx40_LegacySecurityPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: 6be520d4cfd4f9ec05f4aceec82e4fef5440f55d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782317"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="ec739-103">\<NetFx40_LegacySecurityPolicy> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="ec739-103">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="ec739-104">Especifica si el runtime usa la directiva de seguridad de acceso al código (CAS) heredada.</span><span class="sxs-lookup"><span data-stu-id="ec739-104">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="ec739-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec739-105">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ec739-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ec739-106">Attributes and Elements</span></span>

<span data-ttu-id="ec739-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ec739-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ec739-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ec739-108">Attributes</span></span>

|<span data-ttu-id="ec739-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="ec739-109">Attribute</span></span>|<span data-ttu-id="ec739-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec739-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ec739-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ec739-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="ec739-112">Especifica si el Runtime usa una directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="ec739-112">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="ec739-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="ec739-113">enabled Attribute</span></span>

|<span data-ttu-id="ec739-114">Value</span><span class="sxs-lookup"><span data-stu-id="ec739-114">Value</span></span>|<span data-ttu-id="ec739-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec739-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="ec739-116">El runtime no utiliza la Directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="ec739-116">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="ec739-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ec739-117">This is the default.</span></span>|
|`true`|<span data-ttu-id="ec739-118">El Runtime usa una directiva CAS heredada.</span><span class="sxs-lookup"><span data-stu-id="ec739-118">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ec739-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ec739-119">Child Elements</span></span>

<span data-ttu-id="ec739-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ec739-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ec739-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ec739-121">Parent Elements</span></span>

|<span data-ttu-id="ec739-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ec739-122">Element</span></span>|<span data-ttu-id="ec739-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="ec739-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ec739-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec739-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ec739-125">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ec739-125">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ec739-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ec739-126">Remarks</span></span>

<span data-ttu-id="ec739-127">En la versión 3,5 de .NET Framework y versiones anteriores, la Directiva CAS está siempre en vigor.</span><span class="sxs-lookup"><span data-stu-id="ec739-127">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="ec739-128">En el .NET Framework 4, la Directiva de CAS debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="ec739-128">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="ec739-129">La Directiva CAS es específica de la versión.</span><span class="sxs-lookup"><span data-stu-id="ec739-129">CAS policy is version-specific.</span></span> <span data-ttu-id="ec739-130">Las directivas de CA personalizadas que existen en versiones anteriores del .NET Framework deben reespecificarse en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ec739-130">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="ec739-131">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento a un ensamblado de .NET Framework 4 no afecta al [código transparente en seguridad](../../../misc/security-transparent-code.md); las reglas de transparencia se siguen aplicando.</span><span class="sxs-lookup"><span data-stu-id="ec739-131">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ec739-132">Aplicar el `<NetFx40_LegacySecurityPolicy>` elemento puede dar lugar a penalizaciones de rendimiento significativas para los ensamblados de imagen nativa creados por el [generador de imágenes nativas (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) que no están instalados en la [caché global de ensamblados](../../../app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="ec739-132">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="ec739-133">La degradación del rendimiento se debe a la incapacidad del tiempo de ejecución para cargar los ensamblados como imágenes nativas cuando se aplica el atributo, lo que da lugar a que se carguen como ensamblados Just-in-Time.</span><span class="sxs-lookup"><span data-stu-id="ec739-133">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="ec739-134">Si especifica una versión de .NET Framework de destino anterior a la .NET Framework 4 en la configuración del proyecto para el proyecto de Visual Studio, se habilitará la Directiva de CAS, incluidas las directivas CA personalizadas que haya especificado para esa versión.</span><span class="sxs-lookup"><span data-stu-id="ec739-134">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="ec739-135">Sin embargo, no podrá usar los nuevos tipos y miembros de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ec739-135">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="ec739-136">También puede especificar una versión anterior del .NET Framework mediante el [ \<supportedRuntime> elemento](../startup/supportedruntime-element.md) del esquema de configuración de inicio en el archivo de [configuración](../../index.md)de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec739-136">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ec739-137">La sintaxis del archivo de configuración distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ec739-137">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="ec739-138">Debe utilizar la sintaxis que se proporciona en las secciones sintaxis y ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ec739-138">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="ec739-139">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ec739-139">Configuration File</span></span>

<span data-ttu-id="ec739-140">Este elemento solo se puede usar en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec739-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="ec739-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec739-141">Example</span></span>

<span data-ttu-id="ec739-142">En el ejemplo siguiente se muestra cómo habilitar la Directiva CAS heredada para una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec739-142">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ec739-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec739-143">See also</span></span>

- [<span data-ttu-id="ec739-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="ec739-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ec739-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ec739-145">Configuration File Schema</span></span>](../index.md)
