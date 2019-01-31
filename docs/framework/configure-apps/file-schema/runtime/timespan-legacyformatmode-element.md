---
title: Elemento < TimeSpan_LegacyFormatMode >
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
ms.openlocfilehash: f3f18d5e62f4986f880b35825d8e0239dba8d4c6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277750"
---
# <a name="timespanlegacyformatmode-element"></a><span data-ttu-id="d71e9-102">\<TimeSpan_LegacyFormatMode > elemento</span><span class="sxs-lookup"><span data-stu-id="d71e9-102">\<TimeSpan_LegacyFormatMode> Element</span></span>
<span data-ttu-id="d71e9-103">Determina si el runtime conserva el comportamiento heredado para dar formato a las operaciones con <xref:System.TimeSpan?displayProperty=nameWithType> valores.</span><span class="sxs-lookup"><span data-stu-id="d71e9-103">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>  
  
 <span data-ttu-id="d71e9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d71e9-104">\<configuration></span></span>  
<span data-ttu-id="d71e9-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d71e9-105">\<runtime></span></span>  
<span data-ttu-id="d71e9-106"><TimeSpan_LegacyFormatMode></span><span class="sxs-lookup"><span data-stu-id="d71e9-106"><TimeSpan_LegacyFormatMode></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d71e9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d71e9-107">Syntax</span></span>  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d71e9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d71e9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d71e9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d71e9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d71e9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="d71e9-110">Attributes</span></span>  
  
|<span data-ttu-id="d71e9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="d71e9-111">Attribute</span></span>|<span data-ttu-id="d71e9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d71e9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d71e9-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d71e9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d71e9-114">Especifica si el runtime usa el comportamiento de formato heredado con <xref:System.TimeSpan?displayProperty=nameWithType> valores.</span><span class="sxs-lookup"><span data-stu-id="d71e9-114">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="d71e9-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="d71e9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d71e9-116">Valor</span><span class="sxs-lookup"><span data-stu-id="d71e9-116">Value</span></span>|<span data-ttu-id="d71e9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d71e9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="d71e9-118">El tiempo de ejecución no restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="d71e9-118">The runtime does not restore legacy formatting behavior.</span></span>|  
|`true`|<span data-ttu-id="d71e9-119">El runtime restaura el comportamiento de formato heredado.</span><span class="sxs-lookup"><span data-stu-id="d71e9-119">The runtime restores legacy formatting behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d71e9-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d71e9-120">Child Elements</span></span>  
 <span data-ttu-id="d71e9-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d71e9-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d71e9-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d71e9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d71e9-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d71e9-123">Element</span></span>|<span data-ttu-id="d71e9-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d71e9-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d71e9-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d71e9-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d71e9-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d71e9-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d71e9-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d71e9-127">Remarks</span></span>  
 <span data-ttu-id="d71e9-128">A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> estructura implementa el <xref:System.IFormattable> interfaz y admite operaciones con cadenas de formato estándar y personalizadas de formato.</span><span class="sxs-lookup"><span data-stu-id="d71e9-128">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="d71e9-129">Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="d71e9-129">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="d71e9-130">En versiones anteriores de .NET Framework, el <xref:System.TimeSpan> estructura no implementó <xref:System.IFormattable> y no eran compatibles con las cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="d71e9-130">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="d71e9-131">Sin embargo, muchos desarrolladores erróneamente supusieron que <xref:System.TimeSpan> eran compatibles con un conjunto de cadenas de formato y se usaron en [las operaciones de formato compuesto](../../../../../docs/standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d71e9-131">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../../docs/standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d71e9-132">Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con un formato no admitido cadenas suele producen un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="d71e9-132">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="d71e9-133">Sin embargo, dado que <xref:System.TimeSpan> no implementó <xref:System.IFormattable>, el tiempo de ejecución omite la cadena de formato y se llama en su lugar el <xref:System.TimeSpan.ToString?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="d71e9-133">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d71e9-134">Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no se ha producido un <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="d71e9-134">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>  
  
 <span data-ttu-id="d71e9-135">Para los casos en que código heredado pasa un método y una cadena de formato no válido de formato compuesto y no se puede volver a compilar ese código, puede usar el `<TimeSpan_LegacyFormatMode>` elemento para restaurar heredado <xref:System.TimeSpan> comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d71e9-135">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="d71e9-136">Al establecer el `enabled` atributo de este elemento para `true`, el método da como resultado una llamada a de formato compuesto <xref:System.TimeSpan.ToString?displayProperty=nameWithType> lugar <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>y un <xref:System.FormatException> no se produce.</span><span class="sxs-lookup"><span data-stu-id="d71e9-136">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d71e9-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d71e9-137">Example</span></span>  
 <span data-ttu-id="d71e9-138">El ejemplo siguiente crea un <xref:System.TimeSpan> objeto e intenta dar formato con el <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> método mediante una cadena de formato estándar no admitido.</span><span class="sxs-lookup"><span data-stu-id="d71e9-138">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 <span data-ttu-id="d71e9-139">Al ejecutar el ejemplo en el [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] o una versión anterior, muestra el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d71e9-139">When you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] or on an earlier version, it displays the following output:</span></span>  
  
```  
12:30:45  
```  
  
 <span data-ttu-id="d71e9-140">Esto difiere notablemente de la salida, si ejecuta el ejemplo en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o una versión posterior:</span><span class="sxs-lookup"><span data-stu-id="d71e9-140">This differs markedly from the output if you run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version:</span></span>  
  
```  
Invalid Format  
```  
  
 <span data-ttu-id="d71e9-141">Sin embargo, si agrega el siguiente archivo de configuración para el ejemplo del directorio y, a continuación, ejecutar el ejemplo en el [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] o una versión posterior, el resultado es idéntico al producido por el ejemplo, cuando se ejecuta [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d71e9-141">However, if you add the following configuration file to the example's directory and then run the example on the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] or later version, the output is identical to that produced by the example when it is run on [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d71e9-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="d71e9-142">See also</span></span>
- [<span data-ttu-id="d71e9-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="d71e9-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d71e9-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d71e9-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
