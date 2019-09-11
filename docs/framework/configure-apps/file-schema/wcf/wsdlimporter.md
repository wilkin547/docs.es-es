---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 317921a66fa3b8d1f0026d676ea674b67732b3df
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854761"
---
# <a name="wsdlimporter"></a><span data-ttu-id="447d9-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="447d9-101">\<wsdlImporter></span></span>
<span data-ttu-id="447d9-102">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="447d9-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="447d9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="447d9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="447d9-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="447d9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="447d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="447d9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="447d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<metadatos >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="447d9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="447d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> wsdlImporters**](wsdlimporters.md)</span><span class="sxs-lookup"><span data-stu-id="447d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)</span></span>  
<span data-ttu-id="447d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> clase wsdlImporter**</span><span class="sxs-lookup"><span data-stu-id="447d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="447d9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="447d9-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="447d9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="447d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="447d9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="447d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="447d9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="447d9-112">Attributes</span></span>  
  
|<span data-ttu-id="447d9-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="447d9-113">Attribute</span></span>|<span data-ttu-id="447d9-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="447d9-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="447d9-115">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="447d9-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="447d9-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="447d9-116">Child Elements</span></span>  
 <span data-ttu-id="447d9-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="447d9-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="447d9-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="447d9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="447d9-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="447d9-119">Element</span></span>|<span data-ttu-id="447d9-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="447d9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="447d9-121">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="447d9-121">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="447d9-122">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="447d9-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="447d9-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="447d9-123">Remarks</span></span>  
 <span data-ttu-id="447d9-124">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="447d9-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="447d9-125">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="447d9-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="447d9-126">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="447d9-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="447d9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="447d9-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="447d9-128">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="447d9-128">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="447d9-129">Clientes</span><span class="sxs-lookup"><span data-stu-id="447d9-129">Clients</span></span>](../../../wcf/feature-details/clients.md)
