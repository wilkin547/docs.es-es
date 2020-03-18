---
title: Servicios de streaming frente a campos repetidos - gRPC para desarrolladores de WCF
description: Compare los campos repetidos con los servicios de streaming como formas de pasar colecciones de datos mediante gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 542ebc393f9c9c1ad717d02d01fab33d85c18917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147755"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a>Comparación entre servicios de streaming de gRPC y campos repetidos

Los servicios gRPC proporcionan dos formas de devolver conjuntos de datos o listas de objetos. La especificación de mensaje `repeated` Zonas de búferes de protocolo utiliza la palabra clave para declarar listas o matrices de mensajes dentro de otro mensaje. La especificación de `stream` servicio gRPC utiliza la palabra clave para declarar una conexión persistente de larga ejecución. A través de esa conexión, se envían varios mensajes y se pueden procesar individualmente.

También puede utilizar `stream` la característica para datos temporales de ejecución prolongada, como notificaciones o mensajes de registro. Pero este capítulo considerará su uso para devolver un único conjunto de datos.

El que debe usar depende de factores tales como:

- El tamaño total del conjunto de datos.
- El tiempo que se tardó en crear el conjunto de datos en el extremo del cliente o del servidor.
- Si el consumidor del conjunto de datos puede empezar a actuar en él tan pronto como el primer elemento está disponible o necesita el conjunto de datos completo para hacer algo útil.

## <a name="when-to-use-repeated-fields"></a>Cuándo usar `repeated` campos

Para cualquier conjunto de datos que esté restringido en tamaño y que se pueda generar en su totalidad `repeated` en poco tiempo (por ejemplo, en menos de un segundo), debe usar un campo en un mensaje Protobuf normal. Por ejemplo, en un sistema de comercio electrónico, crear una lista de elementos dentro de un pedido es probablemente rápido y la lista no será muy grande. Devolver un único mensaje `repeated` con un campo es `stream` un orden de magnitud más rápido que usar e incurre en menos sobrecarga de red.

Si el cliente necesita todos los datos antes de empezar a procesarlos y `repeated` el conjunto de datos es lo suficientemente pequeño como para construirlo en memoria, considere la posibilidad de usar un campo. Considérelo incluso si la creación del conjunto de datos en memoria en el servidor es más lenta.

## <a name="when-to-use-stream-methods"></a>Cuándo usar `stream` métodos

Cuando los objetos de mensaje de los conjuntos de datos son potencialmente muy grandes, es mejor transferirlos mediante solicitudes o respuestas de streaming. Es más eficaz construir un objeto grande en la memoria, escribirlo en la red y, a continuación, liberar los recursos. Este enfoque mejorará la escalabilidad de su servicio.

De forma similar, debe enviar conjuntos de datos de tamaño sin restricciones sobre secuencias para evitar quedarse sin memoria mientras se construyen.

Para los conjuntos de datos donde el consumidor puede procesar por separado cada elemento, debe considerar el uso de una secuencia si significa que el progreso se puede indicar al usuario. El uso de una secuencia puede mejorar la capacidad de respuesta de una aplicación, pero debe equilibrarla con el rendimiento general de la aplicación.

Otro escenario donde las secuencias pueden ser útiles es donde se procesa un mensaje en varios servicios. Si cada servicio de una cadena devuelve una secuencia, el servicio de terminal (es decir, el último de la cadena) puede empezar a devolver mensajes. Estos mensajes se pueden procesar y devolver a lo largo de la cadena al solicitante original. El solicitante puede devolver una secuencia o agregar los resultados en un único mensaje de respuesta. Este enfoque se presta bien a patrones como MapReduce.

>[!div class="step-by-step"]
>[Anterior](migrate-duplex-services.md)
>[Siguiente](client-libraries.md)
