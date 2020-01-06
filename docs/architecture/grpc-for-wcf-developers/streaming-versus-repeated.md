---
title: Streaming Services frente a campos repetidos-gRPC para desarrolladores de WCF
description: Compare los campos repetidos con los servicios de streaming como formas de pasar colecciones de datos con gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 46586ab08df6b136cdafb990ce8be75435a6bf6c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337867"
---
# <a name="grpc-streaming-services-versus-repeated-fields"></a>gRPC streaming Services frente a campos repetidos

los servicios de gRPC proporcionan dos maneras de devolver conjuntos de valores o listas de objetos. La especificación de mensajes de búferes de protocolo utiliza la palabra clave `repeated` para declarar listas o matrices de mensajes dentro de otro mensaje. La especificación del servicio gRPC usa la palabra clave `stream` para declarar una conexión persistente de ejecución prolongada a través de la cual se envían varios mensajes y se puede procesar de forma individual. La característica `stream` también se puede usar para datos temporales de ejecución prolongada como notificaciones o mensajes de registro, pero en este capítulo se considerará su uso para devolver un único conjunto de datos.

El uso de depende de varios factores, como el tamaño total del conjunto de elementos, el tiempo que se tarda en crear el conjunto de valores en el cliente o en el extremo del servidor, y si el consumidor del conjunto de elementos puede empezar a actuar en él en cuanto el primer elemento esté disponible. , o necesita el conjunto de resultados completo para hacer algo útil.

## <a name="when-to-use-repeated-fields"></a>Cuándo usar `repeated` campos

Para cualquier conjunto de elementos que esté restringido en tamaño y que se pueda generar en su totalidad en un breve período de tiempo (por ejemplo, en un segundo), debe usar un `repeated` campo en un mensaje protobuf normal. Por ejemplo, en un sistema de comercio electrónico, para crear una lista de elementos dentro de un pedido probablemente sea rápido y la lista no sea muy grande. Devolver un solo mensaje con un campo de `repeated` es un orden de magnitud más rápido que el uso de un `stream` e incurre en menos sobrecarga de la red.

Si el cliente necesita todos los datos antes de empezar a procesarlo y el conjunto de datos es lo suficientemente pequeño como para construir en la memoria, considere la posibilidad de usar un campo `repeated` incluso si la creación real del conjunto de datos en memoria en el servidor es más lenta.

## <a name="when-to-use-stream-methods"></a>Cuándo usar métodos `stream`

Los conjuntos de valores en los que los objetos de mensaje son potencialmente grandes se transfieren mejor mediante solicitudes o respuestas de streaming. Es más eficaz construir un objeto grande en la memoria, escribirlo en la red y, a continuación, liberar los recursos. Este enfoque mejorará la escalabilidad del servicio.

Del mismo modo, los conjuntos de valores sin restricciones se deben enviar a través de secuencias para evitar quedarse sin memoria mientras se crean.

En el caso de los conjuntos de usuarios en los que el consumidor puede procesar por separado cada elemento individual, debe considerar la posibilidad de usar un flujo si esto significa que se puede indicar el progreso al usuario final. Esto podría mejorar la capacidad de respuesta aparente de una aplicación, aunque debe equilibrarse con el rendimiento general de la aplicación.

Otro escenario en el que los flujos pueden ser útiles es el lugar en el que se procesa un mensaje en varios servicios. Si cada servicio de una cadena devuelve una secuencia, el servicio de Terminal Server (es decir, el último de la cadena) puede empezar a devolver mensajes que se pueden procesar y devolver a lo largo de la cadena al solicitante original, que puede devolver una secuencia o agregar la da como resultado un único mensaje de respuesta. Este enfoque se presta bien a patrones como asignación y reducción.

>[!div class="step-by-step"]
>[Anterior](migrate-duplex-services.md)
>[Siguiente](client-libraries.md)
