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
ms.openlocfilehash: bd59d1bcc489f248cbeb397afffb638071df17b6
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663586"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="05071-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >, elemento</span><span class="sxs-lookup"><span data-stu-id="05071-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="05071-103">Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="05071-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="05071-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="05071-104">\<configuration></span></span>\
<span data-ttu-id="05071-105">\<> en tiempo de ejecución </span><span class="sxs-lookup"><span data-stu-id="05071-105">\<runtime></span></span>\
<span data-ttu-id="05071-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span><span class="sxs-lookup"><span data-stu-id="05071-106">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings></span></span>

## <a name="syntax"></a><span data-ttu-id="05071-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05071-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="05071-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="05071-108">Attributes and Elements</span></span>

<span data-ttu-id="05071-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="05071-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="05071-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="05071-110">Attributes</span></span>

|<span data-ttu-id="05071-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="05071-111">Attribute</span></span>|<span data-ttu-id="05071-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="05071-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="05071-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="05071-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="05071-114">Especifica si Common Language Runtime asigna una cantidad de memoria fija al calcular códigos hash.</span><span class="sxs-lookup"><span data-stu-id="05071-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="05071-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="05071-115">enabled Attribute</span></span>

|<span data-ttu-id="05071-116">Valor</span><span class="sxs-lookup"><span data-stu-id="05071-116">Value</span></span>|<span data-ttu-id="05071-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="05071-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="05071-118">0</span><span class="sxs-lookup"><span data-stu-id="05071-118">0</span></span>|<span data-ttu-id="05071-119">Common Language Runtime asigna una cantidad de memoria variable para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="05071-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="05071-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="05071-120">This is the default.</span></span>|
|<span data-ttu-id="05071-121">1</span><span class="sxs-lookup"><span data-stu-id="05071-121">1</span></span>|<span data-ttu-id="05071-122">Common Language Runtime asigna una cantidad de memoria fija para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="05071-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="05071-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="05071-123">Child Elements</span></span>

<span data-ttu-id="05071-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="05071-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="05071-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="05071-125">Parent Elements</span></span>

|<span data-ttu-id="05071-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="05071-126">Element</span></span>|<span data-ttu-id="05071-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="05071-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="05071-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05071-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="05071-129">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05071-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="05071-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05071-130">Remarks</span></span>

<span data-ttu-id="05071-131">De forma predeterminada, Common Language Runtime asigna una cantidad de memoria variable para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> y puede que se inicie una excepción <xref:System.ArgumentException> cuando el método intenta calcular el código hash de cadenas muy grandes (con millones de caracteres o más).</span><span class="sxs-lookup"><span data-stu-id="05071-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="05071-132">Al agregar este elemento a un archivo de configuración de la aplicación y establecer su atributo `enabled` en "1", puede especificar que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> use un algoritmo alternativo que asigne una cantidad de memoria fija para el cálculo de códigos hash.</span><span class="sxs-lookup"><span data-stu-id="05071-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05071-133">El elemento `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` no se usa en [!INCLUDE[win8](../../../../../includes/win8-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="05071-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in [!INCLUDE[win8](../../../../../includes/win8-md.md)] and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="05071-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="05071-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="05071-135">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="05071-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="05071-136">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="05071-136">Configuration File Schema</span></span>](../index.md)
