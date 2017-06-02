---
title: "Extensi&#243;n del sistema de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "extensión de metadatos [WCF]"
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Extensi&#243;n del sistema de metadatos
El sistema de metadatos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] es un grupo de clases e interfaces que representan los metadatos requeridos para implementar las aplicaciones basadas en el servicio.Modifique o extienda las clases o implemente y configure las interfaces para exportar e importar metadatos personalizados, como las extensiones de Lenguaje de descripción de servicios Web \(WSDL\) o las aserciones personalizadas de WS\-PolicyAttachments.  
  
## En esta sección  
 [Exportación de metadatos personalizados para una extensión WCF](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=fullName> para incrustar las aserciones de directiva personalizadas en documentos WSDL.  
  
 [Importación de  metadatos personalizados para una extensión de WCF](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 Describe cómo implementar y utilizar la interfaz <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=fullName> para leer y contestar las aserciones de directiva personalizadas en documentos WSDL.  
  
 [Publicación y recuperación de metadatos a través de un enlace personalizado](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 Describe cómo intercambiar los metadatos sobre los enlaces personalizados.