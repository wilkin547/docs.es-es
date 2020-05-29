---
title: <dateTimeSerialization> (Elemento)
description: En este artículo se describe el elemento <dateTimeSerialization>, que determina el modo de serialización de los objetos DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375825"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="c745a-103">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="c745a-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="c745a-104">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="c745a-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="c745a-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c745a-105">\<configuration></span></span>  
<span data-ttu-id="c745a-106">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="c745a-106">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c745a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c745a-107">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c745a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c745a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c745a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c745a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c745a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c745a-110">Attributes</span></span>  
  
|<span data-ttu-id="c745a-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="c745a-111">Attributes</span></span>|<span data-ttu-id="c745a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c745a-112">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="c745a-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c745a-113">Optional.</span></span> <span data-ttu-id="c745a-114">Especifica el modo de serialización.</span><span class="sxs-lookup"><span data-stu-id="c745a-114">Specifies the serialization mode.</span></span> <span data-ttu-id="c745a-115">Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .</span><span class="sxs-lookup"><span data-stu-id="c745a-115">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="c745a-116">El valor predeterminado es **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="c745a-116">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c745a-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c745a-117">Child Elements</span></span>  
 <span data-ttu-id="c745a-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c745a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c745a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c745a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c745a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="c745a-120">Element</span></span>|<span data-ttu-id="c745a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c745a-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c745a-122">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="c745a-122">system.xml.serialization</span></span>|<span data-ttu-id="c745a-123">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="c745a-123">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c745a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c745a-124">Remarks</span></span>  
 <span data-ttu-id="c745a-125">En las versiones 1.0, 1.1, 2.0 y posteriores de .NET Framework, cuando esta propiedad se establece en **Local**, los objetos <xref:System.DateTime> siempre reciben formato según la hora local.</span><span class="sxs-lookup"><span data-stu-id="c745a-125">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="c745a-126">Es decir, la información de zona horaria local siempre se incluye con los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="c745a-126">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="c745a-127">Establezca esta propiedad en **Local** para garantizar la compatibilidad con las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c745a-127">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c745a-128">En la versión 2.0 y posteriores de .NET Framework que tienen esta propiedad establecida en **Roundtrip**, los objetos <xref:System.DateTime> se examinan para determinar si están en la zona horaria local, UTC o una no especificada.</span><span class="sxs-lookup"><span data-stu-id="c745a-128">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="c745a-129">Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="c745a-129">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="c745a-130">Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="c745a-130">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c745a-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c745a-131">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="c745a-132">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c745a-132">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c745a-133">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c745a-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="c745a-134">Elemento \<add> para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c745a-134">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="c745a-135">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c745a-135">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
