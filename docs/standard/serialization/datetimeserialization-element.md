---
title: '&lt;dateTimeSerialization&gt; (Elemento)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 492a3652ca7cd304b953006bb1b18a1edb3dcf51
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="6a5a2-102">&lt;dateTimeSerialization&gt; (Elemento)</span><span class="sxs-lookup"><span data-stu-id="6a5a2-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="6a5a2-103">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="6a5a2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6a5a2-104">\<configuration></span></span>  
<span data-ttu-id="6a5a2-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="6a5a2-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5a2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a5a2-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a5a2-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6a5a2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6a5a2-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a5a2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6a5a2-109">Attributes</span></span>  
  
|<span data-ttu-id="6a5a2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6a5a2-110">Attributes</span></span>|<span data-ttu-id="6a5a2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a5a2-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="6a5a2-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-112">Optional.</span></span> <span data-ttu-id="6a5a2-113">Especifica el modo de serialización.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-113">Specifies the serialization mode.</span></span> <span data-ttu-id="6a5a2-114">Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .</span><span class="sxs-lookup"><span data-stu-id="6a5a2-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="6a5a2-115">El valor predeterminado es **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a5a2-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6a5a2-116">Child Elements</span></span>  
 <span data-ttu-id="6a5a2-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a5a2-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6a5a2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6a5a2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a5a2-119">Element</span></span>|<span data-ttu-id="6a5a2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a5a2-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a5a2-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="6a5a2-121">system.xml.serialization</span></span>|<span data-ttu-id="6a5a2-122">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a5a2-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6a5a2-123">Remarks</span></span>  
 <span data-ttu-id="6a5a2-124">En las versiones 1.0, 1.1, 2.0 y posteriores de .NET Framework, cuando esta propiedad se establece en **Local**, los objetos <xref:System.DateTime> siempre reciben formato según la hora local.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="6a5a2-125">Es decir, la información de zona horaria local siempre se incluye con los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="6a5a2-126">Establezca esta propiedad en **Local** para garantizar la compatibilidad con las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6a5a2-127">En la versión 2.0 y posteriores de .NET Framework que tienen esta propiedad establecida en **Roundtrip**, los objetos <xref:System.DateTime> se examinan para determinar si están en la zona horaria local, UTC o una no especificada.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="6a5a2-128">Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="6a5a2-129">Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="6a5a2-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5a2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a5a2-130">See Also</span></span>  
 <xref:System.DateTime>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="6a5a2-131">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="6a5a2-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="6a5a2-132">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6a5a2-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [<span data-ttu-id="6a5a2-133">Elemento \<add> de \<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="6a5a2-133">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 [<span data-ttu-id="6a5a2-134">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="6a5a2-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
