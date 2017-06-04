---
title: "Implementaci&#243;n de un proyecto de biblioteca de WFC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Implementaci&#243;n de un proyecto de biblioteca de WFC
En este tema se describe cómo puede implementar un proyecto de biblioteca de servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Implementación de una biblioteca de servicios de WFC  
 Una biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una biblioteca de vínculo dinámico \(DLL\).Como tal, no se puede ejecutar por sí misma.Se ha de implementar en un entorno de hospedaje.Para obtener más información sobre este proceso, vea [Hospedaje y uso de servicios de WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se puede implementar como cualquier otro servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Sin embargo, tenga en cuenta que [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no admite la configuración de los archivos DLL.<xref:System.Configuration> admite un archivo de configuración por dominio de aplicación.El proyecto de biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] palia esta limitación proporcionando un archivo App.config para la biblioteca durante el desarrollo.Sin embargo, el archivo App.config no se reconoce después de la implementación.  
  
 Tiene que pasar su código de configuración al archivo de configuración reconocido por su entorno de hospedaje.Para el autohospedaje, debería copiar el contenido del archivo App.config en el archivo App.config del hospedaje ejecutable.Si utiliza IIS para hospedar su servicio, debería copiar el contenido del archivo App.config en el archivo Web.config del directorio virtual.