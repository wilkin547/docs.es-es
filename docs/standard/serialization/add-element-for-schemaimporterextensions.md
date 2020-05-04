---
title: Elemento <add> para <schemaImporterExtensions>
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 4f47623aa305ae6e98625acc3d199a76e27d2ea5
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159941"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="64975-102">Elemento \<add> para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="64975-102">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="64975-103">Agrega tipos utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64975-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="64975-104">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="64975-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="64975-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="64975-105">\<configuration></span></span>  
<span data-ttu-id="64975-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="64975-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="64975-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="64975-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="64975-108">\<add></span><span class="sxs-lookup"><span data-stu-id="64975-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64975-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64975-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64975-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64975-110">Attributes and Elements</span></span>  
 <span data-ttu-id="64975-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="64975-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64975-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="64975-112">Attributes</span></span>  
  
|<span data-ttu-id="64975-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="64975-113">Attribute</span></span>|<span data-ttu-id="64975-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="64975-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64975-115">**name**</span><span class="sxs-lookup"><span data-stu-id="64975-115">**name**</span></span>|<span data-ttu-id="64975-116">Un nombre sencillo que se utiliza para buscar la instancia.</span><span class="sxs-lookup"><span data-stu-id="64975-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="64975-117">**type**</span><span class="sxs-lookup"><span data-stu-id="64975-117">**type**</span></span>|<span data-ttu-id="64975-118">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="64975-118">Required.</span></span> <span data-ttu-id="64975-119">Especifica la clase de extensión de esquema que se agrega.</span><span class="sxs-lookup"><span data-stu-id="64975-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="64975-120">El valor del atributo **type** debe estar en una línea e incluye el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="64975-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="64975-121">Cuando el ensamblado se encuentra en la caché global de ensamblados (GAC), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.</span><span class="sxs-lookup"><span data-stu-id="64975-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64975-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64975-122">Child Elements</span></span>  
 <span data-ttu-id="64975-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="64975-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64975-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64975-124">Parent Elements</span></span>  
  
|<span data-ttu-id="64975-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="64975-125">Element</span></span>|<span data-ttu-id="64975-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="64975-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64975-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="64975-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="64975-128">Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .</span><span class="sxs-lookup"><span data-stu-id="64975-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="64975-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64975-129">Example</span></span>  
 <span data-ttu-id="64975-130">El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.</span><span class="sxs-lookup"><span data-stu-id="64975-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64975-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="64975-131">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="64975-132">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="64975-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="64975-133">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="64975-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
