---
title: Implementación de un proyecto de biblioteca de WFC
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: fb400a4d1ebba691222ad7fc9d2c09f1051591da
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="deploying-a-wcf-library-project"></a>Implementación de un proyecto de biblioteca de WFC
Este tema describe cómo se puede implementar un proyecto de biblioteca de servicio de Windows Communication Foundation (WCF).  
  
## <a name="deploying-a-wcf-service-library"></a>Implementación de una biblioteca de servicios de WFC  
 Una biblioteca de servicios WCF es una biblioteca de vínculos dinámicos (DLL). Como tal, no se puede ejecutar por sí misma. Se ha de implementar en un entorno de hospedaje. Para obtener más información acerca de este proceso, consulte [de hospedaje y consumo de servicios WCF](http://go.microsoft.com/fwlink/?LinkId=99932).  
  
 Una biblioteca de servicios WCF puede implementarse como cualquier otro servicio WCF. Sin embargo, tenga en cuenta que [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] no admite la configuración de los archivos DLL. <xref:System.Configuration> admite un archivo de configuración por dominio de aplicación. El proyecto de biblioteca de servicio WCF palia esta limitación proporcionando un archivo App.config para la biblioteca durante el desarrollo. Sin embargo, el archivo App.config no se reconoce después de la implementación.  
  
 Tiene que pasar su código de configuración al archivo de configuración reconocido por su entorno de hospedaje. Para el autohospedaje, debería copiar el contenido del archivo App.config en el archivo App.config del hospedaje ejecutable. Si utiliza IIS para hospedar su servicio, debería copiar el contenido del archivo App.config en el archivo Web.config del directorio virtual.
