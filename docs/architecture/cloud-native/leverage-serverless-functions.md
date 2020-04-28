---
title: Aprovechamiento de funciones sin servidor
description: Aprovechamiento de Azure Functions sin servidor en aplicaciones nativas de la nube
ms.date: 04/13/2020
ms.openlocfilehash: 176499e3cd0349cd689b9d13d1c237a6343d13f3
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199747"
---
# <a name="leveraging-serverless-functions"></a>Aprovechamiento de funciones sin servidor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En el espectro desde la administración de máquinas físicas hasta el aprovechamiento de funcionalidades de la nube, las vidas sin servidor se encuentran en el extremo extremo. Su única responsabilidad es el código y solo pagará cuando se ejecute el código. Azure Functions proporciona una manera de crear funcionalidades sin servidor en las aplicaciones nativas de la nube.

## <a name="what-is-serverless"></a>¿Qué significa sin servidor?

Sin servidor es un modelo de servicio relativamente nuevo de informática en la nube. No significa que los servidores sean opcionales: el código se sigue ejecutando en un servidor en algún lugar. La diferencia es que el equipo de aplicaciones ya no se preocupa por la administración de la infraestructura de servidor. En su lugar, el proveedor de la nube es el propietario de esta responsabilidad. El equipo de desarrollo aumenta su productividad al ofrecer soluciones empresariales a los clientes, no a la infraestructura.

La informática sin servidor usa contenedores sin estado desencadenados por eventos para hospedar los servicios. Se pueden escalar horizontalmente y en para satisfacer la demanda según sea necesario. Las plataformas sin servidor como Azure Functions tienen una estrecha integración con otros servicios de Azure, como colas, eventos y almacenamiento.

## <a name="what-challenges-are-solved-by-serverless"></a>¿Qué desafíos resuelve sin servidor?

Las plataformas sin servidor solucionan muchos problemas costosos y lentos:

- Comprar máquinas y licencias de software
- Alojamiento, protección, configuración y mantenimiento de los equipos y sus requisitos de red, alimentación y A/C
- Revisión y actualización de sistemas operativos y software
- Configuración de servidores web o servicios de equipo para hospedar software de aplicación
- Configuración de software de aplicaciones en su plataforma

Muchas empresas asignan grandes presupuestos para admitir la infraestructura de hardware. Pasar a la nube puede ayudar a reducir estos costos. desplazar las aplicaciones a sin servidor puede ayudar a eliminarlas.

## <a name="what-is-the-difference-between-a-microservice-and-a-serverless-function"></a>¿Cuál es la diferencia entre un microservicio y una función sin servidor?

Normalmente, un microservicio encapsula una funcionalidad empresarial, como un carro de la compra de un sitio de comercio electrónico en línea. Expone varias operaciones que permiten a un usuario administrar su experiencia de compra. Sin embargo, una función es un pequeño bloque ligero de código que ejecuta una operación de un solo propósito en respuesta a un evento.
Los microservicios se crean normalmente para responder a las solicitudes, a menudo desde una interfaz. Las solicitudes pueden estar basadas en REST o gRPC de HTTP. Los servicios sin servidor responden a los eventos. Su arquitectura orientada a eventos es ideal para procesar tareas en segundo plano de ejecución breve.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>¿Qué escenarios son adecuados para sin servidor?

Sin servidor expone funciones individuales de ejecución breve que se invocan en respuesta a un desencadenador. Esto hace que sean ideales para el procesamiento de tareas en segundo plano.

Es posible que una aplicación necesite enviar un correo electrónico como un paso de un flujo de trabajo. En lugar de enviar la notificación como parte de una solicitud de microservicio, coloque los detalles del mensaje en una cola. Una función de Azure puede quitar el mensaje de la cola y enviar el correo electrónico de forma asincrónica. Esto podría mejorar el rendimiento y la escalabilidad del microservicio. La [nivelación de la carga basada en cola](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) se puede implementar para evitar cuellos de botella relacionados con el envío de los mensajes de correo electrónico. Además, este servicio independiente podría reutilizarse como una utilidad en muchas aplicaciones diferentes.

