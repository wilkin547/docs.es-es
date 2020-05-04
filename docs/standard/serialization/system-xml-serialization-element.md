---
title: Elemento <system.xml.serialization>
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 02027a238bc9a2f82963ea841584d2bb3c6446c6
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410548"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="4109c-102">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="4109c-102">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="4109c-103">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="4109c-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="4109c-104">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="4109c-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="4109c-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4109c-105">\<configuration></span></span>\
<span data-ttu-id="4109c-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="4109c-106">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="4109c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4109c-107">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4109c-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4109c-108">Attributes and Elements</span></span>

<span data-ttu-id="4109c-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4109c-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4109c-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="4109c-110">Attributes</span></span>

<span data-ttu-id="4109c-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4109c-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="4109c-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4109c-112">Child Elements</span></span>

|<span data-ttu-id="4109c-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="4109c-113">Element</span></span>|<span data-ttu-id="4109c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4109c-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4109c-115">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="4109c-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="4109c-116">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="4109c-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="4109c-117">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="4109c-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="4109c-118">Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4109c-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="4109c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4109c-119">Parent Elements</span></span>

|<span data-ttu-id="4109c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4109c-120">Element</span></span>|<span data-ttu-id="4109c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4109c-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="4109c-122">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="4109c-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="4109c-123">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4109c-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="4109c-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4109c-124">Example</span></span>

<span data-ttu-id="4109c-125">El ejemplo de código siguiente muestra cómo especificar el modo de la serialización de un objeto <xref:System.DateTime> y la suma de tipos utilizada por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4109c-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4109c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4109c-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="4109c-127">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4109c-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="4109c-128">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="4109c-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="4109c-129">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="4109c-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- <span data-ttu-id="4109c-130">Elemento [\<add> de \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span><span class="sxs-lookup"><span data-stu-id="4109c-130">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>
