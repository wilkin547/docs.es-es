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
# <a name="protocol-buffers"></a><span data-ttu-id="a64b5-103">Búferes de protocolo</span><span class="sxs-lookup"><span data-stu-id="a64b5-103">Protocol buffers</span></span>

<span data-ttu-id="a64b5-104">los servicios de gRPC envían y reciben datos como *mensajes de búfer de protocolo (protobuf)* , similares a los contratos de datos de WCF.</span><span class="sxs-lookup"><span data-stu-id="a64b5-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="a64b5-105">Protobuf es una manera eficaz de serializar datos estructurados para que los equipos lean y escriban, sin la sobrecarga que generan los formatos que pueden ser legibles como XML o JSON.</span><span class="sxs-lookup"><span data-stu-id="a64b5-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="a64b5-106">En este capítulo se describe cómo funciona protobuf y cómo definir sus propios mensajes protobuf.</span><span class="sxs-lookup"><span data-stu-id="a64b5-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="a64b5-107">Cómo funciona protobuf</span><span class="sxs-lookup"><span data-stu-id="a64b5-107">How Protobuf works</span></span>

<span data-ttu-id="a64b5-108">La mayoría de las técnicas de serialización de objetos .NET, incluidos los contratos de datos de WCF, funcionan mediante la reflexión para analizar la estructura del objeto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a64b5-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="a64b5-109">Por el contrario, la mayoría de las bibliotecas de protobuf requieren que defina la estructura por adelantado mediante un lenguaje dedicado (*lenguaje de búfer de protocolo*) en un archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="a64b5-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="a64b5-110">Después, un compilador usa este archivo para generar código para cualquiera de las plataformas admitidas, como .NET, Java,C++C/, JavaScript y muchos más.</span><span class="sxs-lookup"><span data-stu-id="a64b5-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="a64b5-111">Google mantiene el compilador protobuf, `protoc`, aunque hay implementaciones alternativas disponibles.</span><span class="sxs-lookup"><span data-stu-id="a64b5-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="a64b5-112">El código generado es eficaz y está optimizado para la serialización y deserialización rápida de los datos.</span><span class="sxs-lookup"><span data-stu-id="a64b5-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="a64b5-113">El propio formato de conexión de protobuf es una codificación binaria, que usa algunos trucos inteligentes para minimizar el número de bytes que se usan para representar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a64b5-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="a64b5-114">No es necesario conocer el formato de codificación binaria para usar protobuf, pero si le interesa, puede obtener más información en [el sitio web de búferes de protocolo](https://developers.google.com/protocol-buffers/docs/encoding).</span><span class="sxs-lookup"><span data-stu-id="a64b5-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a64b5-115">[Anterior](why-grpc.md)
>[Siguiente](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="a64b5-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
