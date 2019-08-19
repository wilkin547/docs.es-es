---
title: Razones para modernizar las aplicaciones .NET existentes en aplicaciones optimizadas para la nube
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Razones para modernizar las aplicaciones .NET existentes en aplicaciones optimizadas para la nube
ms.date: 04/28/2018
ms.openlocfilehash: 5aa9828f65f76138461c18711fe03bdbe6a70ffd
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578128"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Razones para modernizar las aplicaciones .NET existentes en aplicaciones optimizadas para la nube

Con una aplicación optimizada para la nube, puede ofrecer aplicaciones confiables de forma rápida y repetida a sus clientes. Obtiene una agilidad y confiabilidad esenciales al aplazar gran parte de la complejidad operativa de la aplicación a la plataforma.

Si no puede hacer que las aplicaciones se comercialicen rápidamente, en el momento en que envía la aplicación, el mercado al que estaba dirigido habrá evolucionado. Es posible que sea demasiado tarde, independientemente de lo bien que la aplicación se diseñó o se diseñó. Es posible que se produzca un error o que no alcance todo el potencial porque no se puede sincronizar la entrega de aplicaciones con las necesidades del mercado.

La necesidad de una innovación empresarial continua inserciones a los equipos de desarrollo y operaciones en el límite. La única manera de lograr la agilidad que necesita en la innovación empresarial continua es modernizar sus aplicaciones con tecnologías como contenedores y principios específicos de la aplicación optimizada para la nube.

La línea inferior es que cuando una organización crea y administra aplicaciones que están optimizadas para la nube, puede poner en marcha soluciones en manos de clientes y aportar nuevas ideas al mercado cuando sean relevantes.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principios y principios de las aplicaciones optimizadas para la nube 

Las mejoras en la nube se centran principalmente en cumplir dos objetivos: Reduzca los costos y mejore el crecimiento empresarial mejorando la agilidad. Estos objetivos se logran simplificando los procesos y reduciendo la fricción al lanzar y enviar aplicaciones.

La aplicación está optimizada para la nube si puede, de forma ágil, desarrollar la aplicación de forma autónoma desde otras aplicaciones locales y, a continuación, publicar, implementar, escalar automáticamente, supervisar y solucionar problemas de la aplicación en la nube.

La clave es *agilidad*. No se puede distribuir con agilidad a menos que se reduzca a un mínimo absoluto de problemas de implementación a producción y de entorno de desarrollo y pruebas. Los contenedores (específicamente, Docker, como estándar de hecho) y los servicios administrados se diseñaron específicamente para este fin.

Para lograr una agilidad, también necesita procesos de DevOps automatizados que se basan en canalizaciones de CI/CD que se publican en plataformas escalables en la nube. Las plataformas de CI/CD (como Azure DevOps Services o Jenkins) que se implementan en una plataforma en la nube escalable y resistente (como Azure App Service o Azure Kubernetes Service) son tecnologías clave para lograr agilidad en la nube.

En la lista siguiente se describen los principios principales o las prácticas recomendadas para las aplicaciones optimizadas para la nube. Tenga en cuenta que puede adoptar todos o solo algunos de estos principios, en un enfoque progresivo o incremental:

- **Contenedores**. Los contenedores le ofrecen la posibilidad de incluir dependencias de aplicaciones con la propia aplicación. La inclusión en contenedores reduce significativamente el número de problemas que pueden surgir al implementar en entornos de producción o realizar pruebas en entornos de ensayo. En última instancia, los contenedores mejoran la agilidad de la entrega de aplicaciones.

- **Nube resistente y escalable**. La nube proporciona una plataforma que es administrada, elástica, escalable y resistente. Estas características son fundamentales para obtener mejoras de costos y enviar aplicaciones de alta disponibilidad y confiable en una entrega continua. Los servicios administrados como bases de datos administradas, caché administrada como servicio (CaaS) y almacenamiento administrado son piezas fundamentales para aliviar los costos de mantenimiento de la aplicación.

