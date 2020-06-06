---
title: Elemento <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 413eb6c6e61b509135601c65cf045eabd849e8b3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802119"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="12d3f-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="12d3f-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="12d3f-103">Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="12d3f-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**  

## <a name="syntax"></a><span data-ttu-id="12d3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12d3f-104">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="12d3f-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="12d3f-105">Attributes and Elements</span></span>

<span data-ttu-id="12d3f-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="12d3f-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="12d3f-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="12d3f-107">Attributes</span></span>

|<span data-ttu-id="12d3f-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="12d3f-108">Attribute</span></span>|<span data-ttu-id="12d3f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d3f-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="12d3f-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="12d3f-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="12d3f-111">Especifica si Common Language Runtime asigna una cantidad de memoria fija al calcular códigos hash.</span><span class="sxs-lookup"><span data-stu-id="12d3f-111">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="12d3f-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="12d3f-112">enabled Attribute</span></span>

|<span data-ttu-id="12d3f-113">Value</span><span class="sxs-lookup"><span data-stu-id="12d3f-113">Value</span></span>|<span data-ttu-id="12d3f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d3f-114">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="12d3f-115">0</span><span class="sxs-lookup"><span data-stu-id="12d3f-115">0</span></span>|<span data-ttu-id="12d3f-116">Common Language Runtime asigna una cantidad de memoria variable para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="12d3f-116">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="12d3f-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="12d3f-117">This is the default.</span></span>|
|<span data-ttu-id="12d3f-118">1</span><span class="sxs-lookup"><span data-stu-id="12d3f-118">1</span></span>|<span data-ttu-id="12d3f-119">Common Language Runtime asigna una cantidad de memoria fija para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="12d3f-119">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="12d3f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="12d3f-120">Child Elements</span></span>

<span data-ttu-id="12d3f-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="12d3f-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="12d3f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="12d3f-122">Parent Elements</span></span>

|<span data-ttu-id="12d3f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="12d3f-123">Element</span></span>|<span data-ttu-id="12d3f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d3f-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="12d3f-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12d3f-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="12d3f-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="12d3f-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12d3f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12d3f-127">Remarks</span></span>

<span data-ttu-id="12d3f-128">De forma predeterminada, Common Language Runtime asigna una cantidad de memoria variable para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> y puede que se inicie una excepción <xref:System.ArgumentException> cuando el método intenta calcular el código hash de cadenas muy grandes (con millones de caracteres o más).</span><span class="sxs-lookup"><span data-stu-id="12d3f-128">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="12d3f-129">Al agregar este elemento a un archivo de configuración de la aplicación y establecer su atributo `enabled` en "1", puede especificar que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> use un algoritmo alternativo que asigne una cantidad de memoria fija para el cálculo de códigos hash.</span><span class="sxs-lookup"><span data-stu-id="12d3f-129">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12d3f-130">El `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` elemento no se utiliza en Windows 8 ni en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="12d3f-130">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="12d3f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12d3f-131">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="12d3f-132">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="12d3f-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="12d3f-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="12d3f-133">Configuration File Schema</span></span>](../index.md)
