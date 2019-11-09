---
title: 'Búferes de protocolo: gRPC para desarrolladores de WCF'
description: Introducción al formato de conexión de búferes de protocolo usado para las redes gRPCles.
author: markrendle
ms.date: 09/09/2019
ms.openlocfilehash: 6b47c7f3576134d8ee44f79e329cc4879661e6c3
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841388"
---
# <a name="protocol-buffers"></a>Búferes de protocolo

los servicios de gRPC envían y reciben datos como *mensajes de búfer de protocolo (protobuf)* , similares a los contratos de datos de WCF. Protobuf es una manera eficaz de serializar datos estructurados para que los equipos lean y escriban, sin la sobrecarga que generan los formatos que pueden ser legibles como XML o JSON.

En este capítulo se describe cómo funciona protobuf y cómo definir sus propios mensajes protobuf.

## <a name="how-protobuf-works"></a>Cómo funciona protobuf

La mayoría de las técnicas de serialización de objetos .NET, incluidos los contratos de datos de WCF, funcionan mediante la reflexión para analizar la estructura del objeto en tiempo de ejecución. Por el contrario, la mayoría de las bibliotecas de protobuf requieren que defina la estructura por adelantado mediante un lenguaje dedicado (*lenguaje de búfer de protocolo*) en un archivo de `.proto`. Después, un compilador usa este archivo para generar código para cualquiera de las plataformas admitidas, como .NET, Java,C++C/, JavaScript y muchos más. Google mantiene el compilador protobuf, `protoc`, aunque hay implementaciones alternativas disponibles. El código generado es eficaz y está optimizado para la serialización y deserialización rápida de los datos.

El propio formato de conexión de protobuf es una codificación binaria, que usa algunos trucos inteligentes para minimizar el número de bytes que se usan para representar mensajes. No es necesario conocer el formato de codificación binaria para usar protobuf, pero si le interesa, puede obtener más información en [el sitio web de búferes de protocolo](https://developers.google.com/protocol-buffers/docs/encoding).

>[!div class="step-by-step"]
>[Anterior](why-grpc.md)
>[Siguiente](protobuf-messages.md)
