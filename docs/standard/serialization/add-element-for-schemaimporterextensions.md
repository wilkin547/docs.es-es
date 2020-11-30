---
title: Elemento <add> para <schemaImporterExtensions>
description: El elemento <add> agrega los tipos que usa la clase XmlSchemaImporter para asignar tipos XSD a tipos de .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: b8a0775e9d33d59606b1150aa9a1b3b1026d4b0b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726449"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="80e6a-103">Elemento \<add> para \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="80e6a-103">\<add> Element for \<schemaImporterExtensions></span></span>

<span data-ttu-id="80e6a-104">Agrega tipos que <xref:System.Xml.Serialization.XmlSchemaImporter> utiliza para asignar los tipos XSD a los tipos de .NET.</span><span class="sxs-lookup"><span data-stu-id="80e6a-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET types.</span></span> <span data-ttu-id="80e6a-105">Para más información sobre los archivos de configuración, vea [Configuration File Schema](../../framework/configure-apps/file-schema/index.md) (Esquema de archivos de configuración).</span><span class="sxs-lookup"><span data-stu-id="80e6a-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
\<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="80e6a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80e6a-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80e6a-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80e6a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="80e6a-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80e6a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80e6a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="80e6a-109">Attributes</span></span>  
  
|<span data-ttu-id="80e6a-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="80e6a-110">Attribute</span></span>|<span data-ttu-id="80e6a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="80e6a-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80e6a-112">**name**</span><span class="sxs-lookup"><span data-stu-id="80e6a-112">**name**</span></span>|<span data-ttu-id="80e6a-113">Un nombre sencillo que se utiliza para buscar la instancia.</span><span class="sxs-lookup"><span data-stu-id="80e6a-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="80e6a-114">**type**</span><span class="sxs-lookup"><span data-stu-id="80e6a-114">**type**</span></span>|<span data-ttu-id="80e6a-115">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="80e6a-115">Required.</span></span> <span data-ttu-id="80e6a-116">Especifica la clase de extensión de esquema que se agrega.</span><span class="sxs-lookup"><span data-stu-id="80e6a-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="80e6a-117">El valor del atributo **type** debe estar en una línea e incluye el nombre de tipo completo.</span><span class="sxs-lookup"><span data-stu-id="80e6a-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="80e6a-118">Cuando el ensamblado se encuentra en la caché global de ensamblados (GAC), también debe incluir la versión, la referencia cultural y el token de clave pública del ensamblado firmado.</span><span class="sxs-lookup"><span data-stu-id="80e6a-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80e6a-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80e6a-119">Child Elements</span></span>  

 <span data-ttu-id="80e6a-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80e6a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80e6a-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80e6a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="80e6a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="80e6a-122">Element</span></span>|<span data-ttu-id="80e6a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="80e6a-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="80e6a-124">Contiene los tipos que utiliza <xref:System.Xml.Serialization.XmlSchemaImporter> .</span><span class="sxs-lookup"><span data-stu-id="80e6a-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80e6a-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80e6a-125">Example</span></span>  

 <span data-ttu-id="80e6a-126">El ejemplo de código siguiente agrega un tipo de extensión que XmlSchemaImporter puede utilizar al asignar los tipos.</span><span class="sxs-lookup"><span data-stu-id="80e6a-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80e6a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="80e6a-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="80e6a-128">Elemento \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="80e6a-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="80e6a-129">Elemento \<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="80e6a-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
