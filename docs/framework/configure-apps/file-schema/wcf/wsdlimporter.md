---
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 82704aa40b508f1b1e2237c9768a7b7599c5c87e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158596"
---
# \<wsdlImporter>

<span data-ttu-id="41df2-101">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="41df2-101">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="41df2-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41df2-102">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41df2-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="41df2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="41df2-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="41df2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41df2-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="41df2-105">Attributes</span></span>  
  
|<span data-ttu-id="41df2-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="41df2-106">Attribute</span></span>|<span data-ttu-id="41df2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="41df2-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="41df2-108">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="41df2-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41df2-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="41df2-109">Child Elements</span></span>  

 <span data-ttu-id="41df2-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="41df2-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41df2-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="41df2-111">Parent Elements</span></span>  
  
|<span data-ttu-id="41df2-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="41df2-112">Element</span></span>|<span data-ttu-id="41df2-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="41df2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="41df2-114">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="41df2-114">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41df2-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41df2-115">Remarks</span></span>  

 <span data-ttu-id="41df2-116">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="41df2-116">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="41df2-117">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="41df2-117">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="41df2-118">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="41df2-118">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41df2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="41df2-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="41df2-120">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="41df2-120">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="41df2-121">Clientes</span><span class="sxs-lookup"><span data-stu-id="41df2-121">Clients</span></span>](../../../wcf/feature-details/clients.md)
