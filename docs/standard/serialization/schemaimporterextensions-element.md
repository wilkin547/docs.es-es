---
title: <schemaImporterExtensions> (Elemento)
description: El elemento <schemaImporterExtensions> contiene tipos que se usan en XmlSchemaImporter para asignar tipos XSD a tipos de .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 35626618a8dd7c63a7008d10bc3568484836a488
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282267"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="05c5f-103">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="05c5f-103">\<schemaImporterExtensions> element</span></span>

<span data-ttu-id="05c5f-104">Contiene tipos que <xref:System.Xml.Serialization.XmlSchemaImporter> usa para asignar de los tipos XSD a los tipos de .NET.</span><span class="sxs-lookup"><span data-stu-id="05c5f-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET types.</span></span> <span data-ttu-id="05c5f-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="05c5f-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c5f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05c5f-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="05c5f-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="05c5f-107">Child Elements</span></span>  
  
|<span data-ttu-id="05c5f-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="05c5f-108">Element</span></span>|<span data-ttu-id="05c5f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="05c5f-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c5f-110">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="05c5f-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="05c5f-111">Agrega tipos que son usados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="05c5f-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="05c5f-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="05c5f-112">Parent Elements</span></span>  
  
|<span data-ttu-id="05c5f-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="05c5f-113">Element</span></span>|<span data-ttu-id="05c5f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="05c5f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05c5f-115">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="05c5f-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="05c5f-116">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="05c5f-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="05c5f-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05c5f-117">Example</span></span>  
 <span data-ttu-id="05c5f-118">El ejemplo de código siguiente muestra cómo agregar tipos que <xref:System.Xml.Serialization.XmlSchemaImporter> usa al asignar los tipos XSD a los tipos de .NET.</span><span class="sxs-lookup"><span data-stu-id="05c5f-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05c5f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="05c5f-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="05c5f-120">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="05c5f-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="05c5f-121">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="05c5f-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="05c5f-122">\<add> Elemento para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="05c5f-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="05c5f-123">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="05c5f-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
