---
title: '&lt;wsdlImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9f4fe6c82d0a6f53dfa05a82622e0412280212cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltwsdlimportergt"></a><span data-ttu-id="4aedc-102">&lt;wsdlImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="4aedc-102">&lt;wsdlImporter&gt;</span></span>
<span data-ttu-id="4aedc-103">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="4aedc-103">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
<span data-ttu-id="4aedc-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4aedc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4aedc-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="4aedc-105">\<client></span></span>  
<span data-ttu-id="4aedc-106">\<metadatos ></span><span class="sxs-lookup"><span data-stu-id="4aedc-106">\<metadata></span></span>  
<span data-ttu-id="4aedc-107">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="4aedc-107">\<wsdlImporters></span></span>  
<span data-ttu-id="4aedc-108">\<wsdlImporter ></span><span class="sxs-lookup"><span data-stu-id="4aedc-108">\<wsdlImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aedc-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4aedc-109">Syntax</span></span>  
  
```xml  
<metadata>  
  <wsdlImporters>  
    <wsdlImporter type="string" />  
  </wsdlImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4aedc-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4aedc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4aedc-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4aedc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4aedc-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4aedc-112">Attributes</span></span>  
  
|<span data-ttu-id="4aedc-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4aedc-113">Attribute</span></span>|<span data-ttu-id="4aedc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4aedc-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="4aedc-115">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="4aedc-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4aedc-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4aedc-116">Child Elements</span></span>  
 <span data-ttu-id="4aedc-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4aedc-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4aedc-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4aedc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="4aedc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="4aedc-119">Element</span></span>|<span data-ttu-id="4aedc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4aedc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4aedc-121">\<wsdlImporters ></span><span class="sxs-lookup"><span data-stu-id="4aedc-121">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="4aedc-122">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="4aedc-122">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aedc-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4aedc-123">Remarks</span></span>  
 <span data-ttu-id="4aedc-124">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="4aedc-124">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="4aedc-125">Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="4aedc-125">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="4aedc-126">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="4aedc-126">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aedc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aedc-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 <xref:System.ServiceModel.Description.WsdlImporter>  
 [<span data-ttu-id="4aedc-128">Configuración de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="4aedc-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="4aedc-129">Clientes</span><span class="sxs-lookup"><span data-stu-id="4aedc-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
