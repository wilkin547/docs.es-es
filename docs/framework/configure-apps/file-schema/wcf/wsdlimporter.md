---
description: 'Más información acerca de: <wsdlImporter>'
title: <wsdlImporter>
ms.date: 03/30/2017
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
ms.openlocfilehash: 9f95d4e6b940f36e9142eb9865327c772e3ce4db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682155"
---
# \<wsdlImporter>

<span data-ttu-id="78c47-102">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="78c47-102">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsdlImporters>**](wsdlimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsdlImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="78c47-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78c47-103">Syntax</span></span>  
  
```xml  
<metadata>
  <wsdlImporters>
    <wsdlImporter type="string" />
  </wsdlImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78c47-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="78c47-104">Attributes and Elements</span></span>  

 <span data-ttu-id="78c47-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="78c47-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78c47-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="78c47-106">Attributes</span></span>  
  
|<span data-ttu-id="78c47-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="78c47-107">Attribute</span></span>|<span data-ttu-id="78c47-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="78c47-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="78c47-109">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="78c47-109">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="78c47-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="78c47-110">Child Elements</span></span>  

 <span data-ttu-id="78c47-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="78c47-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="78c47-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="78c47-112">Parent Elements</span></span>  
  
|<span data-ttu-id="78c47-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="78c47-113">Element</span></span>|<span data-ttu-id="78c47-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="78c47-114">Description</span></span>|  
|-------------|-----------------|  
|[\<wsdlImporters>](wsdlimporters.md)|<span data-ttu-id="78c47-115">Especifica todos los importadores WDSL que importan metadatos de Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="78c47-115">Specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78c47-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78c47-116">Remarks</span></span>  

 <span data-ttu-id="78c47-117">Un importador WDSL se usa para importar metadatos, así como para convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="78c47-117">A WSDL importer is used to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="78c47-118">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="78c47-118">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="78c47-119">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="78c47-119">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78c47-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="78c47-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.WsdlImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="78c47-121">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="78c47-121">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="78c47-122">Clientes</span><span class="sxs-lookup"><span data-stu-id="78c47-122">Clients</span></span>](../../../wcf/feature-details/clients.md)
