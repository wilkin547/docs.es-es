---
title: 'Cómo: Fragmentar datos serializados'
description: Puede fragmentar los datos para evitar problemas con grandes conjuntos de datos. Implemente la interfaz IXmlSerializable para controlar la serialización y la deserialización.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- chunking serialized data
- data chunking
- binary serialization, chunking data
- large data set chunking
- serialization, chunking data
- serialization, examples
- binary serialization, examples
ms.assetid: 22f1b818-7e0d-428a-8680-f17d6ebdd185
ms.openlocfilehash: 860fdcae0d1937f53ee964d9d4631ec812b3d379
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379140"
---
# <a name="how-to-chunk-serialized-data"></a><span data-ttu-id="d4e6e-104">Cómo: Fragmentar datos serializados</span><span class="sxs-lookup"><span data-stu-id="d4e6e-104">How to: chunk serialized data</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="d4e6e-105">Dos problemas que se producen al enviar los conjuntos de datos grandes en mensajes del Servicio Web son:</span><span class="sxs-lookup"><span data-stu-id="d4e6e-105">Two issues that occur when sending large data sets in Web service messages are:</span></span>  
  
1. <span data-ttu-id="d4e6e-106">Un espacio de trabajo grande (memoria) debido al almacenamiento en búfer por el motor de la serialización.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-106">A large working set (memory) due to buffering by the serialization engine.</span></span>  
  
2. <span data-ttu-id="d4e6e-107">Consumo de ancho de banda inmoderado debido a 33 por ciento inflación después de la codificación de Base64.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-107">Inordinate bandwidth consumption due to 33 percent inflation after Base64 encoding.</span></span>  
  
 <span data-ttu-id="d4e6e-108">Para resolver estos problemas, implemente la interfaz <xref:System.Xml.Serialization.IXmlSerializable> para controlar la serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-108">To solve these problems, implement the <xref:System.Xml.Serialization.IXmlSerializable> interface to control the serialization and deserialization.</span></span> <span data-ttu-id="d4e6e-109">Específicamente, implemente <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> y los métodos <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> al fragmento los datos.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-109">Specifically, implement the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> and <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> methods to chunk the data.</span></span>  
  
### <a name="to-implement-server-side-chunking"></a><span data-ttu-id="d4e6e-110">Para implementar la fragmentación del lado del servidor</span><span class="sxs-lookup"><span data-stu-id="d4e6e-110">To implement server-side chunking</span></span>  
  
1. <span data-ttu-id="d4e6e-111">En el equipo del servidor, el método web se debe apagar del almacenado en búfer de ASP.NET y devolver un tipo que implementa <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-111">On the server machine, the Web method must turn off ASP.NET buffering and return a type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span>  
  
2. <span data-ttu-id="d4e6e-112">El tipo que implementa  <xref:System.Xml.Serialization.IXmlSerializable> fragmenta los datos en el método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-112">The type that implements <xref:System.Xml.Serialization.IXmlSerializable> chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
### <a name="to-implement-client-side-processing"></a><span data-ttu-id="d4e6e-113">Para implementar el procesamiento del lado cliente</span><span class="sxs-lookup"><span data-stu-id="d4e6e-113">To implement client-side processing</span></span>  
  
1. <span data-ttu-id="d4e6e-114">Modifique el método Web en el proxy de cliente para devolver el tipo que implementa <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-114">Alter the Web method on the client proxy to return the type that implements <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="d4e6e-115">Puede usar una <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> para realizar esta acción automáticamente, pero no se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-115">You can use a <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension> to do this automatically, but this isn't shown here.</span></span>  
  
2. <span data-ttu-id="d4e6e-116">Implemente el método <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> para leer el flujo de datos fragmentado y escribir los bytes en el disco.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-116">Implement the <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> method to read the chunked data stream and write the bytes to disk.</span></span> <span data-ttu-id="d4e6e-117">Esta implementación también genera eventos de progreso que pueden ser utilizados por un control gráfico, como una barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-117">This implementation also raises progress events that can be used by a graphic control, such as a progress bar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e6e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4e6e-118">Example</span></span>  
<span data-ttu-id="d4e6e-119">El ejemplo de código siguiente muestra el método Web en el cliente que desactiva el almacenado en búfer de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-119">The following code example shows the Web method on the client that turns off ASP.NET buffering.</span></span> <span data-ttu-id="d4e6e-120">También muestra la implementación del lado cliente de la interfaz <xref:System.Xml.Serialization.IXmlSerializable> que fragmenta los datos en el método <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-120">It also shows the client-side implementation of the <xref:System.Xml.Serialization.IXmlSerializable> interface that chunks the data in the <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> method.</span></span>  
  
[!code-csharp[HowToChunkSerializedData#1](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#1)]
[!code-vb[HowToChunkSerializedData#1](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#1)]  
[!code-csharp[HowToChunkSerializedData#2](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#2)]
[!code-vb[HowToChunkSerializedData#2](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#2)]  
[!code-csharp[HowToChunkSerializedData#3](../../../samples/snippets/csharp/VS_Snippets_Remoting/HowToChunkSerializedData/CS/SerializationChunk.cs#3)]
[!code-vb[HowToChunkSerializedData#3](../../../samples/snippets/visualbasic/VS_Snippets_Remoting/HowToChunkSerializedData/VB/SerializationChunk.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d4e6e-121">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="d4e6e-121">Compiling the code</span></span>  
  
- <span data-ttu-id="d4e6e-122">El código utiliza los siguientes espacios de nombres: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, y <xref:System.Xml.Schema>.</span><span class="sxs-lookup"><span data-stu-id="d4e6e-122">The code uses the following namespaces: <xref:System>, <xref:System.Runtime.Serialization>, <xref:System.Web.Services>, <xref:System.Web.Services.Protocols>, <xref:System.Xml>, <xref:System.Xml.Serialization>, and <xref:System.Xml.Schema>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4e6e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4e6e-123">See also</span></span>

- [<span data-ttu-id="d4e6e-124">Serialización personalizada</span><span class="sxs-lookup"><span data-stu-id="d4e6e-124">Custom Serialization</span></span>](custom-serialization.md)
