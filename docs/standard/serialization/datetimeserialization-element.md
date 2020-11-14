---
title: <dateTimeSerialization> (Elemento)
description: En este artículo se describe el elemento <dateTimeSerialization>, que determina el modo de serialización de los objetos DateTime.
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 90ae911c8942fef7a9e8238921990b0a52a47ca0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281764"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="0eb3d-103">\<dateTimeSerialization> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="0eb3d-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="0eb3d-104">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="0eb3d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eb3d-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0eb3d-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0eb3d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0eb3d-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0eb3d-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="0eb3d-108">Attributes</span></span>  
  
|<span data-ttu-id="0eb3d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0eb3d-109">Attributes</span></span>|<span data-ttu-id="0eb3d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eb3d-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="0eb3d-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-111">Optional.</span></span> <span data-ttu-id="0eb3d-112">Especifica el modo de serialización.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-112">Specifies the serialization mode.</span></span> <span data-ttu-id="0eb3d-113">Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .</span><span class="sxs-lookup"><span data-stu-id="0eb3d-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="0eb3d-114">El valor predeterminado es **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0eb3d-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0eb3d-115">Child Elements</span></span>  
 <span data-ttu-id="0eb3d-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0eb3d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0eb3d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0eb3d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0eb3d-118">Element</span></span>|<span data-ttu-id="0eb3d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eb3d-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0eb3d-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="0eb3d-120">system.xml.serialization</span></span>|<span data-ttu-id="0eb3d-121">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eb3d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0eb3d-122">Remarks</span></span>  

<span data-ttu-id="0eb3d-123">Cuando esta propiedad se establece en **Local** , los objetos <xref:System.DateTime> siempre tienen el formato de hora local.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-123">When this property is set to **Local** , <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="0eb3d-124">Es decir, la información de zona horaria local siempre se incluye con los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-124">That is, local time zone information is always included with the serialized data.</span></span>
  
<span data-ttu-id="0eb3d-125">Cuando esta propiedad se establece en **Roundtrip** , los objetos <xref:System.DateTime> se examinan para determinar si se encuentran en la zona horaria local, UTC o una zona horaria no especificada.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-125">When this property is set to **Roundtrip** , <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="0eb3d-126">Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-126">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="0eb3d-127">Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="0eb3d-127">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb3d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eb3d-128">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="0eb3d-129">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0eb3d-129">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="0eb3d-130">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="0eb3d-130">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="0eb3d-131">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="0eb3d-131">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="0eb3d-132">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="0eb3d-132">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
