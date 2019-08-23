---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: da9ab00c86e7f2657bfc28724d328ccbbc6957b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915167"
---
# <a name="wsdlimporters"></a><span data-ttu-id="2bc1e-101">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="2bc1e-101">\<wsdlImporters></span></span>
<span data-ttu-id="2bc1e-102">Este elemento de configuración especifica todos los importadores de WSDL que importan de metadatos del Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="2bc1e-103">Cada elemento secundario es un <`wsdlImporter`> que especifica la forma de importar metadatos, así como convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="2bc1e-104">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="2bc1e-105">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="2bc1e-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc1e-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bc1e-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="2bc1e-107">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="2bc1e-107">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="2bc1e-108">Clientes</span><span class="sxs-lookup"><span data-stu-id="2bc1e-108">Clients</span></span>](../../../wcf/feature-details/clients.md)
