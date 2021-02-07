---
description: 'Más información acerca de: enlaces personalizados'
title: Enlaces personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: ced0f9ada7238b43216a246d75dd391aa6eb3f2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99735353"
---
# <a name="custom-bindings"></a><span data-ttu-id="73b5d-103">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="73b5d-103">Custom Bindings</span></span>

<span data-ttu-id="73b5d-104">Puede usar la clase <xref:System.ServiceModel.Channels.CustomBinding> cuando uno de los enlaces proporcionados por el sistema no cumple los requisitos de su servicio.</span><span class="sxs-lookup"><span data-stu-id="73b5d-104">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="73b5d-105">Todos los enlaces se construyen a partir de un conjunto ordenado de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="73b5d-105">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="73b5d-106">Los enlaces personalizados pueden crearse a partir de un conjunto de elementos de enlace proporcionado por el sistema o incluir elementos de enlace personalizado definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="73b5d-106">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="73b5d-107">Puede utilizar elementos de enlaces personalizados, por ejemplo, para habilitar el uso de nuevos transportes o codificadores en un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="73b5d-107">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="73b5d-108">Para obtener ejemplos prácticos, vea [ejemplos de enlace personalizado](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="73b5d-108">For working examples, see [Custom Binding Samples](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span></span> <span data-ttu-id="73b5d-109">Para obtener más información, vea [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="73b5d-109">For more information, see [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>

## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="73b5d-110">Construcción de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="73b5d-110">Construction of a Custom Binding</span></span>

<span data-ttu-id="73b5d-111">Un enlace personalizado se construye utilizando el constructor <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:</span><span class="sxs-lookup"><span data-stu-id="73b5d-111">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="73b5d-112">En la parte superior hay una clase <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="73b5d-112">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>

- <span data-ttu-id="73b5d-113">A continuación, hay una clase <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y mecanismos de ordenación, como se define en la especificación WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="73b5d-113">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="73b5d-114">Una sesión puede cruzar SOAP y transportar intermediarios.</span><span class="sxs-lookup"><span data-stu-id="73b5d-114">A session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="73b5d-115">A continuación, hay una clase <xref:System.ServiceModel.Channels.SecurityBindingElement> opcional que proporciona características de seguridad, como autorización, autenticación, protección y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="73b5d-115">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>

- <span data-ttu-id="73b5d-116">A continuación, hay una clase <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> opcional que proporciona la capacidad de disponer de comunicación dúplex bidireccional con un protocolo de transporte que no admite la comunicación dúplex de forma nativa, como HTTP.</span><span class="sxs-lookup"><span data-stu-id="73b5d-116">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>

- <span data-ttu-id="73b5d-117">A continuación, hay una clase <xref:System.ServiceModel.Channels.OneWayBindingElement>) opcional que proporciona comunicación unidireccional.</span><span class="sxs-lookup"><span data-stu-id="73b5d-117">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>

- <span data-ttu-id="73b5d-118">A continuación, hay un elemento de enlace de seguridad de secuencia opcional que puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="73b5d-118">Next is an optional stream security binding element which can be one of the following.</span></span>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="73b5d-119">A continuación hay un elemento de enlace de codificación del mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="73b5d-119">Next is a required message encoding binding element.</span></span> <span data-ttu-id="73b5d-120">Puede utilizar su propio codificador de mensajes o uno de los tres enlaces siguientes de codificación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="73b5d-120">You can use your own message encoder or one of the three message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

<span data-ttu-id="73b5d-121">En la parte inferior hay un elemento de transporte necesario.</span><span class="sxs-lookup"><span data-stu-id="73b5d-121">At the bottom is a required transport element.</span></span> <span data-ttu-id="73b5d-122">Puede utilizar su propio transporte o uno de los siguientes elementos de enlace de transporte Windows Communication Foundation (WCF) proporciona:</span><span class="sxs-lookup"><span data-stu-id="73b5d-122">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

<span data-ttu-id="73b5d-123">La tabla siguiente resume las opciones de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="73b5d-123">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="73b5d-124">Nivel</span><span class="sxs-lookup"><span data-stu-id="73b5d-124">Layer</span></span>|<span data-ttu-id="73b5d-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="73b5d-125">Options</span></span>|<span data-ttu-id="73b5d-126">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="73b5d-126">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="73b5d-127">Transacciones</span><span class="sxs-lookup"><span data-stu-id="73b5d-127">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="73b5d-128">No</span><span class="sxs-lookup"><span data-stu-id="73b5d-128">No</span></span>|
|<span data-ttu-id="73b5d-129">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="73b5d-129">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="73b5d-130">No</span><span class="sxs-lookup"><span data-stu-id="73b5d-130">No</span></span>|
|<span data-ttu-id="73b5d-131">Seguridad</span><span class="sxs-lookup"><span data-stu-id="73b5d-131">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="73b5d-132">No</span><span class="sxs-lookup"><span data-stu-id="73b5d-132">No</span></span>|
|<span data-ttu-id="73b5d-133">Encoding</span><span class="sxs-lookup"><span data-stu-id="73b5d-133">Encoding</span></span>|<span data-ttu-id="73b5d-134">Texto, binario, mecanismo de optimización de transmisión de mensajes (MTOM), personalizado</span><span class="sxs-lookup"><span data-stu-id="73b5d-134">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="73b5d-135">Sí</span><span class="sxs-lookup"><span data-stu-id="73b5d-135">Yes</span></span>|
|<span data-ttu-id="73b5d-136">Transporte</span><span class="sxs-lookup"><span data-stu-id="73b5d-136">Transport</span></span>|<span data-ttu-id="73b5d-137">TCP, HTTP, HTTPS, canalizaciones con nombre (también conocidas como IPC), igual a igual (P2P), Message Queuing (también conocido como MSMQ), personalizado</span><span class="sxs-lookup"><span data-stu-id="73b5d-137">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="73b5d-138">Sí</span><span class="sxs-lookup"><span data-stu-id="73b5d-138">Yes</span></span>|

<span data-ttu-id="73b5d-139">Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.</span><span class="sxs-lookup"><span data-stu-id="73b5d-139">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

## <a name="see-also"></a><span data-ttu-id="73b5d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="73b5d-140">See also</span></span>

- [<span data-ttu-id="73b5d-141">Información general acerca de la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="73b5d-141">Endpoint Creation Overview</span></span>](../endpoint-creation-overview.md)
- [<span data-ttu-id="73b5d-142">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="73b5d-142">Using Bindings to Configure Services and Clients</span></span>](../using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="73b5d-143">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="73b5d-143">System-Provided Bindings</span></span>](../system-provided-bindings.md)
- [<span data-ttu-id="73b5d-144">Procedimiento para personalizar un enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="73b5d-144">How to: Customize a System-Provided Binding</span></span>](how-to-customize-a-system-provided-binding.md)
- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="73b5d-145">Enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="73b5d-145">Custom Binding</span></span>](../samples/custom-binding.md)
