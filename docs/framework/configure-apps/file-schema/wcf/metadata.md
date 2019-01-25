---
title: '&lt;metadata&gt;'
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 017a58c7e48a1c4c5b4abdcb7cc603e95f6516a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723971"
---
# <a name="ltmetadatagt"></a><span data-ttu-id="e9612-102">&lt;metadata&gt;</span><span class="sxs-lookup"><span data-stu-id="e9612-102">&lt;metadata&gt;</span></span>
<span data-ttu-id="e9612-103">Especifica cómo se pueden procesar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="e9612-103">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="e9612-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e9612-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e9612-105">\<client></span><span class="sxs-lookup"><span data-stu-id="e9612-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9612-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9612-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <metadata>
      <policyImporters>
        <policyImporter type="string" />
      </policyImporters>
      <wsdlImporters>
        <wsdlImporter type="string" />
      </wsdlImporters>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9612-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e9612-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e9612-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e9612-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9612-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e9612-109">Attributes</span></span>  
 <span data-ttu-id="e9612-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e9612-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e9612-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e9612-111">Child Elements</span></span>  
  
|<span data-ttu-id="e9612-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9612-112">Element</span></span>|<span data-ttu-id="e9612-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9612-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9612-114">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="e9612-114">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="e9612-115">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="e9612-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="e9612-116">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="e9612-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="e9612-117">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="e9612-117">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="e9612-118">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="e9612-118">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="e9612-119">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="e9612-119">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="e9612-120">Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="e9612-120">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="e9612-121">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="e9612-121">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9612-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e9612-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9612-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9612-123">Element</span></span>|<span data-ttu-id="e9612-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9612-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9612-125">\<client></span><span class="sxs-lookup"><span data-stu-id="e9612-125">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="e9612-126">La sección  cliente define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="e9612-126">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9612-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9612-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="e9612-128">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="e9612-128">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="e9612-129">Clientes</span><span class="sxs-lookup"><span data-stu-id="e9612-129">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