La mensajería asincrónica de las colas y los temas es un patrón común para desencadenar funciones sin servidor. Sin embargo, otros eventos pueden desencadenar Azure Functions, como los cambios realizados en Azure Blob Storage. Un servicio que admite cargas de imágenes puede tener una función de Azure responsable de optimizar el tamaño de la imagen. La función se puede activar directamente mediante inserciones en Azure Blob Storage, lo que mantiene la complejidad de las operaciones de microservicios.

Muchos servicios tienen procesos de ejecución prolongada como parte de sus flujos de trabajo. A menudo, estas tareas se realizan como parte de la interacción del usuario con la aplicación. Estas tareas pueden obligar al usuario a esperar, lo que afecta negativamente a su experiencia. La informática sin servidor proporciona una excelente manera de trasladar tareas más lentas fuera del bucle de interacción del usuario. Estas tareas se pueden escalar con la demanda sin necesidad de escalar toda la aplicación.

## <a name="when-should-you-avoid-serverless"></a>¿Cuándo debe evitarse el servidor?

Las soluciones sin servidor se aprovisionan y escalan a petición. Cuando se invoca una instancia nueva, los inicios en frío son un problema común. Un inicio en frío es el período de tiempo que se tarda en aprovisionar esta instancia. Normalmente, este retraso puede ser algunos segundos, pero puede ser más largo en función de varios factores. Una vez aprovisionado, una instancia única se mantiene activa siempre que reciba solicitudes periódicas. Sin embargo, si se llama a un servicio con menos frecuencia, Azure puede quitarlo de la memoria y requerir un inicio en frío cuando se revoque. Los inicios en frío también son necesarios cuando una función se escala horizontalmente a una nueva instancia.

En la figura 3-10 se muestra un patrón de inicio en frío. Tenga en cuenta los pasos adicionales necesarios cuando la aplicación esté en frío.

![En frío frente a](./media/cold-start-warm-start.png)
Inicio en caliente,**figura 3-10**. Inicio en frío frente a Inicio en caliente.

Para evitar que el frío se inicie por completo, puede cambiar de un [plan de consumo a un plan dedicado](https://azure.microsoft.com/blog/understanding-serverless-cold-start/). También puede configurar una o varias [instancias previamente preparadas](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) con la actualización del plan Premium. En estos casos, cuando necesite agregar otra instancia, ya está activa y lista para ir. Estas opciones pueden ayudar a mitigar el problema de inicio en frío asociado a la informática sin servidor.

Los proveedores de nube facturan sin servidor según el tiempo de ejecución de proceso y la memoria consumida. Las operaciones de ejecución prolongada o las cargas de trabajo de consumo de memoria alta no son siempre las mejores candidatas para sin servidor. Las funciones sin servidor favorecen pequeños fragmentos de trabajo que pueden completarse rápidamente. La mayoría de las plataformas sin servidor requieren funciones individuales para completarse en unos minutos. Azure Functions tiene como valor predeterminado una duración de tiempo de espera de 5 minutos, que puede configurarse hasta 10 minutos. El plan de Azure Functions Premium también puede mitigar este problema y establecer de forma predeterminada los tiempos de espera en 30 minutos con un límite superior ilimitado que se pueda configurar. El tiempo de proceso no es la hora del calendario. Las funciones más avanzadas que usan [Azure durable Functions Framework](https://docs.microsoft.com/azure/azure-functions/durable/durable-functions-overview?tabs=csharp) pueden pausar la ejecución en un curso de varios días. La facturación se basa en el tiempo de ejecución real: cuando la función se activa y reanuda el procesamiento.

Por último, el uso de Azure Functions para las tareas de la aplicación agrega complejidad. Es aconsejable diseñar primero la aplicación con un diseño modular y de acoplamiento flexible. A continuación, identifique si hay beneficios que el servidor no pueda ofrecer y justifique la complejidad adicional.

>[!div class="step-by-step"]
>[Anterior](leverage-containers-orchestrators.md)
>[Siguiente](combine-containers-serverless-approaches.md)
