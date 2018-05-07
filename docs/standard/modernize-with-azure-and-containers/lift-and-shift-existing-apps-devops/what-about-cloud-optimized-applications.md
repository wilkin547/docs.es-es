---
title: ¿Qué aplicaciones optimizada para la nube?
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | ¿Qué aplicaciones optimizada para la nube?
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: dd8d16c534afed6a6dac5dfd8d902a3742883571
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="what-about-cloud-optimized-applications"></a>¿Qué aplicaciones optimizada para la nube?

Aunque optimizada para la nube y [nativo en la nube](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) aplicaciones no son el objetivo principal de esta guía, resulta útil para obtener una descripción de este nivel de madurez modernización y distinguirlo de DevOps preparada para la nube.

Figura 4-3 coloca aplicaciones optimizada para la nube en los niveles de madurez de modernización de aplicación:

![Posición de las aplicaciones optimizada para la nube](./media/image3.png)

> **Figura 4-3.** Posición de las aplicaciones optimizada para la nube

El nivel de madurez Modernización optimizada para la nube normalmente requiere nuevas inversiones de desarrollo. Mover al nivel optimizada para la nube normalmente está controlada por la necesidad empresarial de modernizar las aplicaciones tanto como sea posibles reducir los costos y aumentar la agilidad y compite ventaja. Estos objetivos se llevan a cabo al maximizar el uso de la nube PaaS. Esto significa que no sólo mediante los servicios de PaaS como DBaaS, CaaS y almacenamiento como un servicio (STaaS), sino también mediante la migración de sus propias aplicaciones y servicios a un PaaS compute plataforma como servicio de aplicaciones de Azure o con orchestrators.

Este tipo de modernización normalmente requiere refactorización o escribir código nuevo que está optimizado para plataformas de PaaS (tipo de servicio de aplicaciones de Azure) en la nube. Incluso pueden requerir arquitectura específicamente para el entorno de nube, especialmente si va a mover a los modelos de aplicación de nube nativo que se basan en microservicios. Se trata de una clave en comparación con DevOps preparada para la nube, lo que no requiere volver a diseñar y ningún código nuevo el factor diferenciador.

En algunos casos más avanzados, puede crear [nativo en la nube](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) aplicaciones basadas en arquitecturas de microservicios, que pueden evolucionar con agilidad y escalar a los límites que serían difíciles de lograr en una arquitectura monolítica implementar en un entorno local.

Figura 4-4 muestra el tipo de aplicaciones que se pueden implementar cuando se usa el modelo optimizada para la nube. Tiene dos aplicaciones web moderna opciones básico y las aplicaciones de nube nativo.

> ![Tipos de aplicación en el nivel optimizada para la nube](./media/image4.png)
>
> **Figura 4-4.** Tipos de aplicación en el nivel optimizada para la nube

Puede ampliar aplicaciones web modernos básica y las aplicaciones de nube nativo mediante la adición de otros servicios, como inteligencia artificial (AI), el aprendizaje automático (ML) e IoT. Puede usar cualquiera de estos servicios para extender cualquiera de los posibles enfoques optimizada para la nube.

La diferencia fundamental en las aplicaciones en el nivel de optimizada para la nube está en la arquitectura de la aplicación. [En la nube nativo](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) aplicaciones son, por definición, las aplicaciones que se basan en microservicios. Las aplicaciones de nube nativo requieren arquitecturas especial, las tecnologías y plataformas, en comparación con una aplicación web monolítico o aplicación tradicional de N niveles.

También se cree nuevas aplicaciones que no usan microservicios tiene sentido. Hay muchos escenarios nuevo y modernos todavía en el que un enfoque basado en microservicios puede superar sus necesidades. En algunos casos, podría simplemente desea crear una aplicación web monolítico más simple, o agregar servicios de grano grueso a una aplicación con N niveles. En estos casos, todavía puede realizar un uso completo de la nube PaaS capacidades como las que se ofrece el servicio de aplicación de Azure. Todavía se reduce el trabajo de mantenimiento para el límite.

Además, dado que se desarrolla nuevo código en escenarios de optimizada para la nube (para una aplicación completa o parciales subsistemas), cuando se crea el nuevo código, debe usar las versiones más recientes de .NET ([.NET Core](../../../core/index.md) y [ASP.NET Core](/aspnet/core/), en particular). Esto es especialmente cierto si crea microservicios y contenedores como núcleo de .NET es un marco rápido y eficiente. Obtendrá una pequeña superficie de memoria y el inicio rápido de contenedores y las aplicaciones será de alto rendimiento. Este enfoque se adapta a perfectamente con los requisitos de microservicios y contenedores, y obtendrá las ventajas de un multiplataforma framework-teniendo la posibilidad de ejecutar la misma aplicación en Linux, Windows Server y Mac (Mac para los entornos de desarrollo).

