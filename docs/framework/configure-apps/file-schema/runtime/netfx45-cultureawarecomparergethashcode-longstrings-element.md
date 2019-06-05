---
title: Elemento <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23917977add2343732957eaa8dad5d2176315acf
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689860"
---
# <a name="netfx45cultureawarecomparergethashcodelongstrings-element"></a><span data-ttu-id="6d34d-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > elemento</span><span class="sxs-lookup"><span data-stu-id="6d34d-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="6d34d-103">Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6d34d-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6d34d-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="6d34d-104">\<configuration>\\</span></span>
<span data-ttu-id="6d34d-105">\<runtime>\\</span><span class="sxs-lookup"><span data-stu-id="6d34d-105">\<runtime>\\</span></span>
<span data-ttu-id="6d34d-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span><span class="sxs-lookup"><span data-stu-id="6d34d-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>

## <a name="syntax"></a><span data-ttu-id="6d34d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d34d-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6d34d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6d34d-108">Attributes and Elements</span></span>

<span data-ttu-id="6d34d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6d34d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6d34d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6d34d-110">Attributes</span></span>

|<span data-ttu-id="6d34d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6d34d-111">Attribute</span></span>|<span data-ttu-id="6d34d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d34d-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="6d34d-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6d34d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="6d34d-114">Especifica si Common Language Runtime asigna una cantidad de memoria fija al calcular códigos hash.</span><span class="sxs-lookup"><span data-stu-id="6d34d-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="6d34d-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="6d34d-115">enabled Attribute</span></span>

|<span data-ttu-id="6d34d-116">Valor</span><span class="sxs-lookup"><span data-stu-id="6d34d-116">Value</span></span>|<span data-ttu-id="6d34d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d34d-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="6d34d-118">0</span><span class="sxs-lookup"><span data-stu-id="6d34d-118">0</span></span>|<span data-ttu-id="6d34d-119">Common Language Runtime asigna una cantidad de memoria variable para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="6d34d-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="6d34d-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6d34d-120">This is the default.</span></span>|
|<span data-ttu-id="6d34d-121">1</span><span class="sxs-lookup"><span data-stu-id="6d34d-121">1</span></span>|<span data-ttu-id="6d34d-122">Common Language Runtime asigna una cantidad de memoria fija para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="6d34d-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6d34d-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6d34d-123">Child Elements</span></span>

<span data-ttu-id="6d34d-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6d34d-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6d34d-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6d34d-125">Parent Elements</span></span>

|<span data-ttu-id="6d34d-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d34d-126">Element</span></span>|<span data-ttu-id="6d34d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d34d-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6d34d-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d34d-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="6d34d-129">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6d34d-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6d34d-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d34d-130">Remarks</span></span>

<span data-ttu-id="6d34d-131">De forma predeterminada, Common Language Runtime asigna una cantidad de memoria variable para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> y puede que se inicie una excepción <xref:System.ArgumentException> cuando el método intenta calcular el código hash de cadenas muy grandes (con millones de caracteres o más).</span><span class="sxs-lookup"><span data-stu-id="6d34d-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="6d34d-132">Al agregar este elemento a un archivo de configuración de la aplicación y establecer su atributo `enabled` en "1", puede especificar que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> use un algoritmo alternativo que asigne una cantidad de memoria fija para el cálculo de códigos hash.</span><span class="sxs-lookup"><span data-stu-id="6d34d-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d34d-133">El elemento `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` no se usa en [!INCLUDE[win8](../../../../../includes/win8-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6d34d-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d34d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d34d-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6d34d-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="6d34d-135">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6d34d-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6d34d-136">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
