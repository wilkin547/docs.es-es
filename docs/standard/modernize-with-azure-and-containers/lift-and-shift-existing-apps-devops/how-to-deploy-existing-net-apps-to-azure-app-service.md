---
title: "Cómo implementar aplicaciones de .NET existentes al servicio de aplicaciones de Azure"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cómo implementar aplicaciones de .NET existentes al servicio de aplicaciones de Azure"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: aefcd79574cbbf6b3759bfa6cc0f9e46a58244ce
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a>Cómo implementar aplicaciones de .NET existentes al servicio de aplicaciones de Azure 

La característica de las aplicaciones Web de servicio de aplicaciones de Azure es una plataforma de proceso totalmente administrado que está optimizada para hospedar aplicaciones web y sitios Web. Esta oferta de PaaS en Microsoft Azure permite centrarse en la lógica de negocios, mientras Azure se encarga de la infraestructura para ejecutar y escalar sus aplicaciones.

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a>Validar sitios y migrar al servicio de aplicación con el Asistente de migración de Azure aplicación de servicio

Cuando se crea una nueva aplicación en Visual Studio, mover la aplicación al servicio de aplicaciones normalmente es sencillo. Sin embargo, si va a migrar una aplicación existente al servicio de aplicaciones, primero debe evaluar si todas las dependencias de su aplicación son compatibles con el servicio de aplicaciones. Esto incluye las dependencias como sistema operativo del servidor y cualquier software de terceros que está instalado en el servidor.

Puede usar [Azure aplicación servicio Migration Assistant](https://www.migratetoazure.net/) para analizar sitios y, a continuación, migrarlos al servicio de aplicaciones de servidores web de Windows y Linux. Como parte de la migración, la herramienta crea aplicaciones web y bases de datos de Azure según sea necesario, publica contenido y publica la base de datos.

Azure aplicación servicio Migration Assistant admite la migración de IIS que se ejecuta en Windows Server a la nube. Servicio de aplicaciones es compatible con Windows Server 2003 y versiones posteriores.

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> **Figura 4-5.** Usar el Asistente de migración de servicio de aplicaciones de Azure

Asistente para la migración del servicio de aplicación es una herramienta que mueve los sitios Web de los servidores web a la nube de Azure.

Después de migra un sitio Web al servicio de aplicaciones, el sitio tiene todo que lo necesario para ejecutar de forma segura y eficaz. Los sitios se configuran y ejecutan automáticamente en el servicio de PaaS de nube de Azure (servicio de aplicaciones).

La herramienta de migración de servicio de aplicaciones puede analizar los sitios Web e informar sobre su compatibilidad para mover a un servicio de aplicaciones. Si está satisfecho con el análisis, puede dejar que el Asistente para la migración de servicio aplicación migrar contenido, datos y configuración. Si un sitio no es bastante compatible, la herramienta de migración indica lo que necesita ajustar para que funcione.

### <a name="additional-resources"></a>Recursos adicionales

- **Asistente de migración de servicio de aplicaciones de Azure**

    [https://www.migratetoazure.net/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
[Anterior](what-about-cloud-optimized-applications.md)
[Siguiente](deploy-existing-net-apps-as-windows-containers.md)
