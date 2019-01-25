---
title: '&lt;wsdlImporter&gt;'
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 5f3d53111c4d303146701b03d7e7b32833cd9edd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651050"
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="c1695-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="c1695-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="c1695-103">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="c1695-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="c1695-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c1695-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c1695-105">\<client></span><span class="sxs-lookup"><span data-stu-id="c1695-105">\<client></span></span>  
<span data-ttu-id="c1695-106">\<metadata></span><span class="sxs-lookup"><span data-stu-id="c1695-106">\<metadata></span></span>  
<span data-ttu-id="c1695-107">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="c1695-107">\<wsdlImporters></span></span>  
<span data-ttu-id="c1695-108">\<wsdlImporter></span><span class="sxs-lookup"><span data-stu-id="c1695-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1695-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1695-109">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1695-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1695-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c1695-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1695-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1695-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1695-112">Attributes</span></span>  
  
|<span data-ttu-id="c1695-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c1695-113">Attribute</span></span>|<span data-ttu-id="c1695-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1695-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="c1695-115">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="c1695-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1695-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1695-116">Child Elements</span></span>  
 <span data-ttu-id="c1695-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1695-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1695-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1695-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c1695-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1695-119">Element</span></span>|<span data-ttu-id="c1695-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1695-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1695-121">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="c1695-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="c1695-122">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="c1695-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1695-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1695-123">Remarks</span></span>  
 <span data-ttu-id="c1695-124">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c1695-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="c1695-125">Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="c1695-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="c1695-126">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="c1695-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1695-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1695-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="c1695-128">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="c1695-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c1695-129">Clientes</span><span class="sxs-lookup"><span data-stu-id="c1695-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
