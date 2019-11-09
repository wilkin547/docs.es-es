---
title: Aprovechamiento de funciones sin servidor
description: Aprovechamiento de Azure Functions sin servidor en aplicaciones nativas de la nube
ms.date: 06/30/2019
ms.openlocfilehash: 77ddef0eb8844ea1b55cd2fc5ec8aa12593c8631
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841748"
---
# <a name="leveraging-serverless-functions"></a>Aprovechamiento de funciones sin servidor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En el espectro de administración de equipos y sistemas operativos completos para sacar provecho de las funcionalidades de la nube, el uso del servidor se encuentra en el extremo extremo en el que lo único que es responsable es el código y solo paga cuando se ejecuta el código. Azure Functions proporciona una manera de crear funcionalidades sin servidor en las aplicaciones.

## <a name="what-is-serverless"></a>¿Qué es sin servidor?

La informática sin servidor no significa que no haya ningún servidor implicado en la ejecución de la aplicación; el código todavía se ejecuta en un servidor en algún lugar. La diferencia es que el equipo de desarrollo de aplicaciones ya no necesita preocuparse por la administración de la infraestructura de servidor. Soluciones informáticas sin servidor como Azure Functions ayudar a los equipos a aumentar su productividad y permitir a las organizaciones optimizar sus recursos y centrarse en la entrega de soluciones.

La informática sin servidor usa contenedores sin estado desencadenados por eventos para hospedar su aplicación o parte de la aplicación. Las plataformas sin servidor se pueden escalar horizontalmente y en para satisfacer la demanda según sea necesario. Las plataformas como Azure Functions tienen acceso directo sencillo a otros servicios de Azure, como colas, eventos y almacenamiento.

## <a name="what-challenges-are-solved-by-serverless"></a>¿Qué desafíos resuelve sin servidor?

Sin servidor es la abstracción definitiva de la ejecución de su propio hardware. Los desarrolladores pueden centrarse exclusivamente en la escritura de código para resolver problemas empresariales, sin preocuparse por cualquiera de las siguientes tareas que podrían haber sido necesarias al hospedar sus propios servidores:

- Comprar máquinas y licencias de software
- Alojamiento, protección, configuración y mantenimiento de los equipos y sus requisitos de red, alimentación y A/C
- Revisión y actualización de sistemas operativos y software
- Configuración de servidores web o servicios de equipo para hospedar software de aplicación
- Configuración de software de aplicaciones en su plataforma

Muchas empresas emplean docenas de miembros del personal y asignan grandes presupuestos para respaldar estos problemas de la infraestructura de hardware. Simplemente pasar a la nube elimina algunos de estos problemas: desplazar las aplicaciones hasta el modo sin servidor eliminará el resto.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>¿Qué escenarios son adecuados para sin servidor?

Sin servidor usa funciones individuales de ejecución breve a las que se llama en respuesta a algún desencadenador. Esto hace que sean ideales para el procesamiento de tareas en segundo plano.

Por ejemplo, es posible que una aplicación necesite enviar un correo electrónico como parte del procesamiento de una solicitud. En lugar de enviar el correo electrónico como parte del control de la solicitud Web, los detalles del correo electrónico podrían colocarse en una cola y se podría usar una función de Azure para recoger el mensaje y enviar el correo electrónico. Muchas partes diferentes de la aplicación, o incluso de muchas aplicaciones, pueden aprovechar esta misma función de Azure, lo que proporciona un rendimiento y una escalabilidad mejorados para las aplicaciones y el uso de la [nivelación de carga basada en cola](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) para evitar cuellos de botella relacionados con el envío de los mensajes de correo electrónico.

Aunque un [patrón de publicador o suscriptor](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) entre aplicaciones y Azure Functions es el patrón más común, son posibles otros patrones. Otros eventos pueden desencadenar Azure Functions, como los cambios realizados en Azure Blob Storage. Una aplicación que admitía cargas de imágenes podría tener una función de Azure responsable de crear imágenes en miniatura o cambiar el tamaño de las imágenes cargadas a dimensiones coherentes u optimizar el tamaño de la imagen. Toda esta funcionalidad se puede desencadenar directamente mediante inserciones en Azure Blob Storage, manteniendo la complejidad y la carga de trabajo fuera de la propia aplicación.

Muchas aplicaciones tienen procesos de ejecución prolongada como parte de sus flujos de trabajo. A menudo, estas tareas se realizan como parte de la interacción del usuario con la aplicación, lo que obliga al usuario a esperar y afectar negativamente a su experiencia. La informática sin servidor proporciona una excelente manera de realizar tareas más lentas fuera del bucle de interacción del usuario, y estas tareas se pueden escalar fácilmente con la demanda sin necesidad de escalar toda la aplicación.

## <a name="when-should-you-avoid-serverless"></a>¿Cuándo debe evitarse el servidor?

La informática sin servidor se utiliza mejor para las tareas que no bloquean la interfaz de usuario. Esto significa que no son ideales para hospedar aplicaciones web o API Web directamente. La razón principal es que las soluciones sin servidor se aprovisionan y escalan a petición. Cuando se necesita una nueva instancia de una función, a la que se hace referencia como *Inicio en frío*, se tarda en aprovisionar. Este tiempo suele ser unos pocos segundos, pero puede ser más largo en función de una serie de factores. Una sola instancia se puede mantener activa indefinidamente (por ejemplo, mediante una solicitud periódica), pero el problema de inicio en frío permanece si el número de instancias necesita escalarse verticalmente.

![en frío frente al inicio en caliente](./media/cold-start-warm-start.png)
**figura 3-10**. Inicio en frío frente a Inicio en caliente.

Si necesita evitar que el frío se inicie por completo, puede optar por cambiar de un [plan de consumo a un plan dedicado](https://azure.microsoft.com/blog/understanding-serverless-cold-start/). También puede [configurar una o varias instancias previamente preparadas](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) con el plan Premium, de modo que, cuando necesite agregar otra instancia, ya esté activa y lista para ir. Estas opciones pueden mitigar una de las principales preocupaciones asociadas a la informática sin servidor.

Normalmente, también debe evitar el funcionamiento sin servidor para tareas de ejecución prolongada. Son mejores para pequeñas piezas de trabajo que se pueden completar rápidamente. La mayoría de las plataformas sin servidor requieren funciones individuales para completarse en unos minutos. Azure Functions tiene como valor predeterminado una duración de tiempo de espera de 5 minutos (se puede configurar hasta 10 minutos). El plan de Azure Functions Premium también puede mitigar este problema, establecer de forma predeterminada los tiempos de espera de 30 minutos y permitir que se configure un límite superior sin límite.

Por último, el uso de sin servidor para ciertas tareas dentro de la aplicación agrega complejidad. A menudo, es mejor diseñar la aplicación en una manera modular y de acoplamiento flexible en primer lugar y, a continuación, identificar si las ventajas que el servidor no puede ofrecer es el que merece la complejidad adicional. Muchas aplicaciones más pequeñas se ejecutarán perfectamente en una única implementación monolítica, sin necesidad de que la informática sin servidor de arquitectura de aplicación distribuida requiera.

## <a name="references"></a>Referencias

- [Descripción del inicio en frío sin servidor](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Instancias de Azure Functions precalentadas](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)

>[!div class="step-by-step"]
>[Anterior](leverage-containers-orchestrators.md)
>[Siguiente](combine-containers-serverless-approaches.md)