## <a name="cloud-native-applications-with-cloud-optimized-applications"></a>Aplicaciones de nube nativo con aplicaciones optimizada para la nube

[En la nube nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) es un estado más avanzado o consolidado para aplicaciones de gran tamaño y de misión crítica. Las aplicaciones de nube nativo suelen requieran la arquitectura y el diseño que se crean desde el principio en lugar de por modernizar las aplicaciones existentes. La diferencia clave entre una aplicación nativa en la nube y una aplicación web optimizada para la nube más sencilla implementada en PaaS es la recomendación para usar microservicios arquitecturas en un enfoque de nativo en la nube. También pueden ser aplicaciones optimizada para la nube aplicaciones web monolítico o las aplicaciones con N niveles implementado en una nube PaaS servicio como servicio de aplicaciones de Azure.

El [aplicación de Factor de doce](https://12factor.net/) (una colección de modelos que están estrechamente relacionados a los enfoques microservicios) también se considera un requisito para [nativo en la nube](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) arquitecturas de aplicación.

El [Foundation de informática nativo de nube (CNCF)](https://www.cncf.io/) está activa un promotor principal de principios de nativo en la nube. Microsoft es un [miembro de la CNCF](https://azure.microsoft.com/blog/announcing-cncf/).

Para obtener una definición de ejemplo y para obtener más información acerca de las características de aplicaciones de nube nativo, vea el artículo de Gartner [cómo diseñar la arquitectura y las aplicaciones de nube nativo](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications). Para obtener instrucciones específicas de Microsoft acerca de cómo implementar una aplicación nativa en la nube, consulte [microservicios. NET: arquitectura de aplicaciones .NET en contenedores](https://aka.ms/microservicesebook).

El factor más importante a tener en cuenta si migra una aplicación completa para el [nativo en la nube](https://www.gartner.com/doc/3738117/comparing-leading-cloudnative-application-platforms) modelo es que debe volver a diseñar para una arquitectura basada en microservicios. Claramente Esto requiere una inversión importante en el desarrollo como consecuencia del proceso de refactorización grande implicado. Normalmente, se elige esta opción para aplicaciones de misión crítica que necesitan nuevos niveles de escalabilidad y la agilidad a largo plazo. Pero, puede comenzar a mover hacia la nube nativo mediante la adición de microservicios para unos pocos escenarios nuevos y finalmente refactorizar la aplicación completamente como microservicios. Se trata de un enfoque incremental que es la mejor opción para algunos escenarios.

## <a name="what-about-microservices"></a>¿Qué ocurre con microservicios? 

Cuando está pensando en las aplicaciones de nube nativo para su organización, es importante entender microservicios y cómo funcionan.

La arquitectura de microservicios es un enfoque avanzado que puede usar para las aplicaciones que se crean desde el principio o al desarrollar las aplicaciones existentes (locales o aplicaciones compatibles con DevOps en la nube) hacia las aplicaciones de nube nativo. Puede empezar agregando unos microservicios en las aplicaciones existentes para obtener información sobre los nuevos paradigmas de microservicios. Pero claramente, necesitará arquitecto y el código, especialmente para este tipo de enfoque de arquitectura.

Sin embargo, no son obligatorios para cualquier aplicación nueva o moderna microservicios. Microservicios no son "mágica", y no son la forma única y recomendada para crear todas las aplicaciones. Cómo y cuándo usar microservicios depende del tipo de aplicación que necesita para compilar.

La arquitectura de microservicios se está convirtiendo en el método preferido para aplicaciones de misión crítica distribuidas y grandes o complejas que se basan en varios subsistemas independientes en forma de servicios autónomos. En una arquitectura basada en microservicios, una aplicación se compila como una colección de servicios que pueden ser independientemente desarrollado, probado, control de versiones, implementar y escalar. Esto puede incluir cualquier base de datos relacionada, autónomo por microservicio.

Para obtener una visión detallada de una arquitectura de microservicios se puede implementar mediante .NET Core, vea el PDF libro electrónico descargable [microservicios. NET: arquitectura de aplicaciones .NET en contenedores](https://aka.ms/microservicesebook). La guía también está disponible [en línea](../../microservices-architecture/index.md).

Pero incluso en escenarios en que microservicios ofrecen eficaz de independiente de las capacidades de implementación y los límites de subsistema seguro, diversidad de tecnología-también activan muchos desafíos nuevos. Los desafíos relacionados con el desarrollo de aplicaciones distribuidas, como los modelos de datos fragmentados y es independiente; para lograr una comunicación resistente entre microservicios; la necesidad de coherencia definitiva; y la complejidad operativa. Microservicios presentan un mayor nivel de complejidad en comparación con las aplicaciones tradicionales monolíticas.

Dada la complejidad de una arquitectura de microservicios, sólo ciertos tipos de aplicaciones y escenarios específicos son adecuados para aplicaciones basadas en microservicio. Estas soluciones incluyen aplicaciones grandes y complejas que tienen varios evolucionando subsistemas. En estos casos, merece la pena invertir en una arquitectura de software más compleja, para una mayor agilidad a largo plazo y el mantenimiento de aplicación más eficaz. Pero para escenarios menos complejos, podría ser mejor continuar con un enfoque de aplicación monolítico o acerca de N niveles más sencilla.

Como una nota final, incluso con el riesgo de que es repetitivos sobre este concepto, no debe intentar usar microservicios en las aplicaciones como "todo o nada en absoluto *.*" Puede extender y desarrollar aplicaciones monolíticas existentes agregando nuevos, pequeños escenarios basados en microservicios. No es necesario empezar desde cero para empezar a trabajar con un enfoque de arquitectura de microservicios. De hecho, se recomienda que los evolucionar del uso de una aplicación existente de monolítica o N niveles mediante la adición de nuevos escenarios. Finalmente, puede dividir la aplicación en componentes autónomos o microservicios. Puede iniciar la evolución de las aplicaciones monolíticas en una dirección de microservicios, paso a paso.

## <a name="when-to-use-azure-app-service-for-modernizing-existing-net-apps"></a>Cuándo se debe utilizar el servicio de aplicaciones de Azure para modernizar las aplicaciones .NET existentes

Cuando se modernizar las aplicaciones web ASP.NET existentes en el nivel de madurez optimizada para la nube, como las aplicaciones web se desarrollaron con .NET Framework, las dependencias de sus principales están en Windows y, probablemente, Internet Information Server (IIS). Puede usar e implementar aplicaciones basadas en Windows y basadas en IIS ya sea mediante la implementación directamente en [servicio de aplicaciones de Azure](https://docs.microsoft.com/azure/app-service/app-service-value-prop-what-is) o por primera containerizing la aplicación mediante el uso de contenedores de Windows. Si containerizing, implemente las aplicaciones o a contenedores de Windows hospeda (basado en máquina virtual) o a un servicio de Azure Fabric clúster compatible con contenedores de Windows.

Al utilizar los contenedores de Windows, obtendrá todas las ventajas de inclusión en contenedores. Aumentar la agilidad de envío e implementar su aplicación y reducir la fricción para problemas del entorno (almacenamiento provisional, desarrollo y pruebas, producción). En las siguientes secciones, se pasa a información más detallada sobre las ventajas que obtendrá de uso de contenedores.

Al redactar de esta guía, servicio de aplicaciones de Azure no admite contenedores de Windows. Admite contenedores para Linux. Por lo tanto, podría ser la siguiente pregunta, "¿Cómo elijo entre los contenedores de Windows y el servicio de aplicaciones de Azure?"

Básicamente, si el servicio de aplicación de Azure funciona para su aplicación y no hay cualquier servidor o dependencias personalizadas bloqueando la ruta de acceso para usar el servicio de aplicaciones, debe migrar la aplicación web existente de .NET para el servicio de aplicaciones. Que es la manera más fácil y más eficaz para mantener la aplicación. En Azure, la aplicación también tendrá una ruta de acceso de mantenimiento más sencillo debido a las ventajas de la infraestructura de PaaS, como DBaaS, CaaS y STaaS.

Sin embargo, si la aplicación tiene servidor ni dependencias personalizadas que no son compatibles con el servicio de aplicaciones de Azure, tendrá que tener en cuenta las opciones que se basan en los contenedores de Windows. Ejemplos de servidor o dependencias personalizadas incluyen software de terceros o un archivo .msi que debe instalarse en el servidor, pero que no se admite en el servicio de aplicación de Azure. Otro ejemplo es cualquier otra configuración de servidor que no es compatible con el servicio de aplicación de Azure, como el uso de ensamblados en la caché de ensamblados Global (GAC) o COM / componentes COM +. Gracias a las imágenes de contenedor de Windows, puede incluir las dependencias personalizadas en la misma "unidad de implementación."

Como alternativa, puede refactorizar las áreas de la aplicación que no son compatibles con el servicio de aplicaciones de Azure. Según el volumen de trabajo refactorización requerirían, tendría que evalúe cuidadosamente si merece la pena hacerlo.

### <a name="benefits-of-moving-to-azure-app-service"></a>Ventajas de pasar a servicio de aplicaciones de Azure

Servicio de aplicaciones de Azure es una PaaS completamente administrado de la oferta que facilita el proceso compilar aplicaciones web que se basan en los procesos empresariales. Cuando se usa el servicio de aplicaciones, evite los costos de administración de infraestructura asociados a la actualización y mantenimiento de aplicaciones web en local. En concreto, se recorta el hardware y los costos de licencia de la ejecución de aplicaciones web en local.

Si la aplicación web es adecuada para migrar al servicio de aplicaciones de Azure, la principal ventaja es la cantidad de tiempo necesario para mover la aplicación corta. Servicio de aplicaciones ofrece un entorno muy sencillo en el que se va a empezar a trabajar.

Servicio de aplicaciones de Azure es la mejor opción para la mayoría de las aplicaciones web porque es la más sencilla PaaS en Azure que puede usar para ejecutar las aplicaciones web. Implementación y administración se integran en la plataforma, sitios rápidamente escalan para controlar grandes cargas de tráfico y el Administrador de tráfico y equilibrio de carga integrados proporcionan alta disponibilidad.

Incluso las aplicaciones web de supervisión es sencillo, a través de la visión de la aplicación de Azure. Application Insights incluye gratis con el servicio de aplicaciones y no necesitan escribir ningún código especial en la aplicación. Simplemente ejecutar la aplicación web en el servicio de aplicaciones, y obtendrá un sistema de supervisión atractivo, sin ningún trabajo adicional.

Con el servicio de aplicación, puede usar muchas aplicaciones de código abierto directamente desde la Galería de aplicaciones Web de Azure (por ejemplo, WordPress o Umbraco) o puede crear un nuevo sitio mediante el marco y las herramientas de generación de su elección, como ASP.NET. La característica de trabajos Web del servicio de aplicación facilita el Agregar trabajo en segundo plano de procesamiento a la aplicación de servicio de aplicaciones web.

Las principales ventajas de migrar las aplicaciones web mediante la característica de las aplicaciones Web de servicio de aplicaciones de Azure incluyen lo siguiente:

-   El escalado automático para satisfacer la demanda durante horas de disponibilidad y reducir los costes durante intervalos de silencio.

-   Copias de seguridad de sitio automática para proteger los cambios y los datos.

-   Alta disponibilidad y resistencia en la plataforma de PaaS de Azure.

-   Ranuras de implementación para el desarrollo y entornos de ensayo y para probar varios diseños de sitios.

-   Equilibrio de carga y la protección de denegación de servicio (DDoS) distribuido.

-   Administración del tráfico para dirigir a los usuarios a la implementación geográfica más cercana.

Aunque el servicio de aplicaciones puede ser la mejor opción para las nuevas aplicaciones web, sin embargo, para las aplicaciones existentes, servicio de aplicaciones sería la mejor opción solo si se admiten las dependencias de aplicación de servicio de aplicaciones.

### <a name="additional-resources"></a>Recursos adicionales

-   **Análisis de compatibilidad para el servicio de aplicaciones de Azure**  
[https://www.migratetoazure.net/Resources](https://www.migratetoazure.net/Resources)


### <a name="benefits-of-moving-to-windows-containers"></a>Ventajas de pasar a los contenedores de Windows

La principal ventaja de utilizar contenedores de Windows es que tener una experiencia de implementación más confiable y mejorado en comparación con las aplicaciones en contenedores no. Además, hacer que su aplicación y modernizada con contenedores de forma eficaz, la aplicación lista para muchas otras plataformas y las nubes que admiten contenedores de Windows. Las ventajas de pasar a los contenedores de Windows se tratan con más detalle en las secciones siguientes.

Los entornos de proceso principal en Azure (en disponibilidad general, a partir de mediados de 2017) que admiten los contenedores de Windows son Azure Service Fabric y hosts básicos de contenedores de Windows (máquinas virtuales Windows Server 2016). Estos entornos son los escenarios de infraestructura principal que se tratan en esta guía.

También puede implementar contenedores de Windows en otros orchestrators, como Kubernetes, Docker Swarm o DC/OS. Actualmente (pronto se encuentran 2017), estas plataformas se encuentran en vista previa en el servicio de contenedor de Azure para el uso de contenedores de Windows.

>[!div class="step-by-step"]
[Anterior](microsoft-technologies-in-cloud-devops-ready-applications.md)
[Siguiente](how-to-deploy-existing-net-apps-to-azure-app-service.md)
