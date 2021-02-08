---
description: 'Más información acerca de: <NetFx45_CultureAwareComparerGetHashCode_LongStrings elemento>'
title: Elemento <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: ca4099d3bf812cb25e6a611b9b51b3752b1ad361
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782291"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="3085c-103">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="3085c-103">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="3085c-104">Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3085c-104">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**  

## <a name="syntax"></a><span data-ttu-id="3085c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3085c-105">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3085c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3085c-106">Attributes and Elements</span></span>

<span data-ttu-id="3085c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3085c-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3085c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3085c-108">Attributes</span></span>

|<span data-ttu-id="3085c-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="3085c-109">Attribute</span></span>|<span data-ttu-id="3085c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3085c-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="3085c-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3085c-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="3085c-112">Especifica si Common Language Runtime asigna una cantidad de memoria fija al calcular códigos hash.</span><span class="sxs-lookup"><span data-stu-id="3085c-112">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="3085c-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="3085c-113">enabled Attribute</span></span>

|<span data-ttu-id="3085c-114">Value</span><span class="sxs-lookup"><span data-stu-id="3085c-114">Value</span></span>|<span data-ttu-id="3085c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3085c-115">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="3085c-116">0</span><span class="sxs-lookup"><span data-stu-id="3085c-116">0</span></span>|<span data-ttu-id="3085c-117">Common Language Runtime asigna una cantidad de memoria variable para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="3085c-117">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="3085c-118">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3085c-118">This is the default.</span></span>|
|<span data-ttu-id="3085c-119">1</span><span class="sxs-lookup"><span data-stu-id="3085c-119">1</span></span>|<span data-ttu-id="3085c-120">Common Language Runtime asigna una cantidad de memoria fija para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.</span><span class="sxs-lookup"><span data-stu-id="3085c-120">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3085c-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3085c-121">Child Elements</span></span>

<span data-ttu-id="3085c-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3085c-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3085c-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3085c-123">Parent Elements</span></span>

|<span data-ttu-id="3085c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3085c-124">Element</span></span>|<span data-ttu-id="3085c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3085c-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3085c-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3085c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="3085c-127">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3085c-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3085c-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3085c-128">Remarks</span></span>

<span data-ttu-id="3085c-129">De forma predeterminada, Common Language Runtime asigna una cantidad de memoria variable para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> y puede que se inicie una excepción <xref:System.ArgumentException> cuando el método intenta calcular el código hash de cadenas muy grandes (con millones de caracteres o más).</span><span class="sxs-lookup"><span data-stu-id="3085c-129">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="3085c-130">Al agregar este elemento a un archivo de configuración de la aplicación y establecer su atributo `enabled` en "1", puede especificar que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> use un algoritmo alternativo que asigne una cantidad de memoria fija para el cálculo de códigos hash.</span><span class="sxs-lookup"><span data-stu-id="3085c-130">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3085c-131">El `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` elemento no se utiliza en Windows 8 ni en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="3085c-131">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="3085c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3085c-132">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3085c-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3085c-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3085c-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="3085c-134">Configuration File Schema</span></span>](../index.md)
