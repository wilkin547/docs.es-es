---
title: Transferencia y serialización de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
ms.openlocfilehash: 5192030fa2eda45431dd8a3765603d3081b93fa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595323"
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="24048-102">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="24048-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="24048-103">En un sistema conectado, los servicios y clientes dependen del intercambio de datos para realizar cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="24048-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="24048-104">Como desarrollador de un servicio o cliente, también debe entender cómo Windows Communication Foundation (WCF) controla la serialización de datos y datos con el fin de crear aplicaciones eficaces y fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="24048-104">As a developer of a service or client, you must also understand how Windows Communication Foundation (WCF) handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="24048-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="24048-105">In This Section</span></span>  
 [<span data-ttu-id="24048-106">Definición de transferencias de datos en contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="24048-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="24048-107">Describe los conceptos básicos de la transferencia de datos en los servicios.</span><span class="sxs-lookup"><span data-stu-id="24048-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="24048-108">Utilización de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="24048-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="24048-109">Describe qué son los contratos de datos y cómo crearlos y utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="24048-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="24048-110">Serializador de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="24048-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="24048-111">Describe cómo lograr la serialización de los datos con la clase <xref:System.Runtime.Serialization.DataContractSerializer> o cualquier extensión de la clase <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="24048-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="24048-112">Utilización de la clase XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="24048-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="24048-113">Describe cómo y por qué utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>, una alternativa a la clase <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="24048-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="24048-114">Uso de contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="24048-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="24048-115">Describe cómo permiten los contratos de mensajes un control estrecho sobre los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="24048-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="24048-116">Uso de la clase de mensajes</span><span class="sxs-lookup"><span data-stu-id="24048-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="24048-117">Describe cómo utilizar las características de la clase Message.</span><span class="sxs-lookup"><span data-stu-id="24048-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="24048-118">Filtrado</span><span class="sxs-lookup"><span data-stu-id="24048-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="24048-119">Describe el filtrado, que permite el preprocesado de un mensaje en función de varios criterios.</span><span class="sxs-lookup"><span data-stu-id="24048-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="24048-120">Grandes datos y streaming</span><span class="sxs-lookup"><span data-stu-id="24048-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="24048-121">Describe cómo enviar un bloque grande de datos, como, por ejemplo, un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="24048-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="24048-122">Consideraciones de seguridad para datos</span><span class="sxs-lookup"><span data-stu-id="24048-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="24048-123">Describe los elementos que se han de tener en cuenta a la hora de programar la transferencia y serialización de datos.</span><span class="sxs-lookup"><span data-stu-id="24048-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="24048-124">Información general sobre la arquitectura de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="24048-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="24048-125">Describe una vista del diseño general de transferencia de datos de WCF.</span><span class="sxs-lookup"><span data-stu-id="24048-125">Describes a view of the overall design of data transfer in WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="24048-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="24048-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="24048-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="24048-127">Related Sections</span></span>  
 [<span data-ttu-id="24048-128">Extensión de codificadores y serializadores</span><span class="sxs-lookup"><span data-stu-id="24048-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="24048-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="24048-129">See also</span></span>
- [<span data-ttu-id="24048-130">Procedimientos recomendados: Versiones de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="24048-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
- [<span data-ttu-id="24048-131">Control de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="24048-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
