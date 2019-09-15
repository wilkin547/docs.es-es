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
ms.openlocfilehash: 35b4c6201b5181b8d7241906f60a731e4175d523
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991234"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="dbecd-102">Elemento \<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="dbecd-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="dbecd-103">Especifica si se omitirá la validación de nombres seguros en ensamblados de plena confianza que se cargan en una <xref:System.AppDomain>plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dbecd-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="dbecd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dbecd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dbecd-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="dbecd-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="dbecd-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames>**</span><span class="sxs-lookup"><span data-stu-id="dbecd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dbecd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbecd-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dbecd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dbecd-108">Attributes and Elements</span></span>

<span data-ttu-id="dbecd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dbecd-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="dbecd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="dbecd-110">Attributes</span></span>

|<span data-ttu-id="dbecd-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="dbecd-111">Attribute</span></span>|<span data-ttu-id="dbecd-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dbecd-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="dbecd-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="dbecd-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="dbecd-114">Especifica si está habilitada la característica de omisión que evita la validación de nombres seguros para los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dbecd-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="dbecd-115">Cuando esta característica está habilitada, los nombres seguros no se validan para comprobar su exactitud cuando se carga el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dbecd-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="dbecd-116">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="dbecd-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="dbecd-117">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="dbecd-117">enabled Attribute</span></span>

|<span data-ttu-id="dbecd-118">Valor</span><span class="sxs-lookup"><span data-stu-id="dbecd-118">Value</span></span>|<span data-ttu-id="dbecd-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dbecd-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="dbecd-120">Las firmas de nombre seguro de los ensamblados de plena confianza no se validan cuando los ensamblados se cargan en <xref:System.AppDomain>una plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dbecd-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="dbecd-121">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="dbecd-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="dbecd-122">Las firmas de nombre seguro de los ensamblados de plena confianza se validan cuando los ensamblados se cargan en <xref:System.AppDomain>una plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dbecd-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="dbecd-123">La firma de nombre seguro se comprueba únicamente para comprobar la exactitud de la firma; no se compara con otro nombre seguro para buscar coincidencias.</span><span class="sxs-lookup"><span data-stu-id="dbecd-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="dbecd-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dbecd-124">Child Elements</span></span>

<span data-ttu-id="dbecd-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dbecd-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="dbecd-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dbecd-126">Parent Elements</span></span>

|<span data-ttu-id="dbecd-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbecd-127">Element</span></span>|<span data-ttu-id="dbecd-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dbecd-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="dbecd-129">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dbecd-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="dbecd-130">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="dbecd-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="dbecd-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbecd-131">Remarks</span></span>

<span data-ttu-id="dbecd-132">La característica de omisión de nombres seguros evita la sobrecarga de la comprobación de la firma de nombre seguro de los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dbecd-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="dbecd-133">La característica de omisión se aplica a cualquier ensamblado que esté firmado con un nombre seguro y que:</span><span class="sxs-lookup"><span data-stu-id="dbecd-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="dbecd-134">De plena confianza sin <xref:System.Security.Policy.StrongName> la evidencia (por ejemplo, `MyComputer` tiene evidencia de zona).</span><span class="sxs-lookup"><span data-stu-id="dbecd-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="dbecd-135">se cargue en un <xref:System.AppDomain> de plena confianza;</span><span class="sxs-lookup"><span data-stu-id="dbecd-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="dbecd-136">se cargue desde una ubicación en la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> de ese <xref:System.AppDomain>;</span><span class="sxs-lookup"><span data-stu-id="dbecd-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="dbecd-137">no tenga firma retrasada.</span><span class="sxs-lookup"><span data-stu-id="dbecd-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="dbecd-138">Si la característica de omisión se ha desactivado para todas las aplicaciones del equipo mediante una clave del registro, este valor del archivo de configuración no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="dbecd-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="dbecd-139">Para obtener más información, vea [Cómo: para deshabilitar la característica de omisión de nombres seguros](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="dbecd-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="dbecd-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbecd-140">Example</span></span>

<span data-ttu-id="dbecd-141">En el ejemplo siguiente se muestra cómo especificar el comportamiento que valida la firma de nombre seguro en los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="dbecd-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="dbecd-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbecd-142">See also</span></span>

- [<span data-ttu-id="dbecd-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="dbecd-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dbecd-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="dbecd-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dbecd-145">Cómo: Deshabilitar la característica de omisión de nombres seguros</span><span class="sxs-lookup"><span data-stu-id="dbecd-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
