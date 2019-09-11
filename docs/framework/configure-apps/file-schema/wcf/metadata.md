---
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 028e4d3fbe7bce06caa7497c8f95f3b293a4b068
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855228"
---
# <a name="metadata"></a><span data-ttu-id="a0d1e-101">\<metadata></span><span class="sxs-lookup"><span data-stu-id="a0d1e-101">\<metadata></span></span>
<span data-ttu-id="a0d1e-102">Especifica cómo se pueden procesar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-102">Specifies how service metadata can be processed.</span></span>  
  
<span data-ttu-id="a0d1e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0d1e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a0d1e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="a0d1e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="a0d1e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<metadatos >**</span><span class="sxs-lookup"><span data-stu-id="a0d1e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0d1e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0d1e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0d1e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0d1e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0d1e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0d1e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0d1e-110">Attributes</span></span>  
 <span data-ttu-id="a0d1e-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0d1e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0d1e-112">Child Elements</span></span>  
  
|<span data-ttu-id="a0d1e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0d1e-113">Element</span></span>|<span data-ttu-id="a0d1e-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a0d1e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0d1e-115">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="a0d1e-115">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="a0d1e-116">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-116">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="a0d1e-117">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[<span data-ttu-id="a0d1e-118">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="a0d1e-118">\<wsdlImporters></span></span>](wsdlimporters.md)|<span data-ttu-id="a0d1e-119">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-119">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="a0d1e-120">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-120">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="a0d1e-121">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-121">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="a0d1e-122">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-122">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0d1e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0d1e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0d1e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0d1e-124">Element</span></span>|<span data-ttu-id="a0d1e-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a0d1e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0d1e-126">\<client></span><span class="sxs-lookup"><span data-stu-id="a0d1e-126">\<client></span></span>](client.md)|<span data-ttu-id="a0d1e-127">La sección  cliente define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="a0d1e-127">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0d1e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0d1e-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="a0d1e-129">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="a0d1e-129">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="a0d1e-130">Clientes</span><span class="sxs-lookup"><span data-stu-id="a0d1e-130">Clients</span></span>](../../../wcf/feature-details/clients.md)
