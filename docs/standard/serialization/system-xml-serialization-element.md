---
title: Elemento <system.xml.serialization>
description: En este artículo se describe el elemento <system.xml.serialization>, que es el elemento de nivel superior para controlar la serialización XML.
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 6291799aadc429e943996f2256d773ac36dd370f
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282396"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="74f04-103">\<system.xml.serialization> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="74f04-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="74f04-104">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="74f04-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="74f04-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="74f04-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>

\<configuration>\
\<system.xml.serialization>

## <a name="syntax"></a><span data-ttu-id="74f04-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74f04-106">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="74f04-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="74f04-107">Attributes and Elements</span></span>

<span data-ttu-id="74f04-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="74f04-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="74f04-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="74f04-109">Attributes</span></span>

<span data-ttu-id="74f04-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74f04-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="74f04-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="74f04-111">Child Elements</span></span>

|<span data-ttu-id="74f04-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="74f04-112">Element</span></span>|<span data-ttu-id="74f04-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="74f04-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74f04-114">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="74f04-114">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)|<span data-ttu-id="74f04-115">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="74f04-115">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="74f04-116">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="74f04-116">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)|<span data-ttu-id="74f04-117">Contiene tipos que <xref:System.Xml.Serialization.XmlSchemaImporter> usa para asignar de los tipos XSD a los tipos de .NET.</span><span class="sxs-lookup"><span data-stu-id="74f04-117">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="74f04-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="74f04-118">Parent Elements</span></span>

|<span data-ttu-id="74f04-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="74f04-119">Element</span></span>|<span data-ttu-id="74f04-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="74f04-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="74f04-121">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="74f04-121">\<configuration> Element</span></span>](../../framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="74f04-122">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74f04-122">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="74f04-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74f04-123">Example</span></span>

<span data-ttu-id="74f04-124">El ejemplo de código siguiente muestra cómo especificar el modo de la serialización de un objeto <xref:System.DateTime> y la suma de tipos utilizada por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET.</span><span class="sxs-lookup"><span data-stu-id="74f04-124">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="74f04-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="74f04-125">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="74f04-126">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="74f04-126">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="74f04-127">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="74f04-127">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="74f04-128">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="74f04-128">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="74f04-129">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="74f04-129">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
