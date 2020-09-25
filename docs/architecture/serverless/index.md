---
title: 'Aplicaciones sin servidor: Arquitectura, patrones e implementación de Azure'
description: Guía sobre la arquitectura sin servidor. Obtenga información sobre cuándo, cómo y por qué implementar una arquitectura sin servidor (en lugar de una infraestructura como servicio [IaaS] o una plataforma como servicio [PaaS]) para las aplicaciones empresariales.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/22/2020
ms.openlocfilehash: 867765d29a7c50694a5de7b1de56346d86600a83
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171824"
---
# <a name="serverless-apps-architecture-patterns-and-azure-implementation"></a>Aplicaciones sin servidor: Arquitectura, patrones e implementación de Azure

![Captura de pantalla en la que se muestra la portada del libro electrónico Aplicaciones sin servidor.](./media/index/serverless-apps-cover-v3.png)

**EDICIÓN 3.0** — Actualizado a Azure Functions 3

> DESCARGA disponible en: <https://aka.ms/serverlessbookpdf>

PUBLICADO POR

Equipos de producto de la División de desarrolladores de Microsoft, .NET y Visual Studio

División de Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright &copy; 2018-2020 de Microsoft Corporation

Todos los derechos reservados. No se puede reproducir ni transmitir de ninguna forma ni por ningún medio ninguna parte del contenido de este libro sin la autorización por escrito del publicador.

Este libro se proporciona “tal cual” y expresa las opiniones del autor. Las opiniones y la información expresados en este libro, incluidas las direcciones URL y otras referencias a sitios web de Internet, pueden cambiar sin previo aviso.

Algunos ejemplos descritos aquí se proporcionan únicamente con fines ilustrativos y son ficticios. No debe deducirse ninguna asociación ni conexión reales.

Microsoft y las marcas comerciales indicadas en <https://www.microsoft.com> en la página web "Marcas comerciales" pertenecen al grupo de empresas de Microsoft.

Mac y macOS son marcas comerciales de Apple Inc.

El resto de marcas y logotipos pertenece a sus respectivos propietarios.

Autor:

