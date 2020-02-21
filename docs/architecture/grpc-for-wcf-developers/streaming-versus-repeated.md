---
title: Streaming Services frente a campos repetidos-gRPC para desarrolladores de WCF
description: Compare los campos repetidos con los servicios de streaming como formas de pasar colecciones de datos mediante gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 0e717df57ba2bb52d63a063072d8a45bf0f7e395
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503370"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a>gRPC streaming Services frente a campos repetidos

los servicios de gRPC proporcionan dos maneras de devolver conjuntos de valores o listas de objetos. La especificación de mensajes de búferes de protocolo utiliza la palabra clave `repeated` para declarar listas o matrices de mensajes dentro de otro mensaje. La especificación del servicio gRPC usa la palabra clave `stream` para declarar una conexión persistente de ejecución prolongada. A través de esa conexión, se envían varios mensajes y se pueden procesar de forma individual. 

También puede usar la característica `stream` para datos temporales de ejecución prolongada como notificaciones o mensajes de registro. Pero en este capítulo se considerará su uso para devolver un único conjunto de resultados.

Que debe usar depende de factores como:

- Tamaño total del conjunto de los mismos.
- El tiempo que se tardó en crear el conjunto de valores en el cliente o el servidor.
- Si el consumidor del conjunto de resultados puede empezar a actuar en él tan pronto como el primer elemento está disponible, o necesita el conjunto de resultados completo para hacer algo útil.

## <a name="when-to-use-repeated-fields"></a>Cuándo usar `repeated` campos

Para cualquier conjunto de elementos que esté restringido en tamaño y que se pueda generar en su totalidad en un breve período de tiempo (por ejemplo, en un segundo), debe usar un `repeated` campo en un mensaje protobuf normal. Por ejemplo, en un sistema de comercio electrónico, para crear una lista de elementos dentro de un pedido probablemente sea rápido y la lista no sea muy grande. Devolver un solo mensaje con un campo `repeated` es un orden de magnitud más rápido que el uso de `stream` e incurre en menos sobrecarga de la red.

Si el cliente necesita todos los datos antes de empezar a procesarlo y el conjunto de datos es lo suficientemente pequeño como para construir en memoria, considere la posibilidad de usar un campo de `repeated`. Tenga en cuenta incluso si la creación del conjunto de los conjuntos de copia de la memoria en el servidor es más lenta.

## <a name="when-to-use-stream-methods"></a>Cuándo usar métodos `stream`

Cuando los objetos de mensaje de los conjuntos de valores son potencialmente muy grandes, es mejor transferirlos mediante solicitudes o respuestas de streaming. Es más eficaz construir un objeto grande en la memoria, escribirlo en la red y, a continuación, liberar los recursos. Este enfoque mejorará la escalabilidad del servicio.

Del mismo modo, debe enviar los conjuntos de valores de un tamaño no restringido a través de secuencias para evitar quedarse sin memoria mientras los construye.

En el caso de los conjuntos de usuarios en los que el consumidor puede procesar por separado cada elemento, debería considerar la posibilidad de usar un flujo si significa que se puede indicar el progreso al usuario. El uso de una secuencia puede mejorar la capacidad de respuesta de una aplicación, pero debe equilibrarla con el rendimiento general de la aplicación.

Otro escenario en el que los flujos pueden ser útiles es el lugar en el que se procesa un mensaje en varios servicios. Si cada servicio de una cadena devuelve una secuencia, el servicio de Terminal Server (es decir, el último de la cadena) puede empezar a devolver los mensajes. Estos mensajes se pueden procesar y devolver a lo largo de la cadena al solicitante original. El solicitante puede devolver una secuencia o agregar los resultados en un único mensaje de respuesta. Este enfoque se presta bien a patrones como MapReduce.

>[!div class="step-by-step"]
>[Anterior](migrate-duplex-services.md)
>[Siguiente](client-libraries.md)
