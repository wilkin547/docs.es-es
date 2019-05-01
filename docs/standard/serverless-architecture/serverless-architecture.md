---
title: Arquitectura sin servidor - aplicaciones sin servidor
description: Exploración de varias arquitecturas y las aplicaciones que son compatibles con arquitecturas sin servidor, incluidas aplicaciones web, móviles y IoT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 60d225d9794d5c15b0cd8e42800ccad4d7872756
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967818"
---
# <a name="serverless-architecture"></a>Arquitectura sin servidor

Existen varios enfoques para usar [sin servidor](http://azure.com/serverless) arquitecturas. Este capítulo muestra ejemplos de arquitecturas comunes que se integran sin servidor. También trata cuestiones que pueden plantear retos adicionales o requieren una consideración adicional al implementar sin servidor. Finalmente, varios ejemplos de diseño son siempre que ilustran varios casos de uso sin servidor.

Hosts sin servidor suelen usar una existente basada en contenedor o la capa PaaS para administrar las instancias sin servidor. Por ejemplo, Azure Functions se basa en [Azure App Service](https://docs.microsoft.com/azure/app-service/). El servicio de aplicación se usa para escalar horizontalmente las instancias y administrar el tiempo de ejecución que se ejecuta el código de Azure Functions. Para funciones basadas en Windows, se ejecuta el host como PaaS y se escala horizontalmente el tiempo de ejecución .NET. Para las funciones basadas en Linux, el host aprovecha los contenedores.

![Arquitectura de las funciones de Azure](./media/azure-functions-architecture.png)

El núcleo de WebJobs proporciona un contexto de ejecución para la función. El tiempo de ejecución de lenguaje ejecuta secuencias de comandos, ejecuta las bibliotecas y hospeda el marco de trabajo para el lenguaje de destino. Por ejemplo, se usa Node.js para ejecutar las funciones de JavaScript y .NET Framework se usa para ejecutar funciones de C#. Aprenderá más acerca de las opciones de lenguaje y la plataforma más adelante en este capítulo.

Algunos proyectos pueden beneficiarse de adoptar un enfoque "todo" para sin servidor. Las aplicaciones que dependen en gran medida de microservicios pueden implementar todos los microservicios mediante la tecnología sin servidor. La mayoría de las aplicaciones son híbridas, siguiendo un diseño de N niveles y utilizando sin servidor para los componentes que tengan sentido, ya que los componentes son modulares y escalables de forma independiente. Para ayudar a dar sentido a estos escenarios, esta sección se explica algunos ejemplos comunes de arquitectura que utilice sin servidor.

## <a name="full-serverless-back-end"></a>Completa sin servidor back-end

El back-end sin servidor completa es ideal para varios tipos de escenarios, especialmente al crear nuevos o aplicaciones de "green field". Una aplicación con una gran área expuesta de API puede beneficiarse de la implementación de cada API como una función sin servidor. Las aplicaciones que se basan en la arquitectura de microservicios son otro ejemplo que podría implementarse como un back-end sin servidor completa. Los microservicios se comunican a través de protocolos distintos entre sí. Se incluyen escenarios concretos:

* Productos basados en API de SaaS (ejemplo: procesador de pagos financiero).
* Las aplicaciones controladas por mensajes (ejemplo: solución de supervisión de dispositivos).
* Las aplicaciones que se centran en la integración entre los servicios (ejemplo: aplicación de reservas de líneas aéreas).
* Los procesos que se ejecute periódicamente (ejemplo: limpieza base de datos basado en temporizador).
* Las aplicaciones que se centran en la transformación de datos (ejemplo: importación desencadenada por la carga de archivos).
* Extraiga los procesos de transformación y carga (ETL).

Hay casos de uso de otros, más específicos que se tratan más adelante en este documento.

## <a name="monoliths-and-starving-the-beast"></a>Monolitos y "privar a la bestia"

Un desafío común migra una aplicación monolítica existente a la nube. El enfoque menos riesgo es "Levantar y mover" completamente en máquinas virtuales. Muchas tiendas prefieren usar la migración como una oportunidad para modernizar su código base. Un enfoque práctico a la migración se denomina "y privar así a la bestia." En este escenario, se migra el monolito "tal cual" para empezar. A continuación, se ha modernizado servicios seleccionados. En algunos casos, la firma del servicio es idéntica al original: simplemente se hospeda como una función. Los clientes se actualizan para usar el nuevo servicio en lugar de con el punto de conexión de un monolito. Mientras tanto, los pasos como la replicación de base de datos permiten microservicios hospedar su propio almacenamiento, incluso cuando las transacciones aún se gestionan por el monolito. Finalmente, se migran todos los clientes en los nuevos servicios. El monolito "necesite" (sus servicios deje de llamarse) hasta que toda la funcionalidad se ha reemplazado. La combinación de sin servidor y los servidores proxy pueden facilitar en gran parte de esta migración.

![Migración de un monolito sin servidor](./media/serverless-monolith-migration.png)

Para obtener más información sobre este enfoque, vea el vídeo: [Traiga su aplicación a la nube con Azure Functions sin servidor](https://channel9.msdn.com/Events/Connect/2017/E102).

## <a name="web-apps"></a>Aplicaciones web

Las aplicaciones Web son buenos candidatos para las aplicaciones sin servidor. Actualmente, existen dos enfoques comunes para aplicaciones web: controlada por servidor y controladas por cliente (por ejemplo, la aplicación de página única o SPA). Las aplicaciones web controladas por el servidor utilizan normalmente una capa de middleware para emitir llamadas de API para representar la interfaz de usuario web. Las aplicaciones de SPA realizan llamadas API de REST directamente desde el explorador. En ambos escenarios, sin servidor puede alojar el software intermedio o una solicitud de API de REST, ya que proporciona la lógica empresarial necesaria. Es una arquitectura común crear un servidor web estático ligera. La aplicación de página única (SPA) sirve HTML, CSS, JavaScript y otros activos de explorador. La aplicación web, a continuación, se conecta a un back-end de microservicios.

## <a name="mobile-back-ends"></a>Back-end móviles

El paradigma orientado a eventos de aplicaciones sin servidor hace ideal como back-ends móviles. El dispositivo móvil desencadena los eventos y se ejecuta el código sin servidor para satisfacer las solicitudes. Aprovechar un modelo sin servidor permite a los desarrolladores mejorar la lógica de negocios sin tener que implementar una actualización completa de la aplicación. El enfoque sin servidor también permite a los equipos compartir puntos de conexión y trabajar en paralelo.

Los desarrolladores móviles pueden compilar la lógica de negocios sin convertirse en expertos en el servidor. Tradicionalmente, aplicaciones móviles conectadas a servicios locales. Creación de la capa de servicio requiere la descripción de la plataforma de servidor y el paradigma de programación. Los desarrolladores trabajaban con operaciones para aprovisionar servidores y configurarlos de forma adecuada. A veces, días o incluso semanas gastados en la creación de una canalización de implementación. Todos estos desafíos se direccionan mediante sin servidor.

Serverless abstrae las dependencias del lado servidor y permite al programador centrarse en la lógica de negocios. Por ejemplo, un desarrollador móvil que compila las aplicaciones usan un marco JavaScript puede crear funciones sin servidor con JavaScript. El host sin servidor administra el sistema operativo, una instancia de Node.js para hospedar el código, las dependencias de paquetes y mucho más. El desarrollador se proporciona un conjunto simple de entradas y una plantilla estándar para las salidas. A continuación, puede centrarse en compilar y probar la lógica de negocios. Por lo tanto, podemos usar habilidades existentes para crear la lógica de back-end para la aplicación móvil sin tener que aprender nuevas plataformas o conviértase en un "desarrollador del lado servidor".

![End móviles sin servidor nuevo](./media/serverless-mobile-backend.png)

La mayoría de los proveedores de nube ofrece productos sin servidor basada en mobile que simplifican el ciclo de vida completo de desarrollo móvil. Los productos pueden automatizar el aprovisionamiento de bases de datos para conservar los datos, controlar cuestiones de DevOps, proporcione se basa en la nube y las pruebas de marcos de trabajo y la capacidad de los procesos empresariales de script con el desarrollador idioma preferido. Un enfoque centrado en dispositivos móviles sin servidor puede agilizar el proceso. Sin servidor quita la enorme sobrecarga que supone aprovisionar, configurar y mantener servidores para el back-end móvil.

## <a name="internet-of-things-iot"></a>Internet de las cosas (IoT)

IoT hace referencia a objetos físicos que están conectados en red. Le denomina a veces "dispositivos conectados" o "dispositivos inteligentes". Todo el contenido de los automóviles y las máquinas expendedoras pueden estar conectados y enviar información comprendido inventario y datos del sensor, como la temperatura y humedad. En la empresa, IoT proporciona mejoras de los procesos empresariales a través de la supervisión y automatización. Datos de IoT pueden utilizarse para regular el clima en un almacenamiento de gran tamaño o realizar un seguimiento de inventario a través de la cadena de suministro. IoT puede detectar desbordamientos químicos y llamar al departamento de bomberos cuando se detecta el humo.

El volumen real de dispositivos y a menudo información dicta una arquitectura orientada a eventos para la ruta y procesar mensajes. Sin servidor es una solución ideal por varias razones:

* Permite escala a medida que el volumen de datos y dispositivos aumenta.
* Permite agregar nuevos extremos para admitir los nuevos dispositivos y sensores.
* Facilita el control de versiones independiente para que los desarrolladores puedan actualizar la lógica de negocios para un dispositivo específico sin tener que implementar todo el sistema.
* Resistencia y menor tiempo de inactividad.

La omnipresencia de IoT ha traducido en varios productos sin servidor que se centran específicamente en las preocupaciones de IoT, como [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub). Serverless automatiza las tareas como el registro de dispositivos, la aplicación de directivas, seguimiento e incluso implementación de código a los dispositivos en *el borde*. El borde se refiere a los dispositivos, como los sensores y accionadores que están conectados a, pero no parte activa de Internet.

>[!div class="step-by-step"]
>[Anterior](architecture-approaches.md)
>[Siguiente](serverless-architecture-considerations.md)
