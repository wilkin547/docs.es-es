---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: 81fb25f6a77456608fd3cb0d5e73f67c7f7867c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274578"
---
# <a name="wsdlimporters"></a>\<wsdlImporters>
Este elemento de configuración especifica todos los importadores de WSDL que importan de metadatos del Lenguaje de descripción de servicios Web (WSDL) 1.1 con datos adjuntos de WS-Policy. Cada elemento secundario es un <`wsdlImporter`> que especifica la forma de importar metadatos, y también como convertir esa información en varias clases que representan información de contrato y de extremo. Puede importar de manera selectiva información de contrato y extremo y propiedades que exponen cualquier error de importación y aceptan información de tipo importante para el proceso de importación y conversión. También admite la importación de información de enlace y propiedades que proporcionan acceso a cualquier documento de directiva, documentos y extensiones WSDL y documentos de esquema XML.  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)
