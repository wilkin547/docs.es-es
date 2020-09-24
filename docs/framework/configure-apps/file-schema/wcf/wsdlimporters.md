---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: c88fb549674f9cad59c4e23a0cc4099a378bec9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158583"
---
# \<wsdlImporters>

<span data-ttu-id="eac70-101">Este elemento de configuración especifica todos los importadores de WSDL que importan de metadatos del Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy.</span><span class="sxs-lookup"><span data-stu-id="eac70-101">This configuration element specifies all the WSDL importers that imports Web Services Description Language (WSDL) 1.1 metadata with WS-Policy attachments.</span></span> <span data-ttu-id="eac70-102">Cada elemento secundario es un <`wsdlImporter`> que especifica la forma de importar metadatos, así como convertir esa información en varias clases que representan información de contrato y de extremo.</span><span class="sxs-lookup"><span data-stu-id="eac70-102">Each child element is a <`wsdlImporter`> that specifies the way to import metadata as well as convert that information into various classes that represent contract and endpoint information.</span></span> <span data-ttu-id="eac70-103">Puede importar de manera selectiva información de contrato y punto de conexión y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión.</span><span class="sxs-lookup"><span data-stu-id="eac70-103">It can selectively import contract and endpoint information and properties that expose any import errors and accept type information relevant to the import and conversion process.</span></span> <span data-ttu-id="eac70-104">También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="eac70-104">It also supports importing binding information and properties that provide access to any policy documents, WSDL documents, WSDL extensions, and XML schema documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac70-105">Vea también</span><span class="sxs-lookup"><span data-stu-id="eac70-105">See also</span></span>

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [<span data-ttu-id="eac70-106">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="eac70-106">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="eac70-107">Clientes</span><span class="sxs-lookup"><span data-stu-id="eac70-107">Clients</span></span>](../../../wcf/feature-details/clients.md)
