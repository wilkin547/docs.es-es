---
title: Extensión del sistema de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7113120a3cde6b4e6a7eb1d329da625e25996952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272988"
---
# <a name="extending-the-metadata-system"></a>Extensión del sistema de metadatos

El sistema de metadatos de Windows Communication Foundation (WCF) es un grupo de clases e interfaces que representan los metadatos necesarios para implementar aplicaciones basadas en servicio. Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web (WSDL) o las aserciones personalizadas de WS-PolicyAttachments.  
  
## <a name="in-this-section"></a>En esta sección  

 [Exportación de metadatos personalizados para una extensión WCF](exporting-custom-metadata-for-a-wcf-extension.md)  
 Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> para incrustar las aserciones de directiva personalizadas en documentos WSDL.  
  
 [Importación de  metadatos personalizados para una extensión de WCF](importing-custom-metadata-for-a-wcf-extension.md)  
 Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.  
  
 [Publicación y recuperación de metadatos a través de un enlace personalizado](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Describe cómo intercambiar los metadatos sobre los enlaces personalizados.
