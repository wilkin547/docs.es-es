---
title: <dateTimeSerialization> (Elemento)
description: En este artículo se describe el elemento <dateTimeSerialization>, que determina el modo de serialización de los objetos DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: a2684ab72c1fb109d711e333e01836d3399caf86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289647"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="a889f-103">\<dateTimeSerialization> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a889f-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="a889f-104">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="a889f-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="a889f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a889f-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a889f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a889f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a889f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a889f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a889f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a889f-108">Attributes</span></span>  
  
|<span data-ttu-id="a889f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a889f-109">Attributes</span></span>|<span data-ttu-id="a889f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a889f-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="a889f-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="a889f-111">Optional.</span></span> <span data-ttu-id="a889f-112">Especifica el modo de serialización.</span><span class="sxs-lookup"><span data-stu-id="a889f-112">Specifies the serialization mode.</span></span> <span data-ttu-id="a889f-113">Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .</span><span class="sxs-lookup"><span data-stu-id="a889f-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="a889f-114">El valor predeterminado es **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="a889f-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a889f-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a889f-115">Child Elements</span></span>  
 <span data-ttu-id="a889f-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a889f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a889f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a889f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a889f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a889f-118">Element</span></span>|<span data-ttu-id="a889f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a889f-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a889f-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="a889f-120">system.xml.serialization</span></span>|<span data-ttu-id="a889f-121">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="a889f-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a889f-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a889f-122">Remarks</span></span>  
 <span data-ttu-id="a889f-123">En las versiones 1.0, 1.1, 2.0 y posteriores de .NET Framework, cuando esta propiedad se establece en **Local**, los objetos <xref:System.DateTime> siempre reciben formato según la hora local.</span><span class="sxs-lookup"><span data-stu-id="a889f-123">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="a889f-124">Es decir, la información de zona horaria local siempre se incluye con los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="a889f-124">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="a889f-125">Establezca esta propiedad en **Local** para garantizar la compatibilidad con las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a889f-125">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a889f-126">En la versión 2.0 y posteriores de .NET Framework que tienen esta propiedad establecida en **Roundtrip**, los objetos <xref:System.DateTime> se examinan para determinar si están en la zona horaria local, UTC o una no especificada.</span><span class="sxs-lookup"><span data-stu-id="a889f-126">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="a889f-127">Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="a889f-127">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="a889f-128">Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="a889f-128">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a889f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a889f-129">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="a889f-130">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a889f-130">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="a889f-131">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="a889f-131">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="a889f-132">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="a889f-132">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="a889f-133">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="a889f-133">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
