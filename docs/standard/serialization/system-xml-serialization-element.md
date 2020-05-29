---
title: Elemento <system.xml.serialization>
description: En este artículo se describe el elemento <system.xml.serialization>, que es el elemento de nivel superior para controlar la serialización XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 1e66220004d561f937d03c506e6f30db4ccc635b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380117"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="ea5fb-103">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="ea5fb-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="ea5fb-104">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="ea5fb-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="ea5fb-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="ea5fb-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ea5fb-106">\<configuration></span></span>\
<span data-ttu-id="ea5fb-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="ea5fb-107">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="ea5fb-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea5fb-108">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ea5fb-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ea5fb-109">Attributes and Elements</span></span>

<span data-ttu-id="ea5fb-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ea5fb-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ea5fb-111">Attributes</span></span>

<span data-ttu-id="ea5fb-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ea5fb-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ea5fb-113">Child Elements</span></span>

|<span data-ttu-id="ea5fb-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea5fb-114">Element</span></span>|<span data-ttu-id="ea5fb-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea5fb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea5fb-116">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ea5fb-116">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="ea5fb-117">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-117">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="ea5fb-118">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ea5fb-118">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="ea5fb-119">Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-119">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ea5fb-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ea5fb-120">Parent Elements</span></span>

|<span data-ttu-id="ea5fb-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea5fb-121">Element</span></span>|<span data-ttu-id="ea5fb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea5fb-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ea5fb-123">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="ea5fb-123">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="ea5fb-124">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-124">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="ea5fb-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea5fb-125">Example</span></span>

<span data-ttu-id="ea5fb-126">El ejemplo de código siguiente muestra cómo especificar el modo de la serialización de un objeto <xref:System.DateTime> y la suma de tipos utilizada por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ea5fb-126">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a><span data-ttu-id="ea5fb-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea5fb-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="ea5fb-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="ea5fb-128">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ea5fb-129">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ea5fb-129">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="ea5fb-130">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="ea5fb-130">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- <span data-ttu-id="ea5fb-131">Elemento [\<add> de \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span><span class="sxs-lookup"><span data-stu-id="ea5fb-131">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>
