---
title: "Implementación de un proyecto de biblioteca de WFC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04567b0b06ef5c8f105e866e150bfaa221d64057
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="deploying-a-wcf-library-project"></a>Implementación de un proyecto de biblioteca de WFC
En este tema se describe cómo puede implementar un proyecto de biblioteca de servicios de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## <a name="deploying-a-wcf-service-library"></a>Implementación de una biblioteca de servicios de WFC  
 Una biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una biblioteca de vínculo dinámico (DLL). Como tal, no se puede ejecutar por sí misma. Se ha de implementar en un entorno de hospedaje. Para obtener más información acerca de este proceso, consulte [de hospedaje y consumo de servicios WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se puede implementar como cualquier otro servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Sin embargo, tenga en cuenta que [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no admite la configuración de los archivos DLL. <xref:System.Configuration> admite un archivo de configuración por dominio de aplicación. El proyecto de biblioteca de servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] palia esta limitación proporcionando un archivo App.config para la biblioteca durante el desarrollo. Sin embargo, el archivo App.config no se reconoce después de la implementación.  
  
 Tiene que pasar su código de configuración al archivo de configuración reconocido por su entorno de hospedaje. Para el autohospedaje, debería copiar el contenido del archivo App.config en el archivo App.config del hospedaje ejecutable. Si utiliza IIS para hospedar su servicio, debería copiar el contenido del archivo App.config en el archivo Web.config del directorio virtual.
