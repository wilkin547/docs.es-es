---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 75f88219ab73d321b3e04c140bbfe964aed0b83a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225513"
---
# <a name="wsdlimporters"></a><span data-ttu-id="c2eff-101">\<wsdlImporters></span><span class="sxs-lookup"><span data-stu-id="c2eff-101">\<wsdlImporters></span></span>
<span data-ttu-id="c2eff-102">Este elemento de configuración especifica todos los importadores de WSDL que importan de metadatos del Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="c2eff-102">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="c2eff-103">Cada elemento secundario es un <`wsdlImporter`> que especifica la forma de importar metadatos, así como convertir esa información en varias clases que representan información de contrato y punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="c2eff-103">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="c2eff-104">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="c2eff-104">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="c2eff-105">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="c2eff-105">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2eff-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2eff-106">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="c2eff-107">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="c2eff-107">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="c2eff-108">Clientes</span><span class="sxs-lookup"><span data-stu-id="c2eff-108">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
