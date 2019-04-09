---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 1f34486296465b3ea0b5b05bd9492062c85ad8c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134438"
---
# <a name="wsdlimporter"></a><span data-ttu-id="e0ba8-101">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="e0ba8-101">\<wsdlImporter></span></span>
<span data-ttu-id="e0ba8-102">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="e0ba8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e0ba8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e0ba8-104">\<client></span><span class="sxs-lookup"><span data-stu-id="e0ba8-104">\<client></span></span>  
<span data-ttu-id="e0ba8-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="e0ba8-105">\<metadata></span></span>  
<span data-ttu-id="e0ba8-106">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="e0ba8-106">\<wsdlImporters></span></span>  
<span data-ttu-id="e0ba8-107">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="e0ba8-107">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ba8-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0ba8-108">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0ba8-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e0ba8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e0ba8-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0ba8-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e0ba8-111">Attributes</span></span>  
  
|<span data-ttu-id="e0ba8-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e0ba8-112">Attribute</span></span>|<span data-ttu-id="e0ba8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0ba8-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e0ba8-114">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0ba8-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e0ba8-115">Child Elements</span></span>  
 <span data-ttu-id="e0ba8-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0ba8-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e0ba8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e0ba8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e0ba8-118">Element</span></span>|<span data-ttu-id="e0ba8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0ba8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0ba8-120">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="e0ba8-120">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="e0ba8-121">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-121">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0ba8-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0ba8-122">Remarks</span></span>  
 <span data-ttu-id="e0ba8-123">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-123">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="e0ba8-124">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-124">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="e0ba8-125">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="e0ba8-125">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ba8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0ba8-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="e0ba8-127">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="e0ba8-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="e0ba8-128">Clientes</span><span class="sxs-lookup"><span data-stu-id="e0ba8-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
