---
title: Búferes de protocolo - gRPC para desarrolladores de WCF
description: Introducción al formato de cable de búferes de protocolo utilizado para las redes gRPC.
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147937"
---
# <a name="protocol-buffers"></a>Búferes de protocolo

Los servicios gRPC envían y reciben datos como mensajes de búfer de protocolo *(Protobuf),* similar a los contratos de datos en Windows Communication Foundation (WCF). Protobuf es una forma eficaz de serializar datos estructurados para que las máquinas lean y escriban, sin la sobrecarga en la que incurren formatos legibles como XML o JSON.

En este capítulo se explica cómo funciona Protobuf y cómo definir sus propios mensajes de Protobuf.

## <a name="how-protobuf-works"></a>Cómo funciona Protobuf

La mayoría de las técnicas de serialización de objetos .NET, incluidos los contratos de datos de WCF, funcionan mediante la reflexión para analizar la estructura de objetos en tiempo de ejecución. Por el contrario, la mayoría de las bibliotecas de Protobuf requieren que defina `.proto` la estructura por adelantado mediante un lenguaje dedicado *(Lenguaje*de búfer de protocolo) en un archivo. A continuación, un compilador usa este archivo para generar código para cualquiera de las plataformas admitidas. Las plataformas compatibles incluyen .NET, Java, C/C++, JavaScript y muchos más.

El compilador Protobuf, `protoc`, es mantenido por Google, aunque hay implementaciones alternativas disponibles. El código generado es eficaz y optimizado para la serialización y deserialización rápida de datos.

El formato de cable Protobuf es una codificación binaria. Utiliza algunos trucos inteligentes para minimizar el número de bytes utilizados para representar mensajes. El conocimiento del formato de codificación binaria no es necesario para utilizar Protobuf. Pero si está interesado, puede obtener más información al respecto en el sitio web de [búferes](https://developers.google.com/protocol-buffers/docs/encoding)de protocolo .

>[!div class="step-by-step"]
>[Anterior](why-grpc.md)
>[Siguiente](protobuf-messages.md)
