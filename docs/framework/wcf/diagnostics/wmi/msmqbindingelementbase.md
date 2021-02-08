---
description: 'Más información acerca de: Tracelistenerargument'
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 3aa5ec2343d73798f1cf5e3c7d4b5a8282f97ac9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803183"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="24f76-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="24f76-103">MsmqBindingElementBase</span></span>

<span data-ttu-id="24f76-104">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="24f76-104">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f76-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24f76-105">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="24f76-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="24f76-106">Methods</span></span>  

 <span data-ttu-id="24f76-107">La clase TraceListenerArgument no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="24f76-107">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="24f76-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="24f76-108">Properties</span></span>  

 <span data-ttu-id="24f76-109">La clase MsmqBindingElementBase tiene las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="24f76-109">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="24f76-110">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="24f76-110">CustomDeadLetterQueue</span></span>  

 <span data-ttu-id="24f76-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="24f76-111">Data type: string</span></span>  
  
 <span data-ttu-id="24f76-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-113">Un URI que contiene la ubicación de la cola de mensajes no enviados de cada aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o envío han fallado.</span><span class="sxs-lookup"><span data-stu-id="24f76-113">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="24f76-114">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="24f76-114">DeadLetterQueue</span></span>  

 <span data-ttu-id="24f76-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="24f76-115">Data type: string</span></span>  
  
 <span data-ttu-id="24f76-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-117">Un valor de enumeración que indica el tipo de cola de mensajes no enviados que se ha de usar.</span><span class="sxs-lookup"><span data-stu-id="24f76-117">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="24f76-118">Duradero</span><span class="sxs-lookup"><span data-stu-id="24f76-118">Durable</span></span>  

 <span data-ttu-id="24f76-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="24f76-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="24f76-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-121">Un valor que indica si los mensajes procesados por este enlace son duraderos o volátiles.</span><span class="sxs-lookup"><span data-stu-id="24f76-121">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="24f76-122">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="24f76-122">ExactlyOnce</span></span>  

 <span data-ttu-id="24f76-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="24f76-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="24f76-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-125">Un valor booleano que indica si los mensajes procesados por este enlace se reciben solo una vez.</span><span class="sxs-lookup"><span data-stu-id="24f76-125">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="24f76-126">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="24f76-126">MaxRetryCycles</span></span>  

 <span data-ttu-id="24f76-127">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="24f76-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="24f76-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-129">El número máximo de ciclos de reintento de entrega de mensajes a la aplicación receptora.</span><span class="sxs-lookup"><span data-stu-id="24f76-129">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="24f76-130">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="24f76-130">ReceiveErrorHandling</span></span>  

 <span data-ttu-id="24f76-131">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="24f76-131">Data type: string</span></span>  
  
 <span data-ttu-id="24f76-132">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-132">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-133">Los valores para el control de mensajes dudosos.</span><span class="sxs-lookup"><span data-stu-id="24f76-133">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="24f76-134">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="24f76-134">ReceiveRetryCount</span></span>  

 <span data-ttu-id="24f76-135">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="24f76-135">Data type: sint32</span></span>  
  
 <span data-ttu-id="24f76-136">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-136">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-137">El número máximo de intentos de reintento inmediato en un mensaje que se lee desde la cola de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="24f76-137">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="24f76-138">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="24f76-138">RetryCycleDelay</span></span>  

 <span data-ttu-id="24f76-139">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24f76-139">Data type: datetime</span></span>  
  
 <span data-ttu-id="24f76-140">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-140">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-141">Un valor que indica el tiempo de retardo entre los ciclos de reintento al intentar entregar un mensaje que no se pudo entregar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="24f76-141">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="24f76-142">timeToLive</span><span class="sxs-lookup"><span data-stu-id="24f76-142">TimeToLive</span></span>  

 <span data-ttu-id="24f76-143">Tipo de datos: datetime</span><span class="sxs-lookup"><span data-stu-id="24f76-143">Data type: datetime</span></span>  
  
 <span data-ttu-id="24f76-144">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-144">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-145">El intervalo de tiempo que indica cuánto tiempo pueden estar en la cola los mensajes procesados por este enlace antes de expirar.</span><span class="sxs-lookup"><span data-stu-id="24f76-145">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="24f76-146">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="24f76-146">UseMsmqTracing</span></span>  

 <span data-ttu-id="24f76-147">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="24f76-147">Data type: boolean</span></span>  
  
 <span data-ttu-id="24f76-148">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-148">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-149">Un valor booleano que indica si los mensajes procesados por este enlace se deberían seguir paso a paso.</span><span class="sxs-lookup"><span data-stu-id="24f76-149">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="24f76-150">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="24f76-150">UseSourceJournal</span></span>  

 <span data-ttu-id="24f76-151">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="24f76-151">Data type: boolean</span></span>  
  
 <span data-ttu-id="24f76-152">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="24f76-152">Access type: Read-only</span></span>  
  
 <span data-ttu-id="24f76-153">Un valor booleano que indica si las copias de mensajes procesados por este enlace deberían almacenarse en la cola de diario de origen.</span><span class="sxs-lookup"><span data-stu-id="24f76-153">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f76-154">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24f76-154">Requirements</span></span>  
  
|<span data-ttu-id="24f76-155">MOF</span><span class="sxs-lookup"><span data-stu-id="24f76-155">MOF</span></span>|<span data-ttu-id="24f76-156">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="24f76-156">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="24f76-157">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="24f76-157">Namespace</span></span>|<span data-ttu-id="24f76-158">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="24f76-158">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24f76-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="24f76-159">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
