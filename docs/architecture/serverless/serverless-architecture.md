---
title: 'Arquitectura sin servidor: aplicaciones sin servidor'
description: Exploración de las diversas arquitecturas y aplicaciones que admiten las arquitecturas sin servidor como, por ejemplo, aplicaciones web, para dispositivos móviles e IoT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 838dcd7b41df0d8297e1ae10f9c04a8d5b83b332
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522410"
---
# <a name="serverless-architecture"></a>Arquitectura sin servidor

Existen muchos enfoques relacionados con el uso de arquitecturas [sin servidor](https://azure.com/serverless). En este capítulo se exploran algunos ejemplos de arquitecturas comunes que se integran sin servidor. También trata sobre los problemas que pueden constituir desafíos adicionales o que requieren una atención adicional al implementar arquitecturas sin servidor. Por último, se proporcionan varios ejemplos de diseño que ilustran varios casos de uso de arquitecturas sin servidor.

Los hosts sin servidor suelen usar un nivel existente basado en contenedores o PaaS para administrar las instancias sin servidor. Por ejemplo, Azure Functions se basa en [Azure App Service](https://docs.microsoft.com/azure/app-service/). App Service se usa para escalar horizontalmente instancias y administrar el entorno de ejecución que ejecuta el código de Azure Functions. En el caso de funciones basadas en Windows, el host se ejecuta como PaaS y escala horizontalmente el entorno de ejecución de .NET. En el caso de las funciones basadas en Linux, el host utiliza contenedores.

![Arquitectura de Azure Functions](./media/azure-functions-architecture.png)

WebJobs Core proporciona un contexto de ejecución para la función. Language Runtime ejecuta scripts, bibliotecas y hospeda la plataforma para el lenguaje de destino. Por ejemplo, Node.js se emplea para ejecutar funciones de JavaScript y .NET Framework para funciones de C#. Más adelante en este capítulo obtendrá más información sobre las opciones del lenguaje y la plataforma.

Algunos proyectos pueden beneficiarse de la adopción de un enfoque "todo incluido" en relación con las arquitecturas sin servidor. Las aplicaciones que dependen en gran medida de los microservicios pueden implementar todos los microservicios mediante la tecnología sin servidor. La mayoría de las aplicaciones son híbridas, siguen un diseño de n niveles y usan una arquitectura sin servidor para los componentes, lo cual tiene sentido ya que los componentes son modulares y escalables de forma independiente. Para ayudar a comprender estos escenarios, en esta sección se explican algunos ejemplos comunes de arquitectura que usan el modelo sin servidor.

## <a name="full-serverless-back-end"></a>Back-end sin servidor completo

El back-end sin servidor completo es idóneo para varios tipos de escenarios, especialmente a la hora de compilar aplicaciones nuevas o de tipo "green field". Una aplicación con una gran área expuesta de API puede beneficiarse de la implementación de cada API como una función sin servidor. Las aplicaciones que se basan en una arquitectura de microservicios constituyen otro ejemplo que se puede implementar como un back-end sin servidor completo. Los microservicios se comunican entre sí a través de varios protocolos. Entre los escenarios específicos se incluyen:

- Productos de SaaS basados en API (por ejemplo: procesador de pagos financieros).
- Aplicaciones controladas por mensajes (por ejemplo: una solución de supervisión de dispositivos).
- Aplicaciones centradas en la integración entre servicios (por ejemplo: una aplicación de reserva de billetes de avión).
- Procesos que se ejecutan periódicamente (por ejemplo: la limpieza de una base de datos basada en un temporizador).
- Aplicaciones que se centran en la transformación de datos (por ejemplo: importación desencadenada mediante la carga de archivos).
- Procesos de extracción, transformación y carga de datos (ETL).

Hay otros casos de uso más específicos que se describen más adelante en este documento.

## <a name="monoliths-and-starving-the-beast"></a>Monolitos y "extinción por reducción"

Un desafío frecuente es la migración de una aplicación monolítica existente a la nube. El enfoque menos arriesgado consiste en la migración completa mediante "lift-and-shift" a las máquinas virtuales. Muchas tiendas prefieren usar la migración como una oportunidad para modernizar su código base. Hay un práctico enfoque para la migración que se denomina "extinción por reducción". Para empezar, en este escenario, la aplicación monolítica se migra "tal cual". Posteriormente, se modernizan los servicios seleccionados. En algunos casos, la firma del servicio es idéntica a la original: simplemente se hospeda como una función. Los clientes se actualizan para poder usar el nuevo servicio en lugar del punto de conexión del monolito. Mientras tanto, pasos como la replicación de base de datos permiten que los microservicios hospeden su propio almacenamiento, incluso cuando el monolito sigue controlando las transacciones. Por último, todos los clientes se migran a los nuevos servicios. El monolito se "extingue" (es decir, dejan de realizarse llamadas a sus servicios) hasta que se reemplaza toda la funcionalidad. La combinación de servidores proxy y una arquitectura sin servidor puede facilitar gran parte de esta migración.

![Migración de monolitos sin servidor](./media/serverless-monolith-migration.png)

Para más información acerca de este enfoque, vea este vídeo: [Bring your app to the cloud with serverless Azure Functions](https://channel9.msdn.com/Events/Connect/2017/E102) (Migración de aplicaciones a la nube con Azure Functions sin servidor).

## <a name="web-apps"></a>Aplicaciones web

Las aplicaciones web son buenas candidatas para convertirse en aplicaciones sin servidor. Hoy en día hay dos enfoques comunes relacionados con las aplicaciones web: el enfoque controlado por servidor y el controlado por el cliente (por ejemplo, una aplicación de página única o SPA). Las aplicaciones web controladas por servidor suelen usar una capa de middleware para emitir llamadas API para representar la interfaz de usuario web. Las aplicaciones de página única realizan llamadas a la API REST directamente desde el explorador. En ambos escenarios, la arquitectura sin servidor puede acomodar el middleware o la solicitud de la API REST proporcionando la lógica de negocios necesaria. Una arquitectura común consiste en crear un servidor web estático ligero. La aplicación de página única (SPA) proporciona HTML, CSS, JavaScript y otros recursos del explorador. A continuación, la aplicación web se conecta a un back-end de microservicios.

## <a name="mobile-back-ends"></a>Back-ends para dispositivos móviles

El paradigma orientado a eventos de las aplicaciones sin servidor hace que resulten idóneas como back-ends para dispositivos móviles. El dispositivo móvil desencadena los eventos y el código sin servidor se ejecuta para satisfacer las solicitudes. Aprovechar un modelo sin servidor permite a los desarrolladores mejorar la lógica de negocios sin tener que implementar una actualización de la aplicación completa. El enfoque sin servidor también permite a los equipos compartir puntos de conexión y trabajar en paralelo.

Los desarrolladores de dispositivos móviles pueden crear lógica de negocios sin necesidad de convertirse en expertos en lo relacionado con el servidor. Tradicionalmente, las aplicaciones móviles estaban conectadas a servicios locales. La creación del nivel de servicio requería el conocimiento de la plataforma de servidor y un paradigma de programación. Los desarrolladores trabajaban con operaciones para aprovisionar y configurar los servidores de forma adecuada. A veces, se dedicaban días o incluso semanas a la creación de una canalización de implementación. El modo sin servidor ha dado respuesta a todos estos desafíos.

El modo sin servidor reduce las dependencias del lado servidor y permite al desarrollador centrarse en la lógica de negocios. Por ejemplo, un desarrollador móvil que crea aplicaciones mediante una plataforma de JavaScript también puede crear funciones sin servidor con JavaScript. El host sin servidor administra el sistema operativo, una instancia de Node.js para hospedar el código, las dependencias de paquetes, etc. Se proporciona a los desarrolladores un conjunto sencillo de entradas y una plantilla estándar para salidas. Con ello, los desarrolladores se pueden centrar en la creación y la prueba de la lógica de negocios. Por lo tanto, pueden usar las aptitudes existentes para compilar la lógica de back-end de la aplicación móvil sin tener que aprender a manejar nuevas plataformas ni convertirse en un "desarrollador del lado servidor".

![Back-end móvil sin servidor](./media/serverless-mobile-backend.png)

La mayoría de los proveedores de nube ofrecen productos sin servidor basados en dispositivos móviles que simplifican todo el ciclo de vida de desarrollo de estos. Los productos pueden automatizar el aprovisionamiento de bases de datos para conservar datos, controlar problemas de DevOps, proporcionar compilaciones basadas en la nube y plataformas de pruebas, y ofrecer la posibilidad de generar scripts de procesos empresariales con el lenguaje preferido del desarrollador. La utilización de un enfoque sin servidor centrado en los dispositivos móviles puede simplificar el proceso. El modo sin servidor elimina la enorme sobrecarga que produce el aprovisionamiento, configuración y mantenimiento de servidores para el back-end móvil.

## <a name="internet-of-things-iot"></a>Internet de las cosas (IoT)

IoT hace referencia a los objetos físicos que están conectados a una misma red. A veces se denominan "dispositivos conectados" o "dispositivos inteligentes". Todo, desde vehículos a equipos expendedores, puede estar conectado y enviar información que puede incluir desde un inventario a datos de un sensor como, por ejemplo, la temperatura y la humedad. En la empresa, Internet de las cosas proporciona mejoras en los procesos empresariales mediante la supervisión y la automatización. Los datos de IoT se pueden usar para regular la temperatura de un gran almacén o realizar un seguimiento del inventario a través de la cadena de suministro. Con IoT se pueden detectar vertidos químicos y llamar a los bomberos si se detecta humo.

El gran volumen de dispositivos e información a menudo requiere una arquitectura orientada a eventos para enrutar y procesar mensajes. El modo sin servidor es una solución ideal por varias razones:

- Permite escalar a medida que aumenta el volumen de dispositivos y datos.
- Permite agregar nuevos puntos de conexión para admitir nuevos dispositivos y sensores.
- Facilita el control de versiones independiente para que los desarrolladores puedan actualizar la lógica de negocios de un dispositivo específico sin tener que implementar todo el sistema.
- Resistencia y menos tiempo de inactividad.

La generalización de IoT ha dado lugar a varios productos sin servidor que se centran específicamente en cuestiones de IoT, como [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub). El modo sin servidor automatiza tareas como el registro de dispositivos, la aplicación de directivas, el seguimiento e, incluso, la implementación de código en los dispositivos *del perímetro*. El perímetro se refiere a dispositivos como sensores y actuadores que están conectados a Internet, pero no constituyen una parte activa de este.

>[!div class="step-by-step"]
>[Anterior](architecture-approaches.md)
>[Siguiente](serverless-architecture-considerations.md)
