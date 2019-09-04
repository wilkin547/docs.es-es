---
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64bf667c5c9bc20db14f08f18fa6f4f84fa12a24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252250"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="cfe92-102">\<TimeSpan_LegacyFormatMode >, elemento</span><span class="sxs-lookup"><span data-stu-id="cfe92-102">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="cfe92-103">Determina si el tiempo de ejecución conserva el comportamiento heredado en operaciones <xref:System.TimeSpan?displayProperty=nameWithType> de formato con valores.</span><span class="sxs-lookup"><span data-stu-id="cfe92-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

<span data-ttu-id="cfe92-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfe92-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cfe92-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="cfe92-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="cfe92-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> TimeSpan_LegacyFormatMode**</span><span class="sxs-lookup"><span data-stu-id="cfe92-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="cfe92-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfe92-107">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cfe92-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cfe92-108">Attributes and Elements</span></span>

<span data-ttu-id="cfe92-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cfe92-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cfe92-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="cfe92-110">Attributes</span></span>

|<span data-ttu-id="cfe92-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="cfe92-111">Attribute</span></span>|<span data-ttu-id="cfe92-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfe92-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="cfe92-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="cfe92-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="cfe92-114">Especifica si el Runtime usa el comportamiento de formato <xref:System.TimeSpan?displayProperty=nameWithType> heredado con valores.</span><span class="sxs-lookup"><span data-stu-id="cfe92-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="cfe92-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="cfe92-115">enabled Attribute</span></span>

|<span data-ttu-id="cfe92-116">Valor</span><span class="sxs-lookup"><span data-stu-id="cfe92-116">Value</span></span>|<span data-ttu-id="cfe92-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfe92-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="cfe92-118">El motor en tiempo de ejecución no restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="cfe92-118">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="cfe92-119">El motor en tiempo de ejecución restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="cfe92-119">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cfe92-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cfe92-120">Child Elements</span></span>

<span data-ttu-id="cfe92-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cfe92-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cfe92-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cfe92-122">Parent Elements</span></span>

|<span data-ttu-id="cfe92-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="cfe92-123">Element</span></span>|<span data-ttu-id="cfe92-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cfe92-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="cfe92-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cfe92-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="cfe92-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cfe92-126">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cfe92-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cfe92-127">Remarks</span></span>

<span data-ttu-id="cfe92-128">A partir de la .NET Framework 4, <xref:System.TimeSpan?displayProperty=nameWithType> la estructura implementa la <xref:System.IFormattable> interfaz y admite operaciones de formato con cadenas de formato estándar y personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cfe92-128">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="cfe92-129">Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce una <xref:System.FormatException>excepción.</span><span class="sxs-lookup"><span data-stu-id="cfe92-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="cfe92-130">En versiones anteriores del .NET Framework, la <xref:System.TimeSpan> estructura no implementaba <xref:System.IFormattable> y no admitía cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="cfe92-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="cfe92-131">Sin embargo, muchos desarrolladores suponían erróneamente que <xref:System.TimeSpan> admiten un conjunto de cadenas de formato y las usaban en operaciones de [formato compuesto](../../../../standard/base-types/composite-formatting.md) <xref:System.String.Format%2A?displayProperty=nameWithType>con métodos como.</span><span class="sxs-lookup"><span data-stu-id="cfe92-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cfe92-132">Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con cadenas de formato no admitidas normalmente producen una <xref:System.FormatException>excepción.</span><span class="sxs-lookup"><span data-stu-id="cfe92-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="cfe92-133">Sin embargo, <xref:System.TimeSpan> dado que no <xref:System.IFormattable>implementó, el tiempo de ejecución omitió la cadena de <xref:System.TimeSpan.ToString?displayProperty=nameWithType> formato y, en su lugar, llamó al método.</span><span class="sxs-lookup"><span data-stu-id="cfe92-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cfe92-134">Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no da <xref:System.FormatException>como resultado una.</span><span class="sxs-lookup"><span data-stu-id="cfe92-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="cfe92-135">En los casos en que el código heredado pasa un método de formato compuesto y una cadena de formato no válida, y ese código no se puede `<TimeSpan_LegacyFormatMode>` volver a compilar <xref:System.TimeSpan> , puede usar el elemento para restaurar el comportamiento heredado.</span><span class="sxs-lookup"><span data-stu-id="cfe92-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="cfe92-136">Al establecer `enabled` el atributo de este elemento en <xref:System.TimeSpan.ToString?displayProperty=nameWithType> `true`, el método de formato compuesto produce una llamada a en lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, y no <xref:System.FormatException> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="cfe92-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="cfe92-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cfe92-137">Example</span></span>

<span data-ttu-id="cfe92-138">En el ejemplo siguiente se <xref:System.TimeSpan> <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> crea una instancia de un objeto y se intenta dar formato al método mediante una cadena de formato estándar no compatible.</span><span class="sxs-lookup"><span data-stu-id="cfe92-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="cfe92-139">Al ejecutar el ejemplo en el .NET Framework 3,5 o en una versión anterior, se muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cfe92-139">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```
12:30:45
```

<span data-ttu-id="cfe92-140">Esto difiere notablemente de la salida si ejecuta el ejemplo en el .NET Framework 4 o una versión posterior:</span><span class="sxs-lookup"><span data-stu-id="cfe92-140">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```
Invalid Format
```

<span data-ttu-id="cfe92-141">Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo en el .NET Framework 4 o una versión posterior, la salida es idéntica a la generada por el ejemplo cuando se ejecuta en .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="cfe92-141">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cfe92-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfe92-142">See also</span></span>

- [<span data-ttu-id="cfe92-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="cfe92-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cfe92-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="cfe92-144">Configuration File Schema</span></span>](../index.md)