> **[Jeremy Likness](https://twitter.com/jeremylikness)** , director de programas de datos de .NET, Microsoft Corp.

Colaborador:

> **[Cecil Phillip](https://twitter.com/cecilphillip)** , promotor de la nube sénior, Microsoft Corp.

Editores:

> **[Bill Wagner](https://twitter.com/billwagner)** , desarrollador de contenido sénior, Microsoft Corp.

> **[Maira Wenzel](https://twitter.com/mairacw)** , desarrolladora de contenido sénior, Microsoft Corp.

Participantes y revisores:

> **[Steve Smith](https://twitter.com/ardalis)** , propietario, Ardalis Services.

## <a name="introduction"></a>Introducción

La informática [sin servidor](https://azure.microsoft.com/solutions/serverless/) es la evolución de las plataformas de la nube en la línea del código nativo puro de la nube. Además, acerca a los desarrolladores a la lógica de negocios a la vez que los aísla de los problemas de infraestructura. Es un patrón que no implica el uso de "ningún servidor" sino de "menos servidor". El código sin servidor está orientado a eventos. El código se puede desencadenar con solicitudes web HTTP tradicionales, temporizadores o con el resultado de cargar un archivo. La infraestructura que hay detrás de la informática sin servidor permite realizar un escalado instantáneo con el fin de satisfacer las necesidades elásticas y ofrece una microfacturación para "pagar por lo que se usa" y no más. Para usar la informática sin servidor es necesario cambiar la forma de pensar y adoptar un nuevo enfoque para compilar aplicaciones, pero no es la solución adecuada para cada problema. Como desarrollador, debe decidir lo siguiente:

- ¿Qué ventajas e inconvenientes tiene la informática sin servidor?
- ¿Por qué debe plantearse el uso de la informática sin servidor para sus aplicaciones?
- ¿Cómo puede compilar, probar, implementar y mantener el código sin servidor?
- ¿En qué casos tiene sentido migrar el código a la informática sin servidor en las aplicaciones existente y cuál es la mejor forma de conseguir esa transformación?

## <a name="about-this-guide"></a>Acerca de esta guía

Esta guía se centra en el desarrollo nativo en la nube de las aplicaciones en las que se usa la informática sin servidor. En el libro se destacan las ventajas que ofrece esta característica y se exponen los posibles inconvenientes de desarrollar aplicaciones sin servidor. Además, se proporciona una encuesta sobre arquitecturas sin servidor. También se muestran muchos ejemplos del uso que se puede dar a la informática sin servidor, junto con varios modelos de diseño sin servidor.

En esta guía se describen los componentes de la plataforma sin servidor de Azure y se pone especial énfasis en la implementación de la informática sin servidor mediante [Azure Functions](/azure/azure-functions/functions-overview). Se le proporcionará información sobre desencadenadores y enlaces y sobre cómo implementar aplicaciones sin servidor que se basan en el estado mediante funciones duraderas. Por último, se muestran ejemplos y casos prácticos empresariales que le permitirán ponerse en contexto y obtener un marco de referencia para determinar si la informática sin servidor es una opción adecuada para sus proyectos.

## <a name="evolution-of-cloud-platforms"></a>Evolución de las plataformas en la nube

La informática sin servidor es la culminación de varias iteraciones de plataformas en la nube. La evolución empezó con los equipos sin sistema operativo de los centros de datos y evolucionó mediante las infraestructuras como servicio (IaaS) y las plataformas como servicio (PaaS).

![Evolución del entorno local al entorno sin servidor](./media/serverless-evolution-iaas-paas.png)

Antes de que se usara la nube, existía una frontera clara entre el desarrollo y las operaciones. Para implementar una aplicación era necesario responder a un sinfín de preguntas:

- ¿Qué hardware hay que instalar?
- ¿Cómo se protege el acceso físico a las máquinas?
- ¿El centro de datos necesita un sistema de alimentación ininterrumpida, (SAI [UPS])?
- ¿Dónde se envían las copias de seguridad del almacenamiento?
- ¿Es necesaria una fuente de alimentación?

La lista de interrogantes no terminaba aquí, y ello representaba una sobrecarga de grandes dimensiones. En muchas situaciones, los departamentos de TI se veían obligados a tratar con gran cantidad de residuos. Dichos residuos eran el resultado de una sobreasignación de servidores como máquinas de copias de seguridad para la recuperación ante desastres y de servidores en espera para permitir una escalabilidad horizontal. Afortunadamente, la implementación de la tecnología de virtualización (como [Hyper-V](/virtualization/hyper-v-on-windows/about/)) mediante máquinas virtuales (VM) dio un impulso a las infraestructuras como servicio (IaaS). Las infraestructuras virtualizadas permitían a las operaciones establecer como eje principal un conjunto estándar de servidores, lo que generaba entornos flexibles capaces de aprovisionar servidores únicos "bajo demanda". Sin embargo, lo más importante es que con la virtualización se sentaba la base para usar la nube con el fin de proporcionar máquinas virtuales "como servicio". Ello permitía a las empresas dejar de preocuparse por las fuentes de alimentación y las máquinas físicas. Por lo tanto, pudieron centrarse en el entorno virtual.

Las infraestructuras como servicio todavía conllevan una gran sobrecarga porque el equipo de operaciones sigue siendo el responsable de diversas tareas. Estas tareas incluyen:

- Copia de seguridad y revisión de servidores.
- Instalación de paquetes.
- Mantener actualizado el sistema operativo.
- Supervisar la aplicación.

La siguiente evolución redujo la sobrecarga proporcionando una plataforma como servicio (PaaS). Con dicha plataforma, el proveedor de nube controla los sistemas operativos, las revisiones de seguridad e, incluso, los paquetes necesarios para admitir una plataforma concreta. En lugar de compilar una VM, configurar después .NET y mantener los servidores de Internet Information Services (IIS), los desarrolladores solo tienen que elegir un "destino de la plataforma", como una "aplicación web " o un "punto de conexión de API" e implementar el código directamente. Por lo tanto, los interrogantes relacionados con la infraestructura quedan reducidos a estos:

- ¿Qué tamaños de servicio son necesarios?
- ¿Cómo se escalan horizontalmente los servicios (añadir más servidores o nodos)?
- ¿Cómo se escalan verticalmente los servicios (aumentar la capacidad de hospedar servidores o nodos)?

La informática sin servidor reduce todavía más los servidores centrándose en el código orientado a eventos. En lugar de usar una plataforma, los desarrolladores pueden centrarse en un microservicio que tiene una función concreta. Estas son las dos preguntas clave para implementar el código sin servidor:

- ¿Qué desencadena el código?
- ¿Qué hace el código?

Con la informática sin servidor, la infraestructura se reduce. En algunos casos, el desarrollador se puede olvidar totalmente del host. El desarrollador se centra en un desencadenador HTTP, independientemente de si se ejecuta o no una instancia de IIS, Kestrel, Apache u otro servidor web para administrar solicitudes web. El desencadenador proporciona la carga estándar y multiplataforma para la solicitud. La carga no solo simplifica el proceso de desarrollo, sino que facilita las pruebas y, en algunos casos, permite que el código sea pueda portar fácilmente entre plataformas.

La microfacturación es otra de las características de la informática sin servidor. Es habitual que las aplicaciones web hospeden puntos de conexión de API web. En los equipos tradicionales sin sistema operativo, en las implementaciones IaaS e incluso PaaS, se paga continuamente por los recursos necesarios para hospedar las API. Por lo tanto, se paga por hospedar los puntos de conexión aunque no se acceda a ellos. Con frecuencia verá que una API se llama más a menudo que las otras, de forma que todo el sistema se escala a partir de su compatibilidad con los puntos de conexión populares. La informática sin servidor permite escalar cada punto de conexión por separado y pagar por su uso, de forma que no se incurre en ningún costo cuando no se está llamando a las API. En muchas circunstancias, la migración puede reducir de forma drástica el costo continuo que implica la compatibilidad con los puntos de conexión.

## <a name="what-this-guide-doesnt-cover"></a>Aspectos no tratados en esta guía

En esta guía se pone un especial énfasis en los distintos enfoques de arquitectura y modelos de diseño y no se ofrece una explicación detallada sobre los detalles de implementación de Azure Functions, [Logic Apps](/azure/logic-apps/logic-apps-what-are-logic-apps) u otras plataformas sin servidor. Por ejemplo, entre los aspectos que no se tratan se incluyen los flujos de trabajo avanzados de Logic Apps y las características de Azure Functions, como la configuración del uso compartido de recursos entre orígenes (CORS), la aplicación de dominios personalizados o la carga de certificados SSL. Estos detalles están disponibles en la [documentación de Azure Functions](/azure/azure-functions/functions-reference) en línea.

### <a name="additional-resources"></a>Recursos adicionales

- [Centro de arquitectura de Azure](/azure/architecture/)
- [Procedimientos recomendados para aplicaciones en la nube](/azure/architecture/best-practices/api-design)

## <a name="who-should-use-the-guide"></a>Destinatarios de esta guía

Esta guía está destinada a aquellos desarrolladores y arquitectos de soluciones que quieren compilar aplicaciones empresariales con .NET y que pueden usar componentes sin servidor en un entorno local o bien en la nube. Resulta útil para los desarrolladores, arquitectos y directores técnicos interesados por lo siguiente:

- Conocer las ventajas e inconvenientes del desarrollo sin servidor.
- Obtener información sobre cómo usar la arquitectura sin servidor.
- Implementaciones de ejemplo sobre aplicaciones sin servidor

## <a name="how-to-use-the-guide"></a>Cómo usar esta guía

En la primera parte de esta guía se estudia por qué la informática sin servidor es una opción viable mediante la comparación de una serie de distintos enfoques de arquitectura. Se examina tanto la tecnología como el ciclo de vida de desarrollo porque todos los aspectos del desarrollo de software se ven afectados por las decisiones relacionadas con la arquitectura. A continuación, en la guía se examinan casos de uso y modelos de diseño y se incluyen implementaciones de referencia mediante Azure Functions. Cada sección contiene recursos adicionales para obtener más información sobre una cuestión concreta. La guía finaliza con una serie de recursos para los tutoriales y una exploración práctica de la implementación sin servidor.

## <a name="send-your-feedback"></a>Envíe sus comentarios

Nos gustaría que contribuyese al desarrollo constante de la guía y los ejemplos relacionados enviando sus comentarios. Si tiene algún comentario sobre cómo se puede mejorar esta guía, escríbalo en la sección de comentarios situada en la parte inferior de cualquier página creada en [Problemas de GitHub](https://github.com/dotnet/docs/issues).

>[!div class="step-by-step"]
>[Siguiente](architecture-approaches.md)
