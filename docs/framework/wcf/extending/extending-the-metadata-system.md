---
title: "Extensión del sistema de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aca7a7aba7ef4a40100e9858561d197916b71544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="extending-the-metadata-system"></a>Extensión del sistema de metadatos
El sistema de metadatos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es un grupo de clases e interfaces que representan los metadatos requeridos para implementar las aplicaciones basadas en el servicio. Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>En esta sección  
 [Exportación de metadatos personalizados para una extensión WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> para incrustar las aserciones de directiva personalizadas en documentos WSDL.  
  
 [Importación de metadatos personalizados para una extensión WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.  
  
 [Publicación y recuperación de metadatos a través de un enlace personalizado](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Describe cómo intercambiar los metadatos sobre los enlaces personalizados.
