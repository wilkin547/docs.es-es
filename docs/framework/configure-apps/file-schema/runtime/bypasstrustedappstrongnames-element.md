---
description: 'Más información acerca de: <bypassTrustedAppStrongNames> elemento'
title: <bypassTrustedAppStrongNames> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: d23b9efa19481027480f2a1c7dab22bc97a05e13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719167"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="0e19f-103">\<bypassTrustedAppStrongNames> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="0e19f-103">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="0e19f-104">Especifica si se omitirá la validación de nombres seguros en ensamblados de plena confianza que se cargan en una plena confianza <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="0e19f-104">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a><span data-ttu-id="0e19f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e19f-105">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0e19f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e19f-106">Attributes and Elements</span></span>

<span data-ttu-id="0e19f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0e19f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e19f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e19f-108">Attributes</span></span>

|<span data-ttu-id="0e19f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="0e19f-109">Attribute</span></span>|<span data-ttu-id="0e19f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e19f-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0e19f-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0e19f-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="0e19f-112">Especifica si está habilitada la característica de omisión que evita la validación de nombres seguros para los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0e19f-112">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="0e19f-113">Cuando esta característica está habilitada, los nombres seguros no se validan para comprobar su exactitud cuando se carga el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0e19f-113">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="0e19f-114">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="0e19f-114">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="0e19f-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="0e19f-115">enabled Attribute</span></span>

|<span data-ttu-id="0e19f-116">Value</span><span class="sxs-lookup"><span data-stu-id="0e19f-116">Value</span></span>|<span data-ttu-id="0e19f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e19f-117">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="0e19f-118">Las firmas de nombre seguro de los ensamblados de plena confianza no se validan cuando los ensamblados se cargan en una plena confianza <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="0e19f-118">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="0e19f-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0e19f-119">This is the default.</span></span>|
|`false`|<span data-ttu-id="0e19f-120">Las firmas de nombre seguro de los ensamblados de plena confianza se validan cuando los ensamblados se cargan en una plena confianza <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="0e19f-120">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="0e19f-121">La firma de nombre seguro se comprueba únicamente para comprobar la exactitud de la firma; no se compara con otro nombre seguro para buscar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="0e19f-121">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0e19f-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e19f-122">Child Elements</span></span>

<span data-ttu-id="0e19f-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0e19f-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0e19f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e19f-124">Parent Elements</span></span>

|<span data-ttu-id="0e19f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e19f-125">Element</span></span>|<span data-ttu-id="0e19f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e19f-126">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0e19f-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e19f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0e19f-128">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0e19f-128">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0e19f-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e19f-129">Remarks</span></span>

<span data-ttu-id="0e19f-130">La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de la firma de nombre seguro de los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0e19f-130">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="0e19f-131">La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:</span><span class="sxs-lookup"><span data-stu-id="0e19f-131">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="0e19f-132">De plena confianza sin la <xref:System.Security.Policy.StrongName> evidencia (por ejemplo, tiene `MyComputer` evidencia de zona).</span><span class="sxs-lookup"><span data-stu-id="0e19f-132">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="0e19f-133">se cargue en un <xref:System.AppDomain> de plena confianza;</span><span class="sxs-lookup"><span data-stu-id="0e19f-133">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="0e19f-134">se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="0e19f-134">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="0e19f-135">no tenga firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="0e19f-135">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="0e19f-136">Si la característica de omisión se ha desactivado para todas las aplicaciones del equipo mediante una clave del registro, este valor del archivo de configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="0e19f-136">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="0e19f-137">Para obtener más información, consulte [Cómo: deshabilitar la característica de omisión de Strong-Name](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="0e19f-137">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="0e19f-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e19f-138">Example</span></span>

<span data-ttu-id="0e19f-139">En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="0e19f-139">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0e19f-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e19f-140">See also</span></span>

- [<span data-ttu-id="0e19f-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0e19f-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0e19f-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0e19f-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0e19f-143">Cómo: Deshabilitar la característica de omisión de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="0e19f-143">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
