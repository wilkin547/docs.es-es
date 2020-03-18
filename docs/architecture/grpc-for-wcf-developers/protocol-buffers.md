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
# <a name="protocol-buffers"></a><span data-ttu-id="c97f5-103">Búferes de protocolo</span><span class="sxs-lookup"><span data-stu-id="c97f5-103">Protocol buffers</span></span>

<span data-ttu-id="c97f5-104">Los servicios gRPC envían y reciben datos como mensajes de búfer de protocolo *(Protobuf),* similar a los contratos de datos en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c97f5-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="c97f5-105">Protobuf es una forma eficaz de serializar datos estructurados para que las máquinas lean y escriban, sin la sobrecarga en la que incurren formatos legibles como XML o JSON.</span><span class="sxs-lookup"><span data-stu-id="c97f5-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="c97f5-106">En este capítulo se explica cómo funciona Protobuf y cómo definir sus propios mensajes de Protobuf.</span><span class="sxs-lookup"><span data-stu-id="c97f5-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="c97f5-107">Cómo funciona Protobuf</span><span class="sxs-lookup"><span data-stu-id="c97f5-107">How Protobuf works</span></span>

<span data-ttu-id="c97f5-108">La mayoría de las técnicas de serialización de objetos .NET, incluidos los contratos de datos de WCF, funcionan mediante la reflexión para analizar la estructura de objetos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c97f5-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="c97f5-109">Por el contrario, la mayoría de las bibliotecas de Protobuf requieren que defina `.proto` la estructura por adelantado mediante un lenguaje dedicado *(Lenguaje*de búfer de protocolo) en un archivo.</span><span class="sxs-lookup"><span data-stu-id="c97f5-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="c97f5-110">A continuación, un compilador usa este archivo para generar código para cualquiera de las plataformas admitidas.</span><span class="sxs-lookup"><span data-stu-id="c97f5-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="c97f5-111">Las plataformas compatibles incluyen .NET, Java, C/C++, JavaScript y muchos más.</span><span class="sxs-lookup"><span data-stu-id="c97f5-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span>

<span data-ttu-id="c97f5-112">El compilador Protobuf, `protoc`, es mantenido por Google, aunque hay implementaciones alternativas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c97f5-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="c97f5-113">El código generado es eficaz y optimizado para la serialización y deserialización rápida de datos.</span><span class="sxs-lookup"><span data-stu-id="c97f5-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="c97f5-114">El formato de cable Protobuf es una codificación binaria.</span><span class="sxs-lookup"><span data-stu-id="c97f5-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="c97f5-115">Utiliza algunos trucos inteligentes para minimizar el número de bytes utilizados para representar mensajes.</span><span class="sxs-lookup"><span data-stu-id="c97f5-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="c97f5-116">El conocimiento del formato de codificación binaria no es necesario para utilizar Protobuf.</span><span class="sxs-lookup"><span data-stu-id="c97f5-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="c97f5-117">Pero si está interesado, puede obtener más información al respecto en el sitio web de [búferes](https://developers.google.com/protocol-buffers/docs/encoding)de protocolo .</span><span class="sxs-lookup"><span data-stu-id="c97f5-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c97f5-118">[Anterior](why-grpc.md)
>[Siguiente](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c97f5-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
