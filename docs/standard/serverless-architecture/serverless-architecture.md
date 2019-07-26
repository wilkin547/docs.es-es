---
title: 'Arquitectura sin servidor: aplicaciones sin servidor'
description: Exploración de diversas arquitecturas y aplicaciones compatibles con las arquitecturas sin servidor, como Web Apps, Mobile y IoT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3b22fecfdc693154dbdeb3e872e0e246e8ca41f9
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68434066"
---
# <a name="serverless-architecture"></a>Arquitectura sin servidor

Existen muchos enfoques para usar las arquitecturas sin [servidor](https://azure.com/serverless) . En este capítulo se exploran ejemplos de arquitecturas comunes que se integran sin servidor. También se tratan los problemas que pueden suponer desafíos adicionales o que se deben tener en cuenta al implementar sin servidor. Por último, se proporcionan varios ejemplos de diseño que ilustran varios casos de uso sin servidor.

Los hosts sin servidor suelen usar un nivel existente basado en contenedores o PaaS para administrar las instancias sin servidor. Por ejemplo, Azure Functions se basa en [Azure App Service](https://docs.microsoft.com/azure/app-service/). El App Service se usa para escalar horizontalmente las instancias y administrar el motor en tiempo de ejecución que ejecuta Azure Functions código. En el caso de las funciones basadas en Windows, el host se ejecuta como PaaS y escala horizontalmente el entorno de tiempo de ejecución de .NET. En el caso de las funciones basadas en Linux, el host aprovecha los contenedores.

![Arquitectura de Azure Functions](./media/azure-functions-architecture.png)

El núcleo de webjobs proporciona un contexto de ejecución para la función. Language Runtime ejecuta scripts, ejecuta bibliotecas y hospeda el marco de trabajo para el lenguaje de destino. Por ejemplo, node. js se usa para ejecutar funciones de JavaScript y el .NET Framework se usa para C# ejecutar funciones. Más adelante en este capítulo obtendrá más información sobre las opciones de lenguaje y plataforma.

Algunos proyectos pueden beneficiarse de la adopción de un enfoque "todo en todo" para sin servidor. Las aplicaciones que se basan en gran medida en microservicios pueden implementar todos los microservicios mediante tecnología sin servidor. La mayoría de las aplicaciones son híbridas, siguiendo un diseño de N niveles y usando sin servidor para los componentes que tienen sentido, ya que los componentes son modulares y escalables de forma independiente. Para ayudar a comprender estos escenarios, en esta sección se explican algunos ejemplos comunes de arquitectura que usan sin servidor.

## <a name="full-serverless-back-end"></a>Back-end sin servidor completo

El back-end sin servidor completo es ideal para varios tipos de escenarios, especialmente cuando se compilan aplicaciones nuevas o "de campo verde". Una aplicación con un área de gran superficie de API puede beneficiarse de la implementación de cada API como una función sin servidor. Las aplicaciones que se basan en la arquitectura de microservicios son otro ejemplo que se puede implementar como un back-end sin servidor completo. Los microservicios se comunican entre sí a través de varios protocolos. Algunos escenarios específicos son:

* Productos SaaS basados en API (por ejemplo: procesador de pagos financieros).
* Aplicaciones controladas por mensajes (ejemplo: solución de supervisión de dispositivos).
* Aplicaciones centradas en la integración entre servicios (ejemplo: aplicación de reserva de líneas aéreas).
* Procesos que se ejecutan periódicamente (por ejemplo: limpieza de base de datos basada en temporizador).
* Aplicaciones centradas en la transformación de datos (ejemplo: importación desencadenada por la carga de archivos).
* Extraer procesos de transformación y carga (ETL).

Hay otros casos de uso más específicos que se describen más adelante en este documento.

## <a name="monoliths-and-starving-the-beast"></a>Monolitos y "Private de la"

Un desafío común es migrar una aplicación monolítica existente a la nube. El enfoque menos arriesgado consiste en "levantar y mover" por completo a las máquinas virtuales. Muchas tiendas prefieren usar la migración como una oportunidad para modernizar su código base. Un enfoque práctico para la migración se denomina "privar a la misma". En este escenario, el monolito se migra "tal cual" para comenzar. A continuación, se modernizan los servicios seleccionados. En algunos casos, la firma del servicio es idéntica a la original: simplemente se hospeda como una función. Los clientes se actualizan para usar el nuevo servicio en lugar del punto de conexión monolito. Mientras tanto, los pasos como la replicación de base de datos permiten que los microservicios hospeden su propio almacenamiento, incluso cuando el monolito sigue controlando las transacciones. Finalmente, todos los clientes se migran a los nuevos servicios. El monolito está "desusado" (ya no se llama a sus servicios) hasta que se ha reemplazado toda la funcionalidad. La combinación de servidores proxy y sin servidor puede facilitar gran parte de esta migración.

![Migración de monolítico sin servidor](./media/serverless-monolith-migration.png)

Para obtener más información acerca de este enfoque, vea el vídeo: [Lleve su aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102).

## <a name="web-apps"></a>Aplicaciones web

Las aplicaciones web son buenos candidatos para aplicaciones sin servidor. Hoy en día hay dos enfoques comunes para Web Apps: controlado por servidor y controlado por el cliente (por ejemplo, aplicación de una sola página o SPA). Las aplicaciones web controladas por el servidor suelen usar una capa de middleware para emitir llamadas API para representar la interfaz de usuario Web. Las aplicaciones de SPA realizan llamadas a la API de REST directamente desde el explorador. En ambos escenarios, sin servidor puede acomodar el middleware o la solicitud de la API de REST proporcionando la lógica de negocios necesaria. Una arquitectura común consiste en crear un servidor Web estático ligero. La aplicación de una sola página (SPA) sirve HTML, CSS, JavaScript y otros recursos del explorador. A continuación, la aplicación web se conecta a un back-end de microservicios.

## <a name="mobile-back-ends"></a>Back-ends móviles

El paradigma orientado a eventos de las aplicaciones sin servidor hace que sean ideales como back-ends móviles. El dispositivo móvil desencadena los eventos y el código sin servidor se ejecuta para satisfacer las solicitudes. Aprovechar un modelo sin servidor permite a los desarrolladores mejorar la lógica de negocios sin tener que implementar una actualización de la aplicación completa. El enfoque sin servidor también permite a los equipos compartir puntos de conexión y trabajar en paralelo.

Los desarrolladores de dispositivos móviles pueden crear lógica de negocios sin convertirse en expertos en el lado del servidor. Tradicionalmente, las aplicaciones móviles están conectadas a servicios locales. La creación del nivel de servicio requería comprender la plataforma de servidor y el paradigma de programación. Los desarrolladores trabajaron con operaciones para aprovisionar servidores y configurarlos de forma adecuada. A veces, se dedicaron días o incluso semanas a la creación de una canalización de implementación. Todos estos desafíos los aborda sin servidor.

Sin servidor abstrae las dependencias del lado servidor y permite al desarrollador centrarse en la lógica de negocios. Por ejemplo, un desarrollador móvil que crea aplicaciones con un marco de trabajo de JavaScript también puede crear funciones sin servidor con JavaScript. El host sin servidor administra el sistema operativo, una instancia de node. js para hospedar el código, las dependencias de paquete, etc. Se proporciona al desarrollador un conjunto sencillo de entradas y una plantilla estándar para salidas. A continuación, pueden centrarse en la creación y la prueba de la lógica de negocios. Por lo tanto, pueden usar los conocimientos existentes para compilar la lógica de back-end de la aplicación móvil sin tener que aprender nuevas plataformas o convertirse en un "desarrollador del lado servidor".

![Back-end móvil sin servidor](./media/serverless-mobile-backend.png)

La mayoría de los proveedores de nube ofrecen productos sin servidor basados en móviles que simplifican todo el ciclo de vida de desarrollo móvil. Los productos pueden automatizar el aprovisionamiento de bases de datos para conservar los datos, controlar los problemas de DevOps, proporcionar compilaciones basadas en la nube y marcos de pruebas, y la capacidad de generar scripts de procesos empresariales con el lenguaje preferido del desarrollador. Seguir un enfoque sin servidor centrado en dispositivos móviles puede simplificar el proceso. Sin servidor elimina la enorme sobrecarga del aprovisionamiento, la configuración y el mantenimiento de servidores para el back-end móvil.

## <a name="internet-of-things-iot"></a>Internet de las cosas (IoT)

IoT hace referencia a los objetos físicos que están conectados a la red. A veces se denominan "dispositivos conectados" o "dispositivos inteligentes". Todo desde automóviles y equipos expendedores pueden estar conectados y enviar información que abarca desde el inventario hasta los datos del sensor, como la temperatura y la humedad. En la empresa, IoT proporciona mejoras en los procesos empresariales a través de la supervisión y la automatización. Los datos de IoT se pueden usar para regular el clima en un almacén grande o realizar un seguimiento del inventario a través de la cadena de suministro. IoT puede detectar derrames químicas y llamar al Departamento de incendios cuando se detecte humo.

El gran volumen de dispositivos e información a menudo dicta una arquitectura orientada a eventos para enrutar y procesar mensajes. Sin servidor es una solución ideal por varias razones:

* Permite escalar a medida que aumenta el volumen de los dispositivos y los datos.
* Permite agregar nuevos extremos para admitir nuevos dispositivos y sensores.
* Facilita el control de versiones independiente para que los desarrolladores puedan actualizar la lógica de negocios de un dispositivo específico sin tener que implementar todo el sistema.
* Resistencia y menos tiempo de inactividad.

La presencia de IoT ha dado como resultado varios productos sin servidor que se centran específicamente en cuestiones de IoT, como [Azure IOT Hub](https://docs.microsoft.com/azure/iot-hub). Sin servidor automatiza tareas como el registro de dispositivos, la aplicación de directivas, el seguimiento e, incluso, la implementación de código en dispositivos en *el perímetro*. El borde se refiere a dispositivos como sensores y accionadores que están conectados a Internet, pero no a una parte activa.

>[!div class="step-by-step"]
>[Anterior](architecture-approaches.md)
>[Siguiente](serverless-architecture-considerations.md)
