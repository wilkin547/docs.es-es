---
title: <dateTimeSerialization> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 180a4942dd4b701b56fe4788d5f8cd8607faaedd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459263"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="e4362-102">\<elemento > dateTimeSerialization</span><span class="sxs-lookup"><span data-stu-id="e4362-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="e4362-103">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="e4362-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="e4362-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e4362-104">\<configuration></span></span>  
<span data-ttu-id="e4362-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="e4362-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4362-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4362-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4362-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e4362-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e4362-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e4362-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4362-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4362-109">Attributes</span></span>  
  
|<span data-ttu-id="e4362-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e4362-110">Attributes</span></span>|<span data-ttu-id="e4362-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4362-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="e4362-112">Opcional.</span><span class="sxs-lookup"><span data-stu-id="e4362-112">Optional.</span></span> <span data-ttu-id="e4362-113">Especifica el modo de serialización.</span><span class="sxs-lookup"><span data-stu-id="e4362-113">Specifies the serialization mode.</span></span> <span data-ttu-id="e4362-114">Establece uno de los valores de <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> .</span><span class="sxs-lookup"><span data-stu-id="e4362-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="e4362-115">El valor predeterminado es **RoundTrip**.</span><span class="sxs-lookup"><span data-stu-id="e4362-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4362-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e4362-116">Child Elements</span></span>  
 <span data-ttu-id="e4362-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e4362-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4362-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e4362-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e4362-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e4362-119">Element</span></span>|<span data-ttu-id="e4362-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4362-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e4362-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="e4362-121">system.xml.serialization</span></span>|<span data-ttu-id="e4362-122">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="e4362-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4362-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4362-123">Remarks</span></span>  
 <span data-ttu-id="e4362-124">En las versiones 1.0, 1.1, 2.0 y posteriores de .NET Framework, cuando esta propiedad se establece en **Local**, los objetos <xref:System.DateTime> siempre reciben formato según la hora local.</span><span class="sxs-lookup"><span data-stu-id="e4362-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="e4362-125">Es decir, la información de zona horaria local siempre se incluye con los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="e4362-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="e4362-126">Establezca esta propiedad en **Local** para garantizar la compatibilidad con las versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4362-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e4362-127">En la versión 2.0 y posteriores de .NET Framework que tienen esta propiedad establecida en **Roundtrip**, los objetos <xref:System.DateTime> se examinan para determinar si están en la zona horaria local, UTC o una no especificada.</span><span class="sxs-lookup"><span data-stu-id="e4362-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="e4362-128">Los objetos <xref:System.DateTime> se serializan a continuación de este tipo de manera que esta información se conserva.</span><span class="sxs-lookup"><span data-stu-id="e4362-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="e4362-129">Éste es el comportamiento predeterminado y el que se recomienda para todas las aplicaciones nuevas que no funcionan con versiones anteriores de .Net Framework.</span><span class="sxs-lookup"><span data-stu-id="e4362-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4362-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4362-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="e4362-131">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e4362-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e4362-132">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="e4362-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="e4362-133">\<agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="e4362-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="e4362-134">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e4362-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
