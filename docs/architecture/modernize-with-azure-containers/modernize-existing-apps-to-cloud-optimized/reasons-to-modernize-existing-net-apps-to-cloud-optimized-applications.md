---
title: Razones para modernizar las aplicaciones .NET existentes a aplicaciones optimizadas para la nube
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Razones para modernizar las aplicaciones .NET existentes a aplicaciones optimizadas para la nube
ms.date: 12/21/2020
ms.openlocfilehash: e9b3ad151cf0591783ada8a1ab87cb0f14423a7e
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025217"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Razones para modernizar las aplicaciones .NET existentes a aplicaciones optimizadas para la nube

Con una aplicación optimizada para la nube, puede ofrecer aplicaciones confiables de forma rápida y sostenida a sus clientes. Obtiene una agilidad y confiabilidad esenciales porque traslada gran parte de la complejidad operativa de la aplicación a la plataforma.

Si no lanza sus aplicaciones rápidamente al mercado, para el momento en que distribuya su aplicación, el mercado al que estaba dirigida habrá evolucionado. Es posible que sea demasiado tarde, independientemente de lo bien que haya diseñado la aplicación. Es posible que no alcance todo su potencial porque no logra sincronizar la entrega de aplicaciones con las necesidades del mercado.

La necesidad de una innovación empresarial continua empuja a los equipos de desarrollo y operaciones al límite. La única manera de lograr la agilidad que necesita en la innovación empresarial continua es modernizar sus aplicaciones con tecnologías como contenedores y los principios específicos de las aplicaciones optimizadas para la nube.

La idea básica es que, cuando una organización crea y administra aplicaciones que están optimizadas para la nube, puede poner las soluciones en manos de los clientes mucho antes y aportar nuevas ideas al mercado cuando sean pertinentes.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principios de las aplicaciones optimizadas para la nube

Las mejoras en la nube se centran principalmente en cumplir dos objetivos: Aumentar la agilidad para reducir los costos y mejorar el crecimiento empresarial. Para lograr estos objetivos, hay que simplificar los procesos y reducir la fricción en el lanzamiento y la distribución de aplicaciones.

Una aplicación está optimizada para la nube si puede desarrollar la aplicación de forma autónoma y ágil a partir de otras aplicaciones locales y, luego, publicar, implementar, escalar automáticamente y supervisar la aplicación en la nube, así como solucionar problemas.

La clave es la *agilidad*. No se puede distribuir con agilidad a menos que reduzca al mínimo los problemas de implementación en producción y los problemas en el entorno de desarrollo y pruebas. Los contenedores (especialmente Docker como estándar de hecho) y los servicios administrados se diseñaron específicamente para este fin.

Para lograr agilidad, también necesita procesos de DevOps automatizados basados en canalizaciones de CI/CD que publiquen las versiones en plataformas escalables en la nube. Las plataformas de CI/CD (como Azure DevOps Services o Jenkins) que realizan la implementación en una plataforma de nube escalable y resistente (como Azure App Service o Azure Kubernetes Service) son tecnologías clave para lograr agilidad en la nube.

En la lista siguiente se describen los principios o procedimientos principales para las aplicaciones optimizadas para la nube. Tenga en cuenta que puede adoptar todos o solo algunos de estos principios, en un enfoque progresivo o incremental:

- **Contenedores**. los contenedores ofrecen la posibilidad de incluir dependencias de aplicaciones en la propia aplicación. La inclusión en contenedores reduce significativamente el número de problemas que pueden surgir al implementar en entornos de producción o realizar pruebas en entornos de ensayo. En última instancia, los contenedores mejoran la agilidad de la entrega de aplicaciones.

- **Nube resistente y escalable**. la nube proporciona una plataforma administrada, elástica, escalable y resistente. Estas características son fundamentales para obtener mejoras de los costos y enviar aplicaciones de alta disponibilidad y confiables en una entrega continua. Los servicios administrados, como las bases de datos administradas, la memoria caché administrada como servicio (CaaS) y el almacenamiento administrado, son piezas fundamentales para reducir los costos de mantenimiento de la aplicación.

