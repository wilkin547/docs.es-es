---
title: Elemento <add> para <schemaImporterExtensions>
description: El elemento <add> agrega los tipos que usa la clase XmlSchemaImporter para asignar tipos XSD a tipos de .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 401d1ba9cc2f97e93d7851f96f73b552e6ed6356
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378481"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="dca8a-103">Elemento \<add> para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="dca8a-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="dca8a-104">Agrega tipos utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dca8a-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="dca8a-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="dca8a-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="dca8a-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dca8a-106">\<configuration></span></span>  
<span data-ttu-id="dca8a-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="dca8a-107">\<system.xml.serialization></span></span>  
<span data-ttu-id="dca8a-108">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="dca8a-108">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="dca8a-109">\<add></span><span class="sxs-lookup"><span data-stu-id="dca8a-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca8a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dca8a-110">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dca8a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dca8a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dca8a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dca8a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dca8a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="dca8a-113">Attributes</span></span>  
  
|<span data-ttu-id="dca8a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="dca8a-114">Attribute</span></span>|<span data-ttu-id="dca8a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="dca8a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dca8a-116">**name**</span><span class="sxs-lookup"><span data-stu-id="dca8a-116">**name**</span></span>|<span data-ttu-id="dca8a-117">Un nombre sencillo que se utiliza para buscar la instancia.</span><span class="sxs-lookup"><span data-stu-id="dca8a-117">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="dca8a-118">**type**</span><span class="sxs-lookup"><span data-stu-id="dca8a-118">**type**</span></span>|<span data-ttu-id="dca8a-119">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dca8a-119">Required.</span></span> <span data-ttu-id="dca8a-120">Especifica la clase de extensión de esquema que se agrega.</span><span class="sxs-lookup"><span data-stu-id="dca8a-120">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="dca8a-121">El valor del atributo **type** debe estar en una línea e incluye el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="dca8a-121">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="dca8a-122">Cuando el ensamblado se encuentra en la caché global de ensamblados (GAC), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.</span><span class="sxs-lookup"><span data-stu-id="dca8a-122">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dca8a-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dca8a-123">Child Elements</span></span>  
 <span data-ttu-id="dca8a-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dca8a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dca8a-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dca8a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="dca8a-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="dca8a-126">Element</span></span>|<span data-ttu-id="dca8a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="dca8a-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dca8a-128">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="dca8a-128">\<schemaImporterExtensions></span></span>|<span data-ttu-id="dca8a-129">Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .</span><span class="sxs-lookup"><span data-stu-id="dca8a-129">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dca8a-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dca8a-130">Example</span></span>  
 <span data-ttu-id="dca8a-131">El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.</span><span class="sxs-lookup"><span data-stu-id="dca8a-131">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
       PublicKeyToken=b03f5f7f11d50a3a" />
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dca8a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="dca8a-132">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="dca8a-133">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="dca8a-133">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="dca8a-134">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="dca8a-134">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
