---
description: Más información acerca de cómo implementar servicios
title: Desarrollo de servicios
ms.date: 03/30/2017
ms.assetid: ac361bfb-017d-4da9-a2d7-fc0fb72d65bb
ms.openlocfilehash: 6a0b1d88410b865f57cd1eb16f070842a75ddb07
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646002"
---
# <a name="deploying-services"></a>Desarrollo de servicios

En este tema se describe cómo puede implementar una aplicación Windows Communication Foundation (WCF) en un entorno de tiempo de ejecución.  
  
## <a name="choosing-the-hosting-environment-for-your-application"></a>Elegir el entorno de alojamiento para su aplicación  

 Los servicios WCF están diseñados para ejecutarse en cualquier proceso de Windows que admita código administrado. Para activarse, se debe hospedar un servicio dentro de un entorno de tiempo en ejecución que lo crea y controla su contexto y duración. Las opciones de alojamiento son ejecutarse dentro de la aplicación de consola más simple a entornos de servidor como un servicio de Windows, Internet Information Server (IIS), o dentro de un proceso de trabajo administrado por el Servicio de Activación de Windows (WAS). Para revisar las distintas opciones de hospedaje de la aplicación WCF, vea [servicios de hospedaje](../hosting-services.md).  
  
## <a name="see-also"></a>Vea también

- [Hospedar aplicaciones de WPF](../feature-details/hosting.md)
- [Servicios de hospedaje](../hosting-services.md)
