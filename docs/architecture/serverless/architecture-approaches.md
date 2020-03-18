---
title: 'Enfoques de arquitectura: aplicaciones sin servidor'
description: Introducción a los enfoques de arquitectura para la creación de aplicaciones empresariales basadas en la nube, desde arquitecturas de N niveles hasta aplicaciones sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522900"
---
# <a name="architecture-approaches"></a>Enfoques de arquitectura

Conocer los enfoques actuales para diseñar aplicaciones empresariales ayuda a aclarar el rol que desempeñan las aplicaciones sin servidor. Existen muchos enfoques y patrones que han evolucionado a lo largo de décadas de desarrollo de software, y todos tienen sus ventajas e inconvenientes. En muchos casos, es posible que la solución final no implique un solo enfoque, sino la integración de varios enfoques. Los escenarios de migración suelen implicar el cambio de un enfoque de arquitectura a otro mediante un enfoque híbrido.

Este capítulo es una introducción a los patrones de arquitectura física y lógica de las aplicaciones empresariales.

## <a name="architecture-patterns"></a>Patrones de arquitectura

Las aplicaciones empresariales modernas siguen diversos patrones de arquitectura. En esta sección se recoge una selección de los patrones más comunes. Los patrones que se enumeran aquí no son necesariamente todos los procedimientos recomendados, sino que muestran diferentes enfoques.

Para más información, consulte [Guía de arquitectura de aplicaciones de Azure](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Monolitos

Muchas aplicaciones empresariales siguen un patrón monolítico. Las aplicaciones heredadas suelen implementarse como monolitos. En el patrón monolítico, todos los problemas de la aplicación se reducen a una sola implementación. Todo, desde la interfaz de usuario a las llamadas de base de datos, está incluido en el mismo código base.

![Arquitectura monolítica](./media/monolith-architecture.png)

El enfoque monolítico tiene varias ventajas. Normalmente es fácil comenzar a trabajar con una sola base de código. El tiempo de puesta en marcha puede ser menor y crear entornos de prueba es tan sencillo como hacer una nueva copia. El monolito puede estar diseñado para incluir varios componentes y aplicaciones.

Lamentablemente, el patrón monolítico tiende a desmoronarse a medida que aumenta su tamaño. Las principales desventajas del enfoque monolítico son:

- Es difícil trabajar en paralelo en la misma base de código.
- Cualquier cambio, por pequeño que sea, requiere la implementación de una nueva versión de toda la aplicación.
- La refactorización afecta potencialmente a toda la aplicación.
- La única solución para escalar suele ser crear varias copias del monolito, que consumen muchos recursos.
- La integración puede resultar difícil cuando los sistemas se expanden o se adquieren otros sistemas.
- Puede ser difícil de probar debido a la necesidad de configurar todo el monolito.
- La reutilización de código supone un reto y, a menudo, las demás aplicaciones acaban teniendo sus propias copias de código.

Muchas empresas ven la nube como una oportunidad para migrar aplicaciones monolíticas y, al mismo tiempo, refactorizarlas en patrones más fáciles de usar. Es habitual dividir las aplicaciones y los componentes individuales para mantenerlos, implementarlos y escalarlos por separado.

## <a name="n-layer-applications"></a>Aplicaciones de N capas

Las aplicaciones de N capas dividen la lógica de la aplicación en capas específicas. Las capas más comunes son:

- Interfaz de usuario
- Lógica empresarial
- Acceso a datos

Otras capas pueden incluir middleware, procesamiento por lotes y API. Es importante tener en cuenta que las capas son lógicas. Aunque se desarrollan de forma aislada, se pueden implementar en la misma plataforma de destino.

![Arquitectura de N capas](./media/n-layer-architecture.png)

El enfoque de N capas presenta varias ventajas, entre ellas:

- La refactorización está aislada en una capa.
- Los equipos pueden compilar, probar, implementar y mantener las capas de forma independiente.
- Las capas se pueden intercambiar, por ejemplo, la capa de datos puede tener acceso a varias bases de datos sin necesidad de realizar cambios en la capa de la interfaz de usuario.

Puede usarse sin servidor para implementar una o más capas.

## <a name="microservices"></a>Microservicios

Las arquitecturas de **[microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contienen características comunes que incluyen:

- Las aplicaciones se componen de varios servicios pequeños.
- Cada servicio se ejecuta en su propio proceso.
- Los servicios se corresponden con los dominios empresariales.
- Los servicios se comunican mediante API ligeras, normalmente con HTTP como transporte.
- Los servicios se pueden implementar y actualizar de forma independiente.
- Los servicios no dependen de un único almacén de datos.
- El sistema se ha diseñado pensando en los errores y la aplicación puede seguir ejecutándose incluso cuando se produce un error en ciertos servicios.

Los microservicios no excluyen otros enfoques de arquitectura. Por ejemplo, una arquitectura de N niveles puede usar microservicios para el nivel intermedio. Los microservicios se pueden implementar de varias maneras, desde directorios virtuales en hosts de IIS hasta contenedores. Las características de los microservicios hacen que sean especialmente ideales para implementaciones sin servidor.

![Arquitectura de microservicios](./media/microservices-architecture.png)

Entre las ventajas de las arquitecturas de microservicios se incluyen:

- La refactorización suele estar aislada en un único servicio.
- Los servicios se pueden actualizar de forma independiente entre sí.
- La resistencia y la elasticidad se pueden ajustar a las demandas de los servicios individuales.
- El desarrollo puede realizarse en paralelo en diferentes equipos y plataformas.
- Es más fácil escribir pruebas exhaustivas para servicios aislados.

Los microservicios tienen sus propios desafíos, entre ellos:

- Determinar qué servicios hay disponibles y cómo llamarlos.
- Administrar el ciclo de vida de los servicios.
- Comprender cómo encajan los servicios en la aplicación global.
- Probar en todo el sistema las llamadas realizadas a los distintos servicios.

En última instancia, hay soluciones que abordan todos estos desafíos y que permiten aprovechar las ventajas del modelo sin servidor que se describen más adelante.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](architecture-deployment-approaches.md)