- **Supervisión**. no se puede tener una aplicación confiable sin tener una buena manera de detectar y diagnosticar excepciones y problemas de rendimiento de las aplicaciones. Debe obtener información útil mediante la administración del rendimiento de las aplicaciones y el análisis instantáneo.

- **Cultura de DevOps y entrega continua**. la adopción de procedimientos de DevOps requiere un cambio cultural porque los equipos ya no trabajarán en silos independientes. Las canalizaciones de CI/CD solo son posibles cuando hay una mayor colaboración entre los equipos de operaciones de desarrollo y de TI, que admiten los contenedores y las herramientas de CI/CD.

En la figura 4-2 se muestran los principales pilares opcionales de una aplicación optimizada para la nube. Cuanto mayor sea el número de pilares que implemente, más preparada estará su aplicación para satisfacer las expectativas de sus clientes.

![Diagrama que nombra los pilares principales de una aplicación optimizada para la nube.](./media/main-pillars-cloud-optimized-application.png)

**Figura 4-2.** Principales pilares de una aplicación optimizada para la nube

En resumen, una aplicación optimizada para la nube es un enfoque para crear y administrar aplicaciones que aprovechan el modelo de informática en la nube y que usa una combinación de contenedores, infraestructura en la nube administrada, técnicas de aplicación resistentes. supervisión, entrega continua y DevOps, todo ello sin necesidad de rediseñar y recodificar las aplicaciones existentes.

Su organización puede adoptar estas tecnologías y enfoques gradualmente. No es necesario que adopte todos ellos a la vez. Puede adoptarlos de forma incremental, en función de las prioridades de la empresa y de las necesidades de los usuarios.

## <a name="benefits-of-a-cloud-optimized-application"></a>Ventajas de una aplicación optimizada para la nube

Puede obtener las siguientes ventajas si convierte una aplicación existente en una aplicación optimizada para la nube (sin rediseñar ni codificar):

- **Menores costos, porque es el proveedor de nube quien controla la infraestructura administrada**. Las aplicaciones optimizadas para la nube disfrutan de las ventajas de la nube: elasticidad, el escalado automático y alta disponibilidad. Las ventajas están relacionadas no solo con las características de proceso (máquinas virtuales y contenedores), sino que también dependen de los recursos de la nube, como DBaaS, CaaS y cualquier infraestructura que una aplicación pueda necesitar.

- **Aplicación resistente e infraestructura**. Al migrar a la nube, debe poder admitir errores transitorios; se producirán errores en la nube. Además, el hardware y la infraestructura de la nube son "reemplazables", lo que aumenta las probabilidades de sufrir tiempos de inactividad transitorios. Al mismo tiempo, las funcionalidades internas de la nube y ciertas técnicas de desarrollo de aplicaciones que implementan resistencia y automatizan la recuperación facilitan la recuperación de errores inesperados en la nube.

- **Información más detallada sobre el rendimiento de las aplicaciones**. Las herramientas de supervisión en la nube, como Azure Application Insights, permiten ver la administración del estado, los registros y las notificaciones. Los registros de auditoría facilitan la depuración y la auditoría de las aplicaciones, lo que resulta fundamental para una aplicación en la nube confiable.

- **Portabilidad de aplicaciones, con implementaciones ágiles**. Los contenedores (ya sean Linux o Windows basados en el motor de Docker) ofrecen la mejor solución para evitar el bloqueo de una aplicación en la nube. Mediante el uso de contenedores, hosts de Docker y orquestadores multinube, puede cambiar fácilmente de un entorno o de una nube a otra. Los contenedores eliminan la fricción que suele producirse en las implementaciones en cualquier entorno (ensayo, prueba y producción).

En última instancia, todas estas ventajas proporcionan reducciones de costos clave para el ciclo de vida de la aplicación de un extremo a otro.

En las siguientes secciones, se explican estas ventajas con más detalle y se vinculan con tecnologías específicas.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](microsoft-technologies-in-cloud-optimized-applications.md)
