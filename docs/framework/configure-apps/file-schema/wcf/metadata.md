---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 1ff59a3a1a075be4f8024a2a78921d1d50311327
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270802"
---
# <a name="metadata"></a><span data-ttu-id="216a7-101">\<metadata></span><span class="sxs-lookup"><span data-stu-id="216a7-101">\<metadata></span></span>
<span data-ttu-id="216a7-102">Especifica cómo se pueden procesar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="216a7-102">Specifies how service metadata can be processed.</span></span>  
  
 <span data-ttu-id="216a7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="216a7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="216a7-104">\<client></span><span class="sxs-lookup"><span data-stu-id="216a7-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="216a7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="216a7-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="216a7-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="216a7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="216a7-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="216a7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="216a7-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="216a7-108">Attributes</span></span>  
 <span data-ttu-id="216a7-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="216a7-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="216a7-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="216a7-110">Child Elements</span></span>  
  
|<span data-ttu-id="216a7-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="216a7-111">Element</span></span>|<span data-ttu-id="216a7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="216a7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="216a7-113">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="216a7-113">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="216a7-114">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="216a7-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="216a7-115">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="216a7-115">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="216a7-116">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="216a7-116">\<wsdlImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|<span data-ttu-id="216a7-117">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="216a7-117">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="216a7-118">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="216a7-118">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="216a7-119">Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="216a7-119">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="216a7-120">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="216a7-120">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="216a7-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="216a7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="216a7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="216a7-122">Element</span></span>|<span data-ttu-id="216a7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="216a7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="216a7-124">\<client></span><span class="sxs-lookup"><span data-stu-id="216a7-124">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="216a7-125">La sección  cliente define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="216a7-125">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="216a7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="216a7-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="216a7-127">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="216a7-127">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="216a7-128">Clientes</span><span class="sxs-lookup"><span data-stu-id="216a7-128">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
