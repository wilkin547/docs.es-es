---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 0728e22205d4ac2c7674f7690e142aed51d42440
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399539"
---
# \<soapProcessing>

<span data-ttu-id="d1785-101">Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d1785-101">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**
  
## <a name="syntax"></a><span data-ttu-id="d1785-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1785-102">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1785-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d1785-103">Attributes and elements</span></span>  
  
<span data-ttu-id="d1785-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d1785-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1785-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1785-105">Attributes</span></span>  
  
|                   | <span data-ttu-id="d1785-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1785-106">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="d1785-107">Valor booleano que especifica si se deberían calcular las referencias a los mensajes entre las versiones del mensaje SOAP.</span><span class="sxs-lookup"><span data-stu-id="d1785-107">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d1785-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d1785-108">Child elements</span></span>

<span data-ttu-id="d1785-109">None</span><span class="sxs-lookup"><span data-stu-id="d1785-109">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d1785-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d1785-110">Parent elements</span></span>

|     | <span data-ttu-id="d1785-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1785-111">Description</span></span> |
| --- | ----------- |
| [**\<behavior>**](behavior-of-endpointbehaviors.md) | <span data-ttu-id="d1785-112">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="d1785-112">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d1785-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1785-113">Remarks</span></span>

<span data-ttu-id="d1785-114">El procesamiento SOAP es el proceso donde los mensajes se convierten entre las versiones del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d1785-114">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="d1785-115">El servicio de enrutamiento de Windows Communication Foundation (WCF) puede convertir mensajes de un protocolo a otro.</span><span class="sxs-lookup"><span data-stu-id="d1785-115">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="d1785-116">Si las versiones del mensaje de entrada y de salida son diferentes, se crea un nuevo mensaje de la versión correcta.</span><span class="sxs-lookup"><span data-stu-id="d1785-116">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="d1785-117">El procesamiento de los mensajes de una <xref:System.ServiceModel.Channels.MessageVersion> a otra se logra construyendo un nuevo mensaje WCF que contiene la parte del cuerpo y los encabezados pertinentes del mensaje WCF de entrada.</span><span class="sxs-lookup"><span data-stu-id="d1785-117">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="d1785-118">Los encabezados específicos del direccionamiento, o que se interpretan en el nivel del enrutador, no se usan durante la construcción del nuevo mensaje WCF porque estos encabezados son de una versión diferente (en el caso de los encabezados de direccionamiento) o se han procesado como parte de la comunicación entre el cliente y el enrutador.</span><span class="sxs-lookup"><span data-stu-id="d1785-118">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="d1785-119">La colocación de un encabezado en el mensaje de salida está determinada por si se marcó o no como comprendido al atravesar la capa del canal de entrada.</span><span class="sxs-lookup"><span data-stu-id="d1785-119">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="d1785-120">Los encabezados que no se entienden (como los encabezados personalizados) no se quitan y pasan así por el servicio del enrutamiento copiándose en el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="d1785-120">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="d1785-121">El cuerpo del mensaje se copia en el mensaje de salida.</span><span class="sxs-lookup"><span data-stu-id="d1785-121">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="d1785-122">A continuación, el mensaje se envía al canal de salida en el que se señalan todos los encabezados y se crearán y agregarán otros datos del sobre específicos de dicho protocolo/transporte de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="d1785-122">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="d1785-123">Dichos pasos de procesamiento tienen lugar cuando se especifica el comportamiento del procesamiento SOAP.</span><span class="sxs-lookup"><span data-stu-id="d1785-123">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="d1785-124">Este [\<soapProcessingExtension>](soapprocessing.md) comportamiento es un comportamiento de extremo que se aplica a todos los extremos de cliente (salientes) cuando se inicia el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="d1785-124">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="d1785-125">de forma predeterminada, el [\<routing>](routing-of-servicebehavior.md) comportamiento crea y adjunta un nuevo [\<soapProcessingExtension>](soapprocessing.md) comportamiento con `processMessages` establecido en `true` para cada punto de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="d1785-125">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="d1785-126">Si tiene un protocolo que el servicio de enrutamiento no entiende, o desea invalidar el comportamiento del procesamiento predeterminado, puede deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo o solo para extremos determinados.</span><span class="sxs-lookup"><span data-stu-id="d1785-126">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="d1785-127">Para deshabilitar el procesamiento SOAP para el servicio de enrutamiento completo en todos los extremos, establezca el `soapProcessing` atributo del [\<routing>](routing-of-servicebehavior.md) comportamiento en `false` .</span><span class="sxs-lookup"><span data-stu-id="d1785-127">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="d1785-128">Para desactivar el procesamiento SOAP para un extremo determinado, use este comportamiento y establezca el atributo `processMessages` en `false`; a continuación, adjunte este comportamiento al extremo en el que no desea que se ejecute el código de procesamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d1785-128">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="d1785-129">Cuando el [\<routing>](routing-of-servicebehavior.md) comportamiento configura el servicio de enrutamiento, omitirá la reaplicación del comportamiento del extremo puesto que ya existe uno.</span><span class="sxs-lookup"><span data-stu-id="d1785-129">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
