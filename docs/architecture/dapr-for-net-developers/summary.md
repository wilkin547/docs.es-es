---
title: Resumen y camino a seguir
description: Un resumen de las conclusiones clave de DAPR y una mirada hacia adelante.
ms.date: 02/04/2021
author: robvet
ms.openlocfilehash: c15104f861dd6cfb999d3f67f19b988d1a8ffb03
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401830"
---
# <a name="summary-and-the-road-ahead"></a>Resumen y camino a seguir

Estamos al final de nuestro vuelo DAPR. El plano de jet que vuela a 20.000 metros del [capítulo 2](dapr-at-20000-feet.md) está en el enfoque final y sobre la tierra.

En lo que se refiere al avión a la puerta, dedique un minuto a revisar algunas conclusiones importantes de esta guía:

- **DAPR** -DAPR es un entorno de *tiempo de ejecución de aplicaciones distribuidas* que simplifica la creación de aplicaciones distribuidas. Expone una arquitectura de bloques de creación y componentes conectables. DAPR proporciona un **pegado dinámico** que enlaza la aplicación con funcionalidades de infraestructura que existen en el tiempo de ejecución de DAPR. En lugar de compilar la infraestructura de infraestructura, usted y su equipo se centran en ofrecer características empresariales a los clientes.

- **Código abierto y multiplataforma** : la API DAPR nativa puede ser utilizada por *cualquier plataforma* que admita http o gRPC. DAPR también proporciona SDK específicos del lenguaje para plataformas de desarrollo populares. DAPR v 1.0 admite Go, Python, .NET, Java, PHP y JavaScript.

- **Bloques de creación** : bloques de creación DAPR encapsulan la funcionalidad de la aplicación distribuida. En el momento de redactar este documento, DAPR admite los siete bloques de creación que se muestran en la figura 11-1.

![Bloques de creación de DAPR](./media/dapr-at-20000-feet/building-blocks.png)

**Figura 11-1**. Bloques de creación de DAPR.

- **Componentes** : los componentes de DAPR proporcionan la implementación concreta para cada capacidad de bloque de creación de DAPR. Exponen una interfaz común que permite a los desarrolladores intercambiar implementaciones de componentes sin cambiar el código de la aplicación. En la figura 11-2 se muestra la relación entre los componentes, los bloques de creación y el servicio.

![Integración de DAPR Building Blocks](./media/dapr-at-20000-feet/building-blocks-integration.png)

**Figura 11-2**. DAPR integración de bloques de creación.

- **Sidecars** -DAPR se ejecuta junto con la aplicación en una arquitectura de sidecar, ya sea como un proceso independiente de un contenedor. La aplicación se comunica con las API de DAPR a través de HTTP y gRPC. Los sidecares proporcionan aislamiento y encapsulación, ya que no forman parte del servicio, pero se conectan a él. En la figura 11-3 se muestra una arquitectura sidecar.

![Arquitectura de sidecar](./media/dapr-at-20000-feet/sidecar-generic.png)

**Figura 11-3**. Arquitectura sidecar.

- **Entornos de hospedaje** DAPR tiene compatibilidad multiplataforma y se puede ejecutar en varios entornos. En el momento de redactar este documento, los entornos incluyen un modo autohospedado local y Kubernetes.

- **eShopOnDapr** : este libro incluye una aplicación de referencia adjunta titulada [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr). Mediante un conocido dominio de aplicación de comercio electrónico, la aplicación de referencia muestra el uso de cada bloque de creación. Se trata de una evolución del [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)ampliamente popular, lanzado hace varios años.

## <a name="the-road-ahead"></a>Camino hacia adelante

En adelante, DAPR tiene la posibilidad de tener un impacto profundo en el desarrollo de aplicaciones distribuidas. ¿Qué puede esperar del equipo de DAPR y sus colaboradores de código abierto?

En el momento de escribir este documento, la lista de mejoras propuestas para DAPR incluye:

- Mejoras en las características de los bloques de creación existentes:
  - Capacidades de consulta en la administración de estado que permiten recuperar varios valores.
  - Filtrado de temas en pub/sub que le permite filtrar los temas en función de su contenido.
  - Una API de seguimiento de aplicaciones en observación que proporciona seguimiento en la aplicación directamente sin tener que enlazar a bibliotecas específicas.
  - Compatibilidad con enlaces y pub/sub para actores que proporcionan funcionalidades orientadas a eventos al modelo de programación de actor. Los componentes enlazados desencadenarán eventos y mensajes invocarán métodos en el actor.

- Nuevos bloques de creación:
  - Bloque de creación de API de configuración para leer y escribir datos de configuración. El bloque se enlazará a proveedores que incluyen administración de configuración de Azure Configuration Manager o GCP.
  - Escalado automático de escala a cero de http.
  - Bloque de creación de elección de líder para proporcionar instancias singleton y bloquear las capacidades semánticas.
  - Bloque de creación de proxy transparente para la invocación del servicio, lo que le permite enrutar los mensajes basándose en direcciones URL o direcciones DNS en el nivel de red.
  - Bloque de creación de resistencia (disyuntores, mamparos & tiempos de espera).

- Integración con Marcos y tecnologías nativas en la nube. Estos son algunos ejemplos:
  - Django
  - Nodejs
  - Express
  - Kyma
  - Mitad del intervalo

- Nuevos SDK de lenguaje:
  - JavaScript
  - OXIDA
  - C++

- Nuevas plataformas de hospedaje:
  - Máquinas virtuales
  - Azure IoT Edge
  - Azure Stack Edge
  - Azure Service Fabric

- Herramientas de productividad para desarrolladores y operadores:
  - VS Code extensión.
  - Contenedores de desarrollo remotos para la depuración local de un desarrollo de canalización DevOps.
  - DAPR: mejoras del panel operativo que proporcionarán una mayor visibilidad de los aspectos operativos de la administración de aplicaciones de DAPR.

La versión 1,0 de DAPR proporciona a los desarrolladores un cuadro de herramientas atractivo para la creación de aplicaciones distribuidas. Como se muestra en la lista de mejoras propuestas, DAPR se encuentra en desarrollo activo con muchas nuevas funcionalidades que debe obtener. Manténgase atento al [sitio de DAPR](https://dapr.io/) y al [blog del anuncio de DAPR](https://cloudblogs.microsoft.com/opensource/2019/10/16/announcing-dapr-open-source-project-build-microservice-applications/) para futuras actualizaciones.

>[!div class="step-by-step"]
>[Anterior](secrets.md)
