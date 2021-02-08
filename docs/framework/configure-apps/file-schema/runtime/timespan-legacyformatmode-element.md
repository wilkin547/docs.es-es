---
description: 'Más información acerca de: <TimeSpan_LegacyFormatMode elemento>'
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
ms.openlocfilehash: 1fa5c3a15941004ebab9e3622d4b3e7b27130e22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802390"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="237bb-103">\<TimeSpan_LegacyFormatMode> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="237bb-103">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="237bb-104">Determina si el tiempo de ejecución conserva el comportamiento heredado en operaciones de formato con <xref:System.TimeSpan?displayProperty=nameWithType> valores.</span><span class="sxs-lookup"><span data-stu-id="237bb-104">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a><span data-ttu-id="237bb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="237bb-105">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="237bb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="237bb-106">Attributes and Elements</span></span>

<span data-ttu-id="237bb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="237bb-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="237bb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="237bb-108">Attributes</span></span>

|<span data-ttu-id="237bb-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="237bb-109">Attribute</span></span>|<span data-ttu-id="237bb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="237bb-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="237bb-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="237bb-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="237bb-112">Especifica si el Runtime usa el comportamiento de formato heredado con <xref:System.TimeSpan?displayProperty=nameWithType> valores.</span><span class="sxs-lookup"><span data-stu-id="237bb-112">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="237bb-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="237bb-113">enabled Attribute</span></span>

|<span data-ttu-id="237bb-114">Value</span><span class="sxs-lookup"><span data-stu-id="237bb-114">Value</span></span>|<span data-ttu-id="237bb-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="237bb-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="237bb-116">El motor en tiempo de ejecución no restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="237bb-116">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="237bb-117">El motor en tiempo de ejecución restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="237bb-117">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="237bb-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="237bb-118">Child Elements</span></span>

<span data-ttu-id="237bb-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="237bb-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="237bb-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="237bb-120">Parent Elements</span></span>

|<span data-ttu-id="237bb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="237bb-121">Element</span></span>|<span data-ttu-id="237bb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="237bb-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="237bb-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="237bb-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="237bb-124">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="237bb-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="237bb-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="237bb-125">Remarks</span></span>

<span data-ttu-id="237bb-126">A partir de la .NET Framework 4, la <xref:System.TimeSpan?displayProperty=nameWithType> estructura implementa la <xref:System.IFormattable> interfaz y admite operaciones de formato con cadenas de formato estándar y personalizadas.</span><span class="sxs-lookup"><span data-stu-id="237bb-126">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="237bb-127">Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce una excepción <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="237bb-127">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="237bb-128">En versiones anteriores del .NET Framework, la <xref:System.TimeSpan> estructura no implementaba <xref:System.IFormattable> y no admitía cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="237bb-128">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="237bb-129">Sin embargo, muchos desarrolladores suponían erróneamente que <xref:System.TimeSpan> admiten un conjunto de cadenas de formato y las usaban en [operaciones de formato compuesto](../../../../standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="237bb-129">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="237bb-130">Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con cadenas de formato no admitidas normalmente producen una excepción <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="237bb-130">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="237bb-131">Sin embargo, dado <xref:System.TimeSpan> que no implementó <xref:System.IFormattable> , el tiempo de ejecución omitió la cadena de formato y, en su lugar, llamó al <xref:System.TimeSpan.ToString?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="237bb-131">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="237bb-132">Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no da como resultado una <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="237bb-132">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="237bb-133">En los casos en que el código heredado pasa un método de formato compuesto y una cadena de formato no válida, y ese código no se puede volver a compilar, puede usar el `<TimeSpan_LegacyFormatMode>` elemento para restaurar el comportamiento heredado <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="237bb-133">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="237bb-134">Al establecer el `enabled` atributo de este elemento en `true` , el método de formato compuesto produce una llamada a en <xref:System.TimeSpan.ToString?displayProperty=nameWithType> lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> , y <xref:System.FormatException> no se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="237bb-134">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="237bb-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="237bb-135">Example</span></span>

<span data-ttu-id="237bb-136">En el ejemplo siguiente se crea una instancia de un <xref:System.TimeSpan> objeto y se intenta dar formato al <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> método mediante una cadena de formato estándar no compatible.</span><span class="sxs-lookup"><span data-stu-id="237bb-136">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="237bb-137">Al ejecutar el ejemplo en el .NET Framework 3,5 o en una versión anterior, se muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="237bb-137">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```console
12:30:45
```

<span data-ttu-id="237bb-138">Esto difiere notablemente de la salida si ejecuta el ejemplo en el .NET Framework 4 o una versión posterior:</span><span class="sxs-lookup"><span data-stu-id="237bb-138">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```console
Invalid Format
```

<span data-ttu-id="237bb-139">Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo en el .NET Framework 4 o una versión posterior, la salida es idéntica a la generada por el ejemplo cuando se ejecuta en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="237bb-139">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="237bb-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="237bb-140">See also</span></span>

- [<span data-ttu-id="237bb-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="237bb-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="237bb-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="237bb-142">Configuration File Schema</span></span>](../index.md)
