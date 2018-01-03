---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1aeb100e1b8e160d30566cd43d67cbf49c6b5c4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltsoapprocessinggt"></a><span data-ttu-id="0fb1d-102">&lt;soapProcessing&gt;</span><span class="sxs-lookup"><span data-stu-id="0fb1d-102">&lt;soapProcessing&gt;</span></span>

<span data-ttu-id="0fb1d-103">Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-103">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="0fb1d-104">**\<sistema. ServiceModel >** </span><span class="sxs-lookup"><span data-stu-id="0fb1d-104">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="0fb1d-105">&nbsp;&nbsp;**\<comportamientos >** </span><span class="sxs-lookup"><span data-stu-id="0fb1d-105">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="0fb1d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors >** </span><span class="sxs-lookup"><span data-stu-id="0fb1d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="0fb1d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comportamiento >** </span><span class="sxs-lookup"><span data-stu-id="0fb1d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="0fb1d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing >**</span><span class="sxs-lookup"><span data-stu-id="0fb1d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0fb1d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fb1d-109">Syntax</span></span>

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0fb1d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0fb1d-110">Attributes and elements</span></span>

<span data-ttu-id="0fb1d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0fb1d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="0fb1d-112">Attributes</span></span>

|                   | <span data-ttu-id="0fb1d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fb1d-113">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="0fb1d-114">Valor booleano que especifica si se deberían calcular las referencias a los mensajes entre las versiones del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-114">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="0fb1d-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0fb1d-115">Child elements</span></span>

<span data-ttu-id="0fb1d-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="0fb1d-116">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0fb1d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0fb1d-117">Parent elements</span></span>

|     | <span data-ttu-id="0fb1d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fb1d-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0fb1d-119">**\<comportamiento >**</span><span class="sxs-lookup"><span data-stu-id="0fb1d-119">**\<behavior>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | <span data-ttu-id="0fb1d-120">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-120">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0fb1d-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fb1d-121">Remarks</span></span>

<span data-ttu-id="0fb1d-122">El procesamiento SOAP es el proceso donde los mensajes se convierten entre las versiones del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-122">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="0fb1d-123">El servicio de enrutamiento [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] puede convertir los mensajes de un protocolo en otro.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-123">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="0fb1d-124">Si las versiones del mensaje de entrada y de salida son diferentes, se crea un nuevo mensaje de la versión correcta.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-124">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="0fb1d-125">Procesamiento de mensajes de una <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` a otra se logra construyendo un nuevo [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] mensaje que contiene la parte del cuerpo y los encabezados pertinentes de la entrada [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] mensaje.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-125">Processing messages from one <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion`  to another is accomplished by constructing a new [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message that contains the body part and relevant headers from the incoming [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message.</span></span> <span data-ttu-id="0fb1d-126">Los encabezados específicos del direccionamiento, o que se interpretan en el nivel del enrutador, no se usan durante la construcción del nuevo mensaje WCF porque estos encabezados son de una versión diferente (en el caso de los encabezados de direccionamiento) o se han procesado como parte de la comunicación entre el cliente y el enrutador.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-126">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="0fb1d-127">La colocación de un encabezado en el mensaje de salida está determinada por si se marcó o no como comprendido al atravesar la capa del canal de entrada.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-127">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="0fb1d-128">Los encabezados que no se entienden (como los encabezados personalizados) no se quitan y pasan así por el servicio del enrutamiento copiándose en el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-128">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="0fb1d-129">El cuerpo del mensaje se copia en el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-129">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="0fb1d-130">A continuación, el mensaje se envía al canal de salida en el que se señalan todos los encabezados y se crearán y agregarán otros datos del sobre específicos de dicho protocolo/transporte de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-130">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="0fb1d-131">Dichos pasos de procesamiento tienen lugar cuando se especifica el comportamiento del procesamiento SOAP.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-131">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="0fb1d-132">Esto [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) comportamiento es un comportamiento del punto de conexión que se aplica a todos los extremos de cliente (saliente) cuando se inicia el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-132">This [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="0fb1d-133">de manera predeterminada, el [ \<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportamiento crea y asocia una nueva [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) comportamiento con `processMessages` establecido en `true` para cada uno punto de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-133">default, the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="0fb1d-134">Si tiene un protocolo que el servicio de enrutamiento no entiende, o desea invalidar el comportamiento del procesamiento predeterminado, puede deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo o solo para puntos de conexión determinados.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-134">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="0fb1d-135">Para deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo en todos los puntos de conexión, establezca el `soapProcessing` atributo de la [ \<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportamiento `false`.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-135">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="0fb1d-136">Para desactivar el procesamiento SOAP para un extremo determinado, use este comportamiento y establezca el atributo `processMessages` en `false`; a continuación, adjunte este comportamiento al extremo en el que no desea que se ejecute el código de procesamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-136">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="0fb1d-137">Cuando el [ \<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) comportamiento configura el servicio de enrutamiento, se omitirán volver a aplicar el comportamiento de punto de conexión porque ya existe uno.</span><span class="sxs-lookup"><span data-stu-id="0fb1d-137">When the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
