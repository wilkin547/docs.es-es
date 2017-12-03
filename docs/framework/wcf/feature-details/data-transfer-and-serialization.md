---
title: "Transferencia y serialización de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data serialization [WCF]
- data transfer [WCF]
ms.assetid: 0f03c635-f3e7-4c5c-9463-3cb0135e221e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 29ca4041e24a99546dfb665b0ce9e695732442d4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="data-transfer-and-serialization"></a><span data-ttu-id="4516a-102">Transferencia y serialización de datos</span><span class="sxs-lookup"><span data-stu-id="4516a-102">Data Transfer and Serialization</span></span>
<span data-ttu-id="4516a-103">En un sistema conectado, los servicios y clientes dependen del intercambio de datos para realizar cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="4516a-103">In a connected system, services and clients depend on the exchange of data to accomplish any task.</span></span> <span data-ttu-id="4516a-104">Como programador de un servicio o cliente, también debe entender cómo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] administra los datos y la serialización de los datos para crear aplicaciones eficaces y fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="4516a-104">As a developer of a service or client, you must also understand how [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] handles data and data serialization in order to create applications that are efficient and easy to maintain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4516a-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4516a-105">In This Section</span></span>  
 [<span data-ttu-id="4516a-106">Specifying Data Transfer in Service Contracts</span><span class="sxs-lookup"><span data-stu-id="4516a-106">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 <span data-ttu-id="4516a-107">Describe los conceptos básicos de la transferencia de datos en los servicios.</span><span class="sxs-lookup"><span data-stu-id="4516a-107">Describes the basic concepts of data transfer in services.</span></span>  
  
 [<span data-ttu-id="4516a-108">Usar contratos de datos</span><span class="sxs-lookup"><span data-stu-id="4516a-108">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 <span data-ttu-id="4516a-109">Describe qué son los contratos de datos y cómo crearlos y utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="4516a-109">Describes what data contracts are and how to create and use them.</span></span>  
  
 [<span data-ttu-id="4516a-110">Serializador de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="4516a-110">Data Contract Serializer</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-serializer.md)  
 <span data-ttu-id="4516a-111">Describe cómo lograr la serialización de los datos con la clase <xref:System.Runtime.Serialization.DataContractSerializer> o cualquier extensión de la clase <xref:System.Runtime.Serialization.XmlObjectSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4516a-111">Describes how to accomplish serialization of data with the <xref:System.Runtime.Serialization.DataContractSerializer> class or any extension of the <xref:System.Runtime.Serialization.XmlObjectSerializer> class.</span></span>  
  
 [<span data-ttu-id="4516a-112">Mediante la clase XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="4516a-112">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)  
 <span data-ttu-id="4516a-113">Describe cómo y por qué utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>, una alternativa a la clase <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4516a-113">Describes how and why to use the <xref:System.Xml.Serialization.XmlSerializer> class, an alternative to the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 [<span data-ttu-id="4516a-114">Usar contratos de mensaje</span><span class="sxs-lookup"><span data-stu-id="4516a-114">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)  
 <span data-ttu-id="4516a-115">Describe cómo permiten los contratos de mensajes un control estrecho sobre los mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="4516a-115">Describes how message contracts allow fine control over SOAP messages.</span></span>  
  
 [<span data-ttu-id="4516a-116">Uso de la clase de mensaje</span><span class="sxs-lookup"><span data-stu-id="4516a-116">Using the Message Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)  
 <span data-ttu-id="4516a-117">Describe cómo utilizar las características de la clase Message.</span><span class="sxs-lookup"><span data-stu-id="4516a-117">Describes how to use Message class features.</span></span>  
  
 [<span data-ttu-id="4516a-118">Filtrado</span><span class="sxs-lookup"><span data-stu-id="4516a-118">Filtering</span></span>](../../../../docs/framework/wcf/feature-details/filtering.md)  
 <span data-ttu-id="4516a-119">Describe el filtrado, que permite el preprocesado de un mensaje en función de varios criterios.</span><span class="sxs-lookup"><span data-stu-id="4516a-119">Describes filtering, which enables pre-processing of a message based on various criteria.</span></span>  
  
 [<span data-ttu-id="4516a-120">Datos de gran tamaño y la transmisión por secuencias</span><span class="sxs-lookup"><span data-stu-id="4516a-120">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)  
 <span data-ttu-id="4516a-121">Describe cómo enviar un bloque grande de datos, como, por ejemplo, un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="4516a-121">Describes how to send a large block of data, such as a binary file.</span></span>  
  
 [<span data-ttu-id="4516a-122">Consideraciones de seguridad de datos</span><span class="sxs-lookup"><span data-stu-id="4516a-122">Security Considerations for Data</span></span>](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 <span data-ttu-id="4516a-123">Describe los elementos que se han de tener en cuenta a la hora de programar la transferencia y serialización de datos.</span><span class="sxs-lookup"><span data-stu-id="4516a-123">Describes items to be aware of when programming data transfer and serialization.</span></span>  
  
 [<span data-ttu-id="4516a-124">Introducción a la arquitectura de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="4516a-124">Data Transfer Architectural Overview</span></span>](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md)  
 <span data-ttu-id="4516a-125">Describe una vista del diseño general de la transferencia de datos en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4516a-125">Describes a view of the overall design of data transfer in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4516a-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="4516a-126">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
  
 <xref:System.Xml.Serialization.XmlSerializer>  
  
 <xref:System.Runtime.Serialization>  
  
 <xref:System.Xml.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="4516a-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4516a-127">Related Sections</span></span>  
 [<span data-ttu-id="4516a-128">Extensión de codificadores y serializadores</span><span class="sxs-lookup"><span data-stu-id="4516a-128">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
  
## <a name="see-also"></a><span data-ttu-id="4516a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4516a-129">See Also</span></span>  
 [<span data-ttu-id="4516a-130">Procedimientos recomendados: creación de versiones de contratos de datos</span><span class="sxs-lookup"><span data-stu-id="4516a-130">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="4516a-131">Control de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="4516a-131">Service Versioning</span></span>](../../../../docs/framework/wcf/service-versioning.md)
