---
title: <bypassTrustedAppStrongNames> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739086"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="64928-102">\<bypassTrustedAppStrongNames> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="64928-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="64928-103">Especifica si se omitirá la validación de nombres seguros en ensamblados de plena confianza que se cargan en una plena confianza <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="64928-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a><span data-ttu-id="64928-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64928-104">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64928-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64928-105">Attributes and Elements</span></span>

<span data-ttu-id="64928-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="64928-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="64928-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="64928-107">Attributes</span></span>

|<span data-ttu-id="64928-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="64928-108">Attribute</span></span>|<span data-ttu-id="64928-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="64928-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="64928-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="64928-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="64928-111">Especifica si está habilitada la característica de omisión que evita la validación de nombres seguros para los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="64928-111">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="64928-112">Cuando esta característica está habilitada, los nombres seguros no se validan para comprobar su exactitud cuando se carga el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="64928-112">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="64928-113">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="64928-113">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="64928-114">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="64928-114">enabled Attribute</span></span>

|<span data-ttu-id="64928-115">Value</span><span class="sxs-lookup"><span data-stu-id="64928-115">Value</span></span>|<span data-ttu-id="64928-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="64928-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="64928-117">Las firmas de nombre seguro de los ensamblados de plena confianza no se validan cuando los ensamblados se cargan en una plena confianza <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="64928-117">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="64928-118">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="64928-118">This is the default.</span></span>|
|`false`|<span data-ttu-id="64928-119">Las firmas de nombre seguro de los ensamblados de plena confianza se validan cuando los ensamblados se cargan en una plena confianza <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="64928-119">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="64928-120">La firma de nombre seguro se comprueba únicamente para comprobar la exactitud de la firma; no se compara con otro nombre seguro para buscar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="64928-120">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="64928-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64928-121">Child Elements</span></span>

<span data-ttu-id="64928-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="64928-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="64928-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64928-123">Parent Elements</span></span>

|<span data-ttu-id="64928-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="64928-124">Element</span></span>|<span data-ttu-id="64928-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="64928-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="64928-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64928-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="64928-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="64928-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="64928-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64928-128">Remarks</span></span>

<span data-ttu-id="64928-129">La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de la firma de nombre seguro de los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="64928-129">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="64928-130">La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:</span><span class="sxs-lookup"><span data-stu-id="64928-130">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="64928-131">De plena confianza sin la <xref:System.Security.Policy.StrongName> evidencia (por ejemplo, tiene `MyComputer` evidencia de zona).</span><span class="sxs-lookup"><span data-stu-id="64928-131">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="64928-132">se cargue en un <xref:System.AppDomain> de plena confianza;</span><span class="sxs-lookup"><span data-stu-id="64928-132">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="64928-133">se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="64928-133">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="64928-134">no tenga firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="64928-134">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="64928-135">Si la característica de omisión se ha desactivado para todas las aplicaciones del equipo mediante una clave del registro, este valor del archivo de configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="64928-135">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="64928-136">Para obtener más información, consulte [Cómo: deshabilitar la característica de omisión de nombres seguros](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="64928-136">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="64928-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64928-137">Example</span></span>

<span data-ttu-id="64928-138">En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="64928-138">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="64928-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64928-139">See also</span></span>

- [<span data-ttu-id="64928-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="64928-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="64928-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="64928-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="64928-142">Cómo: Deshabilitar la característica de omisión de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="64928-142">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
