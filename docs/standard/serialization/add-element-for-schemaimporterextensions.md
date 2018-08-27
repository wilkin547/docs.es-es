---
title: '&lt;agregar&gt; (elemento) para &lt;schemaImporterExtensions&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 3d3c72fd64042032d44c49ebde867d111ce03b94
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42936589"
---
# <a name="ltaddgt-element-for-ltschemaimporterextensionsgt"></a><span data-ttu-id="7f3a8-102">&lt;agregar&gt; (elemento) para &lt;schemaImporterExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="7f3a8-102">&lt;add&gt; Element for &lt;schemaImporterExtensions&gt;</span></span>
<span data-ttu-id="7f3a8-103">Agrega tipos utilizados por <xref:System.Xml.Serialization.XmlSchemaImporter> para asignar los tipos XSD a los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="7f3a8-104">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="7f3a8-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="7f3a8-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7f3a8-105">\<configuration></span></span>  
<span data-ttu-id="7f3a8-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7f3a8-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="7f3a8-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7f3a8-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="7f3a8-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7f3a8-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f3a8-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f3a8-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f3a8-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7f3a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7f3a8-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f3a8-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7f3a8-112">Attributes</span></span>  
  
|<span data-ttu-id="7f3a8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="7f3a8-113">Attribute</span></span>|<span data-ttu-id="7f3a8-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f3a8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f3a8-115">**name**</span><span class="sxs-lookup"><span data-stu-id="7f3a8-115">**name**</span></span>|<span data-ttu-id="7f3a8-116">Un nombre sencillo que se utiliza para buscar la instancia.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="7f3a8-117">**type**</span><span class="sxs-lookup"><span data-stu-id="7f3a8-117">**type**</span></span>|<span data-ttu-id="7f3a8-118">Requerido.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-118">Required.</span></span> <span data-ttu-id="7f3a8-119">Especifica la clase de extensión de esquema que se agrega.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="7f3a8-120">El valor del atributo **type** debe estar en una línea e incluye el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="7f3a8-121">Cuando el ensamblado se encuentra en la caché global de ensamblados (GAC), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f3a8-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7f3a8-122">Child Elements</span></span>  
 <span data-ttu-id="7f3a8-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f3a8-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7f3a8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7f3a8-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="7f3a8-125">Element</span></span>|<span data-ttu-id="7f3a8-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f3a8-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f3a8-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7f3a8-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="7f3a8-128">Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .</span><span class="sxs-lookup"><span data-stu-id="7f3a8-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f3a8-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f3a8-129">Example</span></span>  
 <span data-ttu-id="7f3a8-130">El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.</span><span class="sxs-lookup"><span data-stu-id="7f3a8-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f3a8-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f3a8-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="7f3a8-132">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7f3a8-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="7f3a8-133">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7f3a8-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
