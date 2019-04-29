---
title: Implementación de un proyecto de biblioteca de WFC
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 1ba26a7e68fe262dc5f4f569647af1ebb94e03a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785130"
---
# <a name="deploying-a-wcf-library-project"></a>Implementación de un proyecto de biblioteca de WFC
Este tema describe cómo puede implementar un proyecto de biblioteca de servicio de Windows Communication Foundation (WCF).  
  
## <a name="deploying-a-wcf-service-library"></a>Implementación de una biblioteca de servicios de WFC  
 Una biblioteca de servicios WCF es una biblioteca de vínculos dinámicos (DLL). Como tal, no se puede ejecutar por sí misma. Se ha de implementar en un entorno de hospedaje. Para obtener más información sobre este proceso, consulte [alojamiento y consumo de servicios WCF](https://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una biblioteca de servicios WCF puede implementarse como cualquier otro servicio WCF. Sin embargo, tenga en cuenta que [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no admite la configuración de los archivos DLL. <xref:System.Configuration> admite un archivo de configuración por dominio de aplicación. El proyecto de biblioteca de servicio WCF palia esta limitación proporcionando un archivo App.config para la biblioteca durante el desarrollo. Sin embargo, el archivo App.config no se reconoce después de la implementación.  
  
 Tiene que pasar su código de configuración al archivo de configuración reconocido por su entorno de hospedaje. Para el autohospedaje, debería copiar el contenido del archivo App.config en el archivo App.config del hospedaje ejecutable. Si utiliza IIS para hospedar su servicio, debería copiar el contenido del archivo App.config en el archivo Web.config del directorio virtual.
