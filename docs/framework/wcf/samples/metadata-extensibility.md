---
title: "Extensibilidad de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Extensibilidad de metadatos
Esta sección contiene ejemplos que muestran los metadatos personalizados.  
  
## En esta sección  
 [Extremo personalizado de metadatos seguros](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 Muestra cómo implementar un servicio con un extremo de metadatos seguro que utiliza uno de los enlaces de intercambio que no es de metadatos y cómo configurar [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) o clientes para capturar los metadatos de este extremo de metadatos.  
  
 [Publicación de WSDL personalizada](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)  
 Muestra cómo implementar un <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=fullName> en un atributo <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> personalizado para exportar las propiedades de atributo como anotaciones WSDL, entre otras funcionalidades.