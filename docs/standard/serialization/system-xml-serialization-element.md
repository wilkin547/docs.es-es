---
title: '&lt;system.xml.serialization&gt; (Elemento)'
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: b67c1ec1ec737976e4e50b80b42f34e508dc0224
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836224"
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="41e69-102">&lt;system.xml.serialization&gt; (Elemento)</span><span class="sxs-lookup"><span data-stu-id="41e69-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="41e69-103">El elemento de nivel superior para controlar la serialización XML.</span><span class="sxs-lookup"><span data-stu-id="41e69-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="41e69-104">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="41e69-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="41e69-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="41e69-105">\<configuration></span></span>  
<span data-ttu-id="41e69-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="41e69-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e69-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41e69-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41e69-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="41e69-108">Attributes and Elements</span></span>  
 <span data-ttu-id="41e69-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="41e69-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41e69-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="41e69-110">Attributes</span></span>  
 <span data-ttu-id="41e69-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="41e69-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="41e69-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="41e69-112">Child Elements</span></span>  
  
|<span data-ttu-id="41e69-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="41e69-113">Element</span></span>|<span data-ttu-id="41e69-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="41e69-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41e69-115">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="41e69-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="41e69-116">Determina el modo de serialización XML de los objetos <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="41e69-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="41e69-117">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="41e69-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="41e69-118">Contiene tipos que son utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar de los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41e69-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41e69-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="41e69-119">Parent Elements</span></span>  
  
|<span data-ttu-id="41e69-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="41e69-120">Element</span></span>|<span data-ttu-id="41e69-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="41e69-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41e69-122">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="41e69-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="41e69-123">Elemento raíz necesario en cada archivo de configuración utilizado por Common Language Runtime y las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41e69-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="41e69-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41e69-124">Example</span></span>  
 <span data-ttu-id="41e69-125">El ejemplo de código siguiente muestra cómo especificar el modo de la serialización de un objeto <xref:System.DateTime> y la suma de tipos utilizada por <xref:System.Xml.Serialization.XmlSchemaImporter> al asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="41e69-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41e69-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="41e69-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>  
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
- [<span data-ttu-id="41e69-127">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="41e69-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="41e69-128">Elemento \<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="41e69-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
- [<span data-ttu-id="41e69-129">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="41e69-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
- [<span data-ttu-id="41e69-130">\<Agregar > elemento para \<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="41e69-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
