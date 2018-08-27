---
title: '&lt;dateTimeSerialization&gt; (Elemento)'
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 15fad472288a72a079991f41e6c2859776d78cca
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930092"
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="26e6a-102">&lt;dateTimeSerialization&gt; (Elemento)</span><span class="sxs-lookup"><span data-stu-id="26e6a-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="26e6a-103">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="26e6a-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="26e6a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="26e6a-104">\<configuration></span></span>  
<span data-ttu-id="26e6a-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="26e6a-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26e6a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26e6a-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26e6a-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26e6a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="26e6a-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="26e6a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26e6a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="26e6a-109">Attributes</span></span>  
  
|<span data-ttu-id="26e6a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="26e6a-110">Attributes</span></span>|<span data-ttu-id="26e6a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e6a-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="26e6a-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="26e6a-112">Optional.</span></span> <span data-ttu-id="26e6a-113">Especifica el modo de serialización.</span><span class="sxs-lookup"><span data-stu-id="26e6a-113">Specifies the serialization mode.</span></span> <span data-ttu-id="26e6a-114">Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .</span><span class="sxs-lookup"><span data-stu-id="26e6a-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="26e6a-115">El valor predeterminado es **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="26e6a-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26e6a-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26e6a-116">Child Elements</span></span>  
 <span data-ttu-id="26e6a-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="26e6a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26e6a-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26e6a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="26e6a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="26e6a-119">Element</span></span>|<span data-ttu-id="26e6a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="26e6a-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="26e6a-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="26e6a-121">system.xml.serialization</span></span>|<span data-ttu-id="26e6a-122">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="26e6a-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26e6a-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26e6a-123">Remarks</span></span>  
 <span data-ttu-id="26e6a-124">En las versiones 1.0, 1.1, 2.0 y posteriores de .NET Framework, cuando esta propiedad se establece en **Local**, los objetos <xref:System.DateTime> siempre reciben formato según la hora local.</span><span class="sxs-lookup"><span data-stu-id="26e6a-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="26e6a-125">Es decir, la información de zona horaria local siempre se incluye con los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="26e6a-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="26e6a-126">Establezca esta propiedad en **Local** para garantizar la compatibilidad con las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="26e6a-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="26e6a-127">En la versión 2.0 y posteriores de .NET Framework que tienen esta propiedad establecida en **Roundtrip**, los objetos <xref:System.DateTime> se examinan para determinar si están en la zona horaria local, UTC o una no especificada.</span><span class="sxs-lookup"><span data-stu-id="26e6a-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="26e6a-128">Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="26e6a-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="26e6a-129">Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="26e6a-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e6a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="26e6a-130">See Also</span></span>  
 <xref:System.DateTime>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="26e6a-131">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="26e6a-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="26e6a-132">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="26e6a-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [<span data-ttu-id="26e6a-133">\<Agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="26e6a-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)  
 [<span data-ttu-id="26e6a-134">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="26e6a-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
