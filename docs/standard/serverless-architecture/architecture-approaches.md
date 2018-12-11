---
title: Enfoques de arquitectura - aplicaciones sin servidor
description: Una introducción a la arquitectura de enfoques para crear aplicaciones empresariales basadas en la nube, de las arquitecturas de N niveles a sin servidor.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 04ad383586f974bb2dccc4623a9a254f5668dab4
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126750"
---
# <a name="architecture-approaches"></a>Enfoques de arquitectura

Descripción de los enfoques existentes para diseñar aplicaciones empresariales Ayuda a aclarar la función desempeñada por sin servidor. Hay muchos enfoques y patrones que ha evolucionaron a lo largo de décadas de desarrollo de software, y todas tienen sus propias ventajas y desventajas. En muchos casos, la solución final puede implicar la decidir un enfoque único, pero puede integrar varios enfoques. Escenarios de migración suelen implican el cambio de enfoque de arquitectura de uno a otro a través de un enfoque híbrido.

Este capítulo proporciona información general de ambos patrones de arquitectura lógica y física para aplicaciones empresariales.

## <a name="architecture-patterns"></a>Patrones de arquitectura

Las aplicaciones empresariales modernas siguen una variedad de patrones de arquitectura. En esta sección representa una encuesta de patrones comunes. Los patrones que se muestran aquí no son necesariamente todas las prácticas recomendadas, pero muestran los distintos enfoques.

Para obtener más información, consulte [Guía de arquitectura de aplicación de Azure](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Monolitos

Muchas aplicaciones empresariales siguen un patrón de monolito. Las aplicaciones heredadas a menudo se implementan como monolitos. En el patrón monolítico, todos los problemas de la aplicación se encuentran en una sola implementación. Todo, desde la interfaz de usuario para las llamadas de base de datos se incluye en el mismo código base.

![Arquitectura de un monolito](./media/monolith-architecture.png)

Hay varias ventajas del enfoque monolítico. A menudo es fácil extraer un único código base y empezar a trabajar. Tiempo de inicialización puede ser menor y creación de entornos de prueba es tan sencilla como proporcionar una nueva copia. El monolito puede diseñarse para incluir varios componentes y aplicaciones.

Lamentablemente, el patrón de monolito tiende a desglosar a escala. Las desventajas importantes del enfoque monolítico incluyen:

* Difícil trabajar en paralelo en el mismo código base.
* Cualquier cambio, con independencia de cómo trivial, requiere la implementación de una nueva versión de toda la aplicación.
* Refactorización potencialmente afecta a toda la aplicación.
* A menudo es la única solución a escalar crear varias copias de la gran cantidad de recursos de monolito.
* Expanda los sistemas o se adquieren a otros sistemas, integración puede ser difícil.
* Puede ser difícil de probar debido a la necesidad de configurar el monolito todo.
* Reutilización del código es un desafío y a menudo otras aplicaciones acaban tener sus propias copias del código.

Muchas empresas recurren a la nube como una oportunidad para migrar aplicaciones de un monolito y al mismo tiempo los refactorizar más patrones utilizable. Es habitual para desglosar los componentes y aplicaciones individuales para que puedan ser mantiene, implementan y escalan por separado.

## <a name="n-layer-applications"></a>Aplicaciones de N capas

Lógica de aplicación de partición de aplicación de N capas en niveles específicos. Las capas más comunes incluyen:

* Interfaz de usuario
* lógica de negocios
* Acceso a datos

Pueden incluir otras capas middleware, procesamiento por lotes y API. Es importante tener en cuenta que las capas son lógicas. Aunque se desarrollan en aislamiento, todo se puede implementar en la misma plataforma de destino.

![Arquitectura de N capas](./media/n-layer-architecture.png)

Hay varias ventajas del enfoque de N capas, incluidas:

* Refactorización está aislada en una capa.
* Por separado los equipos pueden crear, probar, implementar y mantener capas separadas.
* Se pueden intercambiar las capas, por ejemplo la capa de datos puede tener acceso a varias bases de datos sin necesidad de realizar cambios a la capa de interfaz de usuario.

Sin servidor puede utilizarse para implementar una o varias capas.

## <a name="microservices"></a>Microservicios

**[Microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  arquitecturas contienen características comunes que incluyen:

* Las aplicaciones se componen de varios servicios pequeños.
* Cada servicio se ejecuta en su propio proceso.
* Los servicios se alinean en torno a dominios empresariales.
* Los servicios se comunican a través de API ligeras, normalmente mediante HTTP como transporte.
* Los servicios se pueden implementar y actualizar de forma independiente.
* Servicios no son dependientes de un único almacén de datos.
* El sistema está diseñado con un error en la cuenta y la aplicación, puede que siga funcionando incluso cuando determinados servicios producirá un error.

Microservicios no tienen que ser mutuamente excluyentes para otros enfoques de arquitectura. Por ejemplo, una arquitectura de N niveles puede usar microservicios para el nivel intermedio. También es posible implementar microservicios en una variedad de formas, desde los directorios virtuales en hosts IIS para contenedores. Las características de microservicios que sean especialmente ideal para implementaciones sin servidor.

![Arquitectura de microservicios](./media/microservices-architecture.png)

Entre las ventajas de las arquitecturas de microservicios se incluyen:

* Refactorización a menudo se aísla en un único servicio.
* Los servicios se pueden actualizar independientemente entre sí.
* Resistencia y la elasticidad pueden ajustarse a las exigencias de los servicios individuales.
* Desarrollo puede darse en paralelo en las plataformas y los equipos dispares.
* Es más fácil escribir pruebas integrales para servicios aislado.

Microservicios vienen con sus propios desafíos, incluyendo:

* Determinación de qué servicios están disponibles y cómo llamarlos.
* Administrar el ciclo de vida de los servicios.
* Comprender cómo encajan los servicios en la aplicación general.
* Total de pruebas del sistema de las llamadas realizadas a través de diferentes servicios.

En última instancia, hay soluciones para abordar todos estos desafíos, incluido el aprovechamiento de las ventajas de sin servidor que se describen más adelante.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](architecture-deployment-approaches.md)