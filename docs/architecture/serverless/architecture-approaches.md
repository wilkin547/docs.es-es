---
title: 'Enfoques de arquitectura: aplicaciones sin servidor'
description: Introducción a los enfoques de arquitectura para la creación de aplicaciones empresariales basadas en la nube, desde arquitecturas de N niveles hasta sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522900"
---
# <a name="architecture-approaches"></a>Enfoques de arquitectura

Comprender los enfoques existentes para diseñar aplicaciones empresariales ayuda a aclarar el rol que desempeña sin servidor. Existen muchos enfoques y patrones que han evolucionado en más de décadas de desarrollo de software y todos tienen sus propias ventajas e inconvenientes. En muchos casos, es posible que la solución final no implique la decisión de un solo enfoque, sino que pueda integrar varios enfoques. Los escenarios de migración suelen implicar el cambio de un enfoque de arquitectura a otro a través de un enfoque híbrido.

En este capítulo se proporciona información general sobre los patrones de arquitectura física y lógica de las aplicaciones empresariales.

## <a name="architecture-patterns"></a>Patrones de arquitectura

Las aplicaciones empresariales modernas siguen una variedad de patrones de arquitectura. En esta sección se representa una encuesta de patrones comunes. Los patrones que se enumeran aquí no son necesariamente todos los procedimientos recomendados, sino que muestran diferentes enfoques.

Para obtener más información, consulte la [Guía de arquitectura de aplicaciones de Azure](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Monolitos

Muchas aplicaciones empresariales siguen un patrón de monolito. Las aplicaciones heredadas suelen implementarse como monolíticos. En el patrón de monolítico, todos los problemas de la aplicación se encuentran en una sola implementación. Todo lo que se deriva de la interfaz de usuario a las llamadas de base de datos se incluye en el mismo código base.

![Arquitectura de monolito](./media/monolith-architecture.png)

El enfoque de monolítico tiene varias ventajas. A menudo es fácil extraer una sola base de código y comenzar a trabajar. El tiempo de puesta en marcha puede ser menor y crear entornos de prueba es tan sencillo como proporcionar una nueva copia. El monolito puede estar diseñado para incluir varios componentes y aplicaciones.

Desafortunadamente, el patrón de monolítico tiende a desglosar a escala. Las principales desventajas del enfoque de monolítico incluyen:

- Es difícil trabajar en paralelo en la misma base de código.
- Cualquier cambio, con independencia de lo trivial, requiere la implementación de una nueva versión de toda la aplicación.
- La refactorización afecta potencialmente a toda la aplicación.
- A menudo, la única solución que se debe escalar es crear varias copias de la monolítica que consumen muchos recursos.
- A medida que se expandan sistemas o se adquieran otros sistemas, la integración puede ser difícil.
- Puede ser difícil de probar debido a la necesidad de configurar todo el monolito.
- La reutilización de código es desafiante y a menudo las demás aplicaciones acaban teniendo sus propias copias de código.

Muchas empresas ven a la nube como una oportunidad para migrar aplicaciones monolíticas y, al mismo tiempo, refactorizarlas en patrones más fáciles de usar. Es habitual dividir las aplicaciones y los componentes individuales para que se mantengan, implementen y escalen por separado.

## <a name="n-layer-applications"></a>Aplicaciones de N capas

Lógica de aplicación de partición de aplicación de N niveles en capas específicas. Las capas más comunes incluyen:

- Interfaz de usuario
- Lógica de negocios
- Acceso a datos

Otras capas pueden incluir middleware, procesamiento por lotes y API. Es importante tener en cuenta que las capas son lógicas. Aunque se desarrollan en aislamiento, se pueden implementar en la misma plataforma de destino.

![Arquitectura de N capas](./media/n-layer-architecture.png)

Hay varias ventajas en el enfoque de N niveles, entre las que se incluyen:

- La refactorización está aislada en una capa.
- Los equipos pueden compilar, probar, implementar y mantener capas independientes de forma independiente.
- Las capas se pueden intercambiar, por ejemplo, la capa de datos puede tener acceso a varias bases de datos sin necesidad de realizar cambios en la capa de la interfaz de usuario.

Puede usarse sin servidor para implementar una o más capas.

## <a name="microservices"></a>Microservicios

Las arquitecturas de **[microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contienen características comunes que incluyen:

- Las aplicaciones se componen de varios servicios pequeños.
- Cada servicio se ejecuta en su propio proceso.
- Los servicios están alineados en torno a los dominios empresariales.
- Los servicios se comunican a través de API ligeras, normalmente con HTTP como transporte.
- Los servicios se pueden implementar y actualizar de forma independiente.
- Los servicios no dependen de un único almacén de datos.
- El sistema se ha diseñado pensando en los errores y la aplicación puede seguir ejecutándose incluso cuando se produce un error en ciertos servicios.

Los microservicios no tienen que ser mutuamente excluyentes a otros enfoques de arquitectura. Por ejemplo, una arquitectura de N niveles puede usar microservicios para el nivel intermedio. También es posible implementar microservicios de varias maneras, desde directorios virtuales en hosts de IIS hasta contenedores. Las características de los microservicios hacen que sean especialmente ideales para implementaciones sin servidor.

![Arquitectura de microservicios](./media/microservices-architecture.png)

Entre las ventajas de las arquitecturas de microservicios se incluyen:

- La refactorización suele estar aislada en un único servicio.
- Los servicios se pueden actualizar de forma independiente entre sí.
- La resistencia y la elasticidad se pueden ajustar a las demandas de los servicios individuales.
- El desarrollo puede realizarse en paralelo en diferentes equipos y plataformas.
- Es más fácil escribir pruebas exhaustivas para servicios aislados.

Los microservicios incluyen sus propios desafíos, entre los que se incluyen:

- Determinar qué servicios están disponibles y cómo llamarlos.
- Administrar el ciclo de vida de los servicios.
- Comprender cómo se ajustan los servicios en la aplicación global.
- Pruebas completas del sistema de las llamadas realizadas en servicios dispares.

En última instancia, hay soluciones que abordan todos estos desafíos, entre las que se incluyen las ventajas de sin servidor que se describen más adelante.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](architecture-deployment-approaches.md)
