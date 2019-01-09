---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 43c1a50c740cd9c75ee641e4ac4d0fa8ea3ca36b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144995"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="e1d3e-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="e1d3e-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="e1d3e-103">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="e1d3e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e1d3e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e1d3e-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="e1d3e-105">\<client></span></span>  
<span data-ttu-id="e1d3e-106">\<metadatos ></span><span class="sxs-lookup"><span data-stu-id="e1d3e-106">\<metadata></span></span>  
<span data-ttu-id="e1d3e-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="e1d3e-107">\<wsdlImporters></span></span>  
<span data-ttu-id="e1d3e-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="e1d3e-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1d3e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1d3e-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1d3e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e1d3e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e1d3e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1d3e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e1d3e-112">Attributes</span></span>  
  
|<span data-ttu-id="e1d3e-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e1d3e-113">Attribute</span></span>|<span data-ttu-id="e1d3e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1d3e-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e1d3e-115">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1d3e-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e1d3e-116">Child Elements</span></span>  
 <span data-ttu-id="e1d3e-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1d3e-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e1d3e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e1d3e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e1d3e-119">Element</span></span>|<span data-ttu-id="e1d3e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1d3e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1d3e-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="e1d3e-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="e1d3e-122">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1d3e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1d3e-123">Remarks</span></span>  
 <span data-ttu-id="e1d3e-124">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="e1d3e-125">Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="e1d3e-126">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="e1d3e-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d3e-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1d3e-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="e1d3e-128">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="e1d3e-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="e1d3e-129">Clientes</span><span class="sxs-lookup"><span data-stu-id="e1d3e-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
