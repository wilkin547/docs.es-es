---
title: Desarrollo de servicios
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 2c3cd17b597fafcd02b9155089bc583fafbc9dea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085770"
---
# <a name="deploying-services"></a>Desarrollo de servicios
Este tema describe cómo puede implementar una aplicación de Windows Communication Foundation (WCF) en un entorno de tiempo de ejecución.  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a>Elegir el entorno de alojamiento para su aplicación  
 Servicios WCF están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado. Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración. Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS). Para revisar las distintas opciones de hospedaje para la aplicación de WCF, vea [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="see-also"></a>Vea también

- [Hospedaje](../../../../docs/framework/wcf/feature-details/hosting.md)
- [Servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md)