- **Supervisión**. No se puede tener una aplicación confiable sin tener una buena manera de detectar y diagnosticar excepciones y problemas de rendimiento de las aplicaciones. Debe obtener información útil a través de la administración del rendimiento de las aplicaciones y el análisis instantáneo.

- **Referencia cultural de DevOps y entrega continua**. La adopción de prácticas DevOps requiere un cambio cultural en el que los equipos ya no trabajan en silos independientes. Las canalizaciones de CI/CD solo son posibles cuando hay una mayor colaboración entre los equipos de operaciones de desarrollo y de ti, que admiten los contenedores y las herramientas de CI/CD.

En la figura 4-2 se muestran los pilares opcionales principales de una aplicación optimizada para la nube. Cuanto mayor sea el número de pilares que implemente, readier su aplicación será correcta para satisfacer las expectativas de sus clientes.

> ![Principales pilares de una aplicación optimizada para la nube](./media/image2.png)
>
> **Figura 4-2.** Principales pilares de una aplicación optimizada para la nube

En Resumen, una aplicación optimizada para la nube es un enfoque para crear y administrar aplicaciones que aprovechan el modelo de informática en la nube, al tiempo que se usa una combinación de contenedores, una infraestructura en la nube administrada, técnicas de aplicación resistentes. supervisión, entrega continua y DevOps, todo sin necesidad de rediseñar y recodificar las aplicaciones existentes.

Su organización puede adoptar estas tecnologías y enfoques gradualmente. No es necesario que adopte todos ellos a la vez. Puede adoptarlos de forma incremental, en función de las prioridades de la empresa y de las necesidades de los usuarios.

## <a name="benefits-of-a-cloud-optimized-application"></a>Ventajas de una aplicación optimizada para la nube

Puede obtener las siguientes ventajas si convierte una aplicación existente en una aplicación optimizada para la nube (sin rediseñar o codificar):

- **Menores costos, ya que la infraestructura administrada se controla mediante el proveedor**de la nube. Las aplicaciones optimizadas para la nube obtienen las ventajas de la nube con la elasticidad de la nube, el escalado automático y la alta disponibilidad de la nube. Las ventajas están relacionadas no solo con las características de proceso (máquinas virtuales y contenedores), sino que también dependen de los recursos de la nube, como DBaaS, CaaS y cualquier infraestructura que una aplicación pueda necesitar.

- **Infraestructura y aplicación resistentes**. Al migrar a la nube, debe adoptar errores transitorios. se producirán errores en la nube. Además, el hardware y la infraestructura de la nube son "reemplazables", lo que aumenta las oportunidades de tiempo de inactividad transitorio. Al mismo tiempo, las capacidades internas de la nube y ciertas técnicas de desarrollo de aplicaciones que implementan resistencia y automatizan la recuperación facilitan la recuperación de errores inesperados en la nube.

- **Información más detallada**sobre el rendimiento de las aplicaciones. Las herramientas de supervisión en la nube como Aplicación de Azure Insights proporcionan visualización para la administración del estado, el registro y las notificaciones. Los registros de auditoría facilitan la depuración y la auditoría de aplicaciones, fundamental para una aplicación en la nube confiable.

- **Portabilidad de aplicaciones, con implementaciones ágiles**. Los contenedores (ya sean de Linux o de Windows basados en el motor de Docker) ofrecen la mejor solución para evitar una aplicación bloqueada en la nube. Mediante el uso de contenedores, hosts de Docker y orquestadores multinube, puede cambiar fácilmente de un entorno o de una nube a otra. Los contenedores eliminan la fricción que suele producirse en las implementaciones en cualquier entorno (fase, prueba y producción).

En última instancia, todas estas ventajas proporcionan reducciones de costos clave para el ciclo de vida de la aplicación de un extremo a otro.

En las siguientes secciones, estas ventajas se explican con más detalle y están vinculadas a tecnologías específicas.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](microsoft-technologies-in-cloud-optimized-applications.md)
