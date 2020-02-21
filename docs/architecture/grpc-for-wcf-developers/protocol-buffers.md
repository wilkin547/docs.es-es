---
title: 'Búferes de protocolo: gRPC para desarrolladores de WCF'
description: Introducción al formato de conexión de búferes de protocolo usado para las redes gRPCles.
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503457"
---
# <a name="protocol-buffers"></a>Búferes de protocolo

los servicios de gRPC envían y reciben datos como *mensajes de búfer de protocolo (protobuf)* , similares a los contratos de datos en Windows Communication Foundation (WCF). Protobuf es una manera eficaz de serializar datos estructurados para que los equipos lean y escriban, sin la sobrecarga que generan los formatos que pueden ser legibles como XML o JSON.

En este capítulo se describe cómo funciona protobuf y cómo definir sus propios mensajes protobuf.

## <a name="how-protobuf-works"></a>Cómo funciona protobuf

La mayoría de las técnicas de serialización de objetos .NET, incluidos los contratos de datos de WCF, funcionan mediante la reflexión para analizar la estructura del objeto en tiempo de ejecución. Por el contrario, la mayoría de las bibliotecas de protobuf requieren que defina la estructura por adelantado mediante un lenguaje dedicado (*lenguaje de búfer de protocolo*) en un archivo de `.proto`. Después, un compilador usa este archivo para generar código para cualquiera de las plataformas admitidas. Entre las plataformas admitidas se incluyen .NET,C++Java, C/, JavaScript y muchas más. 

Google mantiene el compilador protobuf, `protoc`, aunque hay implementaciones alternativas disponibles. El código generado es eficaz y está optimizado para la serialización y deserialización rápida de los datos.

El formato de protobuf es una codificación binaria. Usa algunos trucos inteligentes para minimizar el número de bytes que se usan para representar mensajes. No es necesario conocer el formato de codificación binaria para usar protobuf. Pero si le interesa, puede obtener más información al respecto en [el sitio web de búferes de protocolo](https://developers.google.com/protocol-buffers/docs/encoding).

>[!div class="step-by-step"]
>[Anterior](why-grpc.md)
>[Siguiente](protobuf-messages.md)
