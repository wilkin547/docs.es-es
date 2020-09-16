---
title: Enlaces personalizados
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: 062aba26227fedeea3e5f462ebf5d55cf0cba56c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540002"
---
# <a name="custom-bindings"></a><span data-ttu-id="8d656-102">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="8d656-102">Custom Bindings</span></span>

<span data-ttu-id="8d656-103">Puede usar la clase <xref:System.ServiceModel.Channels.CustomBinding> cuando uno de los enlaces proporcionados por el sistema no cumple los requisitos de su servicio.</span><span class="sxs-lookup"><span data-stu-id="8d656-103">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="8d656-104">Todos los enlaces se construyen a partir de un conjunto ordenado de elementos de enlace.</span><span class="sxs-lookup"><span data-stu-id="8d656-104">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="8d656-105">Los enlaces personalizados pueden crearse a partir de un conjunto de elementos de enlace proporcionado por el sistema o incluir elementos de enlace personalizado definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8d656-105">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="8d656-106">Puede utilizar elementos de enlaces personalizados, por ejemplo, para habilitar el uso de nuevos transportes o codificadores en un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="8d656-106">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="8d656-107">Para obtener ejemplos prácticos, vea [ejemplos de enlace personalizado](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="8d656-107">For working examples, see [Custom Binding Samples](/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span></span> <span data-ttu-id="8d656-108">Para obtener más información, vea [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="8d656-108">For more information, see [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md).</span></span>

## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="8d656-109">Construcción de un enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="8d656-109">Construction of a Custom Binding</span></span>

<span data-ttu-id="8d656-110">Un enlace personalizado se construye utilizando el constructor <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> de una colección de elementos de enlace que se apilan en un orden específico:</span><span class="sxs-lookup"><span data-stu-id="8d656-110">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>

- <span data-ttu-id="8d656-111">En la parte superior hay una clase <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> opcional que permite el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="8d656-111">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>

- <span data-ttu-id="8d656-112">A continuación, hay una clase <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> opcional que proporciona una sesión y mecanismos de ordenación, como se define en la especificación WS-ReliableMessaging.</span><span class="sxs-lookup"><span data-stu-id="8d656-112">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="8d656-113">Una sesión puede cruzar SOAP y transportar intermediarios.</span><span class="sxs-lookup"><span data-stu-id="8d656-113">A session can cross SOAP and transport intermediaries.</span></span>

- <span data-ttu-id="8d656-114">A continuación, hay una clase <xref:System.ServiceModel.Channels.SecurityBindingElement> opcional que proporciona características de seguridad, como autorización, autenticación, protección y confidencialidad.</span><span class="sxs-lookup"><span data-stu-id="8d656-114">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>

- <span data-ttu-id="8d656-115">A continuación, hay una clase <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> opcional que proporciona la capacidad de disponer de comunicación dúplex bidireccional con un protocolo de transporte que no admite la comunicación dúplex de forma nativa, como HTTP.</span><span class="sxs-lookup"><span data-stu-id="8d656-115">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>

- <span data-ttu-id="8d656-116">A continuación, hay una clase <xref:System.ServiceModel.Channels.OneWayBindingElement>) opcional que proporciona comunicación unidireccional.</span><span class="sxs-lookup"><span data-stu-id="8d656-116">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>

- <span data-ttu-id="8d656-117">A continuación, hay un elemento de enlace de seguridad de secuencia opcional que puede ser uno de los siguientes.</span><span class="sxs-lookup"><span data-stu-id="8d656-117">Next is an optional stream security binding element which can be one of the following.</span></span>

  - <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>

  - <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>

- <span data-ttu-id="8d656-118">A continuación hay un elemento de enlace de codificación del mensaje requerido.</span><span class="sxs-lookup"><span data-stu-id="8d656-118">Next is a required message encoding binding element.</span></span> <span data-ttu-id="8d656-119">Puede utilizar su propio codificador de mensajes o uno de los tres enlaces siguientes de codificación de mensajes:</span><span class="sxs-lookup"><span data-stu-id="8d656-119">You can use your own message encoder or one of the three message encoding bindings:</span></span>

  - <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>

  - <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>

