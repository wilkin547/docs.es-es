---
title: <schemaImporterExtensions> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: 5ed80ac370e34d6b62bb2b601cb7bd978228a302
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159824"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="c1496-102">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c1496-102">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="c1496-103">Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1496-103">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="c1496-104">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="c1496-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1496-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1496-105">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="c1496-106">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1496-106">Child Elements</span></span>  
  
|<span data-ttu-id="c1496-107">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1496-107">Element</span></span>|<span data-ttu-id="c1496-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1496-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1496-109">Elemento [\<add> de \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span><span class="sxs-lookup"><span data-stu-id="c1496-109">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>|<span data-ttu-id="c1496-110">Agrega tipos que son usados por <xref:System.Xml.Serialization.XmlSchemaImporter> para crear las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="c1496-110">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="c1496-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1496-111">Parent Elements</span></span>  
  
|<span data-ttu-id="c1496-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1496-112">Element</span></span>|<span data-ttu-id="c1496-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1496-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1496-114">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c1496-114">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="c1496-115">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="c1496-115">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c1496-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1496-116">Example</span></span>  
 <span data-ttu-id="c1496-117">El ejemplo de código siguiente muestra cómo agregar tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1496-117">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1496-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1496-118">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="c1496-119">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c1496-119">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c1496-120">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="c1496-120">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- <span data-ttu-id="c1496-121">Elemento [\<add> de \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span><span class="sxs-lookup"><span data-stu-id="c1496-121">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>
- [<span data-ttu-id="c1496-122">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c1496-122">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
