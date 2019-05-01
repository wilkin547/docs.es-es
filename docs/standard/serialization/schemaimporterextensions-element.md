---
title: <schemaImporterExtensions> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 43f8439708c73e8e5241a923360caf549bf09d8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017974"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="fadb2-102">\<schemaImporterExtensions > elemento</span><span class="sxs-lookup"><span data-stu-id="fadb2-102">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="fadb2-103">Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fadb2-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="fadb2-104">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="fadb2-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fadb2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fadb2-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="fadb2-106">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fadb2-106">Child Elements</span></span>  
  
|<span data-ttu-id="fadb2-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="fadb2-107">Element</span></span>|<span data-ttu-id="fadb2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="fadb2-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fadb2-109">\<Agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="fadb2-109">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)|<span data-ttu-id="fadb2-110">Agrega tipos que son usados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="fadb2-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="fadb2-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fadb2-111">Parent Elements</span></span>  
  
|<span data-ttu-id="fadb2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="fadb2-112">Element</span></span>|<span data-ttu-id="fadb2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fadb2-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fadb2-114">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fadb2-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="fadb2-115">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="fadb2-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fadb2-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fadb2-116">Example</span></span>  
 <span data-ttu-id="fadb2-117">El ejemplo de código siguiente muestra cómo agregar tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fadb2-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fadb2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fadb2-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="fadb2-119">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="fadb2-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="fadb2-120">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="fadb2-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="fadb2-121">\<Agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="fadb2-121">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="fadb2-122">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fadb2-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