<span data-ttu-id="8d656-120">En la parte inferior hay un elemento de transporte necesario.</span><span class="sxs-lookup"><span data-stu-id="8d656-120">At the bottom is a required transport element.</span></span> <span data-ttu-id="8d656-121">Puede utilizar su propio transporte o uno de los siguientes elementos de enlace de transporte Windows Communication Foundation (WCF) proporciona:</span><span class="sxs-lookup"><span data-stu-id="8d656-121">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>

- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>

- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>

- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>

<span data-ttu-id="8d656-122">La tabla siguiente resume las opciones de cada nivel.</span><span class="sxs-lookup"><span data-stu-id="8d656-122">The following table summarizes the options for each layer.</span></span>

|<span data-ttu-id="8d656-123">Nivel</span><span class="sxs-lookup"><span data-stu-id="8d656-123">Layer</span></span>|<span data-ttu-id="8d656-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="8d656-124">Options</span></span>|<span data-ttu-id="8d656-125">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8d656-125">Required</span></span>|
|-----------|-------------|--------------|
|<span data-ttu-id="8d656-126">Transacciones</span><span class="sxs-lookup"><span data-stu-id="8d656-126">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="8d656-127">No</span><span class="sxs-lookup"><span data-stu-id="8d656-127">No</span></span>|
|<span data-ttu-id="8d656-128">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="8d656-128">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="8d656-129">No</span><span class="sxs-lookup"><span data-stu-id="8d656-129">No</span></span>|
|<span data-ttu-id="8d656-130">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8d656-130">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="8d656-131">No</span><span class="sxs-lookup"><span data-stu-id="8d656-131">No</span></span>|
|<span data-ttu-id="8d656-132">Encoding</span><span class="sxs-lookup"><span data-stu-id="8d656-132">Encoding</span></span>|<span data-ttu-id="8d656-133">Texto, binario, mecanismo de optimización de transmisión de mensajes (MTOM), personalizado</span><span class="sxs-lookup"><span data-stu-id="8d656-133">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="8d656-134">Sí</span><span class="sxs-lookup"><span data-stu-id="8d656-134">Yes</span></span>|
|<span data-ttu-id="8d656-135">Transporte</span><span class="sxs-lookup"><span data-stu-id="8d656-135">Transport</span></span>|<span data-ttu-id="8d656-136">TCP, HTTP, HTTPS, canalizaciones con nombre (también conocidas como IPC), igual a igual (P2P), Message Queuing (también conocido como MSMQ), personalizado</span><span class="sxs-lookup"><span data-stu-id="8d656-136">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="8d656-137">Sí</span><span class="sxs-lookup"><span data-stu-id="8d656-137">Yes</span></span>|

<span data-ttu-id="8d656-138">Además, puede definir sus propios elementos de enlace e insertarlos entre cualquiera de las capas definidas anteriores.</span><span class="sxs-lookup"><span data-stu-id="8d656-138">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d656-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d656-139">See also</span></span>

- [<span data-ttu-id="8d656-140">Información general acerca de la creación de puntos finales</span><span class="sxs-lookup"><span data-stu-id="8d656-140">Endpoint Creation Overview</span></span>](../endpoint-creation-overview.md)
- [<span data-ttu-id="8d656-141">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8d656-141">Using Bindings to Configure Services and Clients</span></span>](../using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="8d656-142">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="8d656-142">System-Provided Bindings</span></span>](../system-provided-bindings.md)
- [<span data-ttu-id="8d656-143">Procedimiento para personalizar un enlace proporcionado por el sistema</span><span class="sxs-lookup"><span data-stu-id="8d656-143">How to: Customize a System-Provided Binding</span></span>](how-to-customize-a-system-provided-binding.md)
- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="8d656-144">Enlace personalizado</span><span class="sxs-lookup"><span data-stu-id="8d656-144">Custom Binding</span></span>](../samples/custom-binding.md)
