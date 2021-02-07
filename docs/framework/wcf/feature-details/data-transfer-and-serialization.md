---
description: 'Más información acerca de: Transferencia de datos y serialización'
title: Transferencia y serialización de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 50e5068efc10d706fb9ce2634998408e48037ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756570"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="8c452-103">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="8c452-103">Data Transfer and Serialization</span></span>

<span data-ttu-id="8c452-104">En un sistema conectado, los servicios y clientes dependen del intercambio de datos para realizar cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="8c452-104">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="8c452-105">Como desarrollador de un servicio o cliente, también debe comprender cómo el Windows Communication Foundation (WCF) controla los datos y la serialización de datos con el fin de crear aplicaciones que sean eficientes y fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="8c452-105">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c452-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8c452-106">In This Section</span></span>  

 [<span data-ttu-id="8c452-107">Especificación de transferencia de datos en contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="8c452-107">Specifying Data Transfer in Service Contracts</span></span>](specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="8c452-108">Describe los conceptos básicos de la transferencia de datos en los servicios.</span><span class="sxs-lookup"><span data-stu-id="8c452-108">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="8c452-109">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="8c452-109">Using Data Contracts</span></span>](using-data-contracts.md)  
 <span data-ttu-id="8c452-110">Describe qué son los contratos de datos y cómo crearlos y utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="8c452-110">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="8c452-111">Serializador de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="8c452-111">Data Contract Serializer</span></span>](data-contract-serializer.md)  
 <span data-ttu-id="8c452-112">Describe cómo lograr la serialización de los datos con la clase <xref:System.Runtime.Serialization.DataContractSerializer> o cualquier extensión de la clase <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8c452-112">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="8c452-113">Utilización de la clase XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="8c452-113">Using the XmlSerializer Class</span></span>](using-the-xmlserializer-class.md)  
 <span data-ttu-id="8c452-114">Describe cómo y por qué utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>, una alternativa a la clase <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8c452-114">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="8c452-115">Usar contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="8c452-115">Using Message Contracts</span></span>](using-message-contracts.md)  
 <span data-ttu-id="8c452-116">Describe cómo permiten los contratos de mensajes un control estrecho sobre los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="8c452-116">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="8c452-117">Uso de la clase de mensajes</span><span class="sxs-lookup"><span data-stu-id="8c452-117">Using the Message Class</span></span>](using-the-message-class.md)  
 <span data-ttu-id="8c452-118">Describe cómo utilizar las características de la clase Message.</span><span class="sxs-lookup"><span data-stu-id="8c452-118">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="8c452-119">Filtros</span><span class="sxs-lookup"><span data-stu-id="8c452-119">Filtering</span></span>](filtering.md)  
 <span data-ttu-id="8c452-120">Describe el filtrado, que permite el preprocesado de un mensaje en función de varios criterios.</span><span class="sxs-lookup"><span data-stu-id="8c452-120">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="8c452-121">Datos de gran tamaño y secuencias</span><span class="sxs-lookup"><span data-stu-id="8c452-121">Large Data and Streaming</span></span>](large-data-and-streaming.md)  
 <span data-ttu-id="8c452-122">Describe cómo enviar un bloque grande de datos, como, por ejemplo, un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="8c452-122">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="8c452-123">Consideraciones de seguridad para datos</span><span class="sxs-lookup"><span data-stu-id="8c452-123">Security Considerations for Data</span></span>](security-considerations-for-data.md)  
 <span data-ttu-id="8c452-124">Describe los elementos que se han de tener en cuenta a la hora de programar la transferencia y serialización de datos.</span><span class="sxs-lookup"><span data-stu-id="8c452-124">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="8c452-125">Información general sobre la arquitectura de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="8c452-125">Data Transfer Architectural Overview</span></span>](data-transfer-architectural-overview.md)  
 <span data-ttu-id="8c452-126">Describe una vista del diseño general de la transferencia de datos en WCF.</span><span class="sxs-lookup"><span data-stu-id="8c452-126">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8c452-127">Referencia</span><span class="sxs-lookup"><span data-stu-id="8c452-127">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="8c452-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8c452-128">Related Sections</span></span>  

 [<span data-ttu-id="8c452-129">Extensión de codificadores y serializadores</span><span class="sxs-lookup"><span data-stu-id="8c452-129">Extending Encoders and Serializers</span></span>](../extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c452-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c452-130">See also</span></span>

- [<span data-ttu-id="8c452-131">Procedimientos recomendados: Versiones de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="8c452-131">Best Practices: Data Contract Versioning</span></span>](../best-practices-data-contract-versioning.md)
- [<span data-ttu-id="8c452-132">Control de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="8c452-132">Service Versioning</span></span>](../service-versioning.md)
