---
description: 'Más información acerca de: <metadata>'
title: <metadata>
ms.date: 03/30/2017
ms.assetid: d09653eb-e355-4c73-b87b-28f93d56480d
ms.openlocfilehash: 6cc1e472dbada72fe6a375a6832e7c9128dcda6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684430"
---
# \<metadata>

<span data-ttu-id="167ab-102">Especifica cómo se pueden procesar los metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="167ab-102">Specifies how service metadata can be processed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<metadata>**  
  
## <a name="syntax"></a><span data-ttu-id="167ab-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="167ab-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="167ab-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="167ab-104">Attributes and Elements</span></span>  

 <span data-ttu-id="167ab-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="167ab-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="167ab-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="167ab-106">Attributes</span></span>  

 <span data-ttu-id="167ab-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="167ab-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="167ab-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="167ab-108">Child Elements</span></span>  
  
|<span data-ttu-id="167ab-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="167ab-109">Element</span></span>|<span data-ttu-id="167ab-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="167ab-110">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="167ab-111">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="167ab-111">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span> <span data-ttu-id="167ab-112">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="167ab-112">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="167ab-113">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="167ab-113">Specifies all the WSDL importers that import Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="167ab-114">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="167ab-114">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="167ab-115">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="167ab-115">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="167ab-116">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="167ab-116">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="167ab-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="167ab-117">Parent Elements</span></span>  
  
|<span data-ttu-id="167ab-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="167ab-118">Element</span></span>|<span data-ttu-id="167ab-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="167ab-119">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="167ab-120">La sección  cliente define una lista de puntos de conexión a los que un cliente puede conectarse.</span><span class="sxs-lookup"><span data-stu-id="167ab-120">The client section defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="167ab-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="167ab-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="167ab-122">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="167ab-122">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="167ab-123">Clientes</span><span class="sxs-lookup"><span data-stu-id="167ab-123">Clients</span></span>](../../../wcf/feature-details/clients.md)
