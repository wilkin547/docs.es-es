---
title: <schemaImporterExtensions> (Elemento)
description: El elemento <schemaImporterExtensions> contiene tipos que se usan en XmlSchemaImporter para asignar tipos XSD a tipos de .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5b9820ccdf2c75bed9beda72358c4c4d82ff9ff7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379787"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="e041a-103">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="e041a-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="e041a-104">Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e041a-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="e041a-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="e041a-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e041a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e041a-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="e041a-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e041a-107">Child Elements</span></span>  
  
|<span data-ttu-id="e041a-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="e041a-108">Element</span></span>|<span data-ttu-id="e041a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="e041a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e041a-110">Elemento [\<add> de \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span><span class="sxs-lookup"><span data-stu-id="e041a-110">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>|<span data-ttu-id="e041a-111">Agrega tipos que son usados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="e041a-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="e041a-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e041a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="e041a-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e041a-113">Element</span></span>|<span data-ttu-id="e041a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e041a-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e041a-115">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e041a-115">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="e041a-116">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="e041a-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e041a-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e041a-117">Example</span></span>  
 <span data-ttu-id="e041a-118">El ejemplo de código siguiente muestra cómo agregar tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e041a-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e041a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e041a-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="e041a-120">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="e041a-120">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e041a-121">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="e041a-121">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- <span data-ttu-id="e041a-122">Elemento [\<add> de \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span><span class="sxs-lookup"><span data-stu-id="e041a-122">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>
- [<span data-ttu-id="e041a-123">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="e041a-123">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
